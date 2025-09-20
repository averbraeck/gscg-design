# 5.2. Class design of the simulation model

The `Actor` with one or more `Role` instances is at the heart of the design. The `Actor` represents a (department in a) supply chain organization that is responsible to process certain information and/or products. The processing of information and/or products is done by a so-called `ContentHandler`. Roles only have handlers for the tasks they are supposed to so. So a `FinancingRole` has a `ContentHandler` for an `Invoice`, whereas a `SellingRole` has a `ContentHandler` for an `Order`. The actors, roles, and content handlers enable a fine-grained set of responses for information coming in, where each handler typically consists of only a few lines of code that determine whether to react on the incoming content, how to react, and when to react. Reactions are always implemented by sending new content -- sometimes to the sender of the original request, sometimes to another actor or role. A `Role` can also start autonomous processes at regular intervals, e.g., to check on inventory or to purchase goods.

The relation between these important objects is as follows:

![](diagrams/actor-classes.svg)

