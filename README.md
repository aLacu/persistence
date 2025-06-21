# persistence

This project is a proof of concept library to implement a datastructure with a centralized entity management.

Characteristics:

- the centralized entity has an id, an entity type that should be extensible, timestamp of creation, validity timestamp from and to, a transaction unit entity, and an ownership
- the owner is not centralized, it exists before the entity is inserted
- the owner is connected to a user or multiple user, any user connected to an owner can see every entity linked to that owner
- the transaction unit creates a graph (not a tree, we can have a transaction unit that merges many branches into one) 
- the transaction unit is centralized with owner the super user
- a transaction unit is linked to any number of transaction unit already inserted
- a transaction unit can be rolled back by rolling back all the transaction units that branches from that and recursively so, unless it is frozen
