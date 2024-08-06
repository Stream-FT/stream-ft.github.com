# How to - APIs
1. [Recursive Contract Construction](#recursive-contract-construction)
2. [Setup Flow](#overall-setup-flow)
3. [Operational Flow](#operational-flow)
4. [Modifications and Updates](#modifications--updates)

### General Principles

###### Recursive Contract Construction 

![Contract-Hierarchy](img/parent_hierarchy.png)

Constructing objects in streamOS is recursive, start with the lowest in the tree and continue building upwards through the hierarchy. Every reference to a UUID in a POST is an id of an object returned from another POST statement. 
streamOS maintains a factory that it references for all of these objects and links them together on run time. 

The Parent Contract is your ultimate tie in to the customer, so until the Parent Contract is created - contracts are orphans. 

Plans and Contracts can be reused - so once created you can use them over and over in other create objects for free, by just referencing the id.

###### Overall Setup Flow 

The overall flow of creation follows this pattern: 

1. Create Customers: Create all the customers in streamOS appropriately and store the streamOS customer_ids
2. Create Products: Create all the customers in streamOS appropriately and store the streamOS customer_ids
3. Create Contracts: Create the appropriate contract structure that represent your contracts, verify using the UI if required

###### Operational Flow

- **Structure Usage:** Ensure your usage flow is of the format specified in the /contracts/org_id/usage [endpoint](https://api.streamos.io/swagger-ui/#/Usage/post_contracts__organization_id__factory_usage) 
- **Get Charges:** Every update of usage or a contract upload / update triggers a run of the contracts - use the charges [endpoint](https://api.streamos.io/swagger-ui/#/Contracts/get_contracts__organization_id__factory_charges) to get the results.
- **Force a contract run:** if you want to force a contract run trigger [this](https://api.streamos.io/swagger-ui/#/Contracts/post_contracts__organization_id__factory_run)


###### Modifications & Updates 

**Modifying Contracts:** Modifying contracts in streamOS is tantamount to creating a new contract. You would provide the same information as you did during contract creation to the same endpoint, except for the information that you are changing. Ensure you use the same id as the object you are replacing so that the system knows to replace existing references to it. 

**Modifying Plans:** Plans are modified in a similar fashion - post the modified information to the same endpoint with the same id to replace a plan definition. However, now that a plan has been changed - call the refresh [endpoint](https://api.streamos.io/swagger-ui/#/Contracts/options_contracts__organization_id__refresh) to ensure that all contracts that reference this plan update their local copies of the plan. 




