# Users 

streamOS has a light weight user model.

**Operational User:** Permissions to create items and events within the system (with approval). Creation events like contract,customer & product creation can be made by this user. However, all events need to be approved by a user with manager permissions before they become active.  

**Operational Manager:** All permissions of operational user + permissions to approve requests from operational users. NOTE: Operational Manager's cannot approve their own requests. 

**Administrative User:** Ability to setup changes in the system. Create new plan types that can be applied to other contracts. 

**Administrative Manager:** Approve permissions for requests by Administrative Users. As well as core system event such as setting up and managing integrations, users and other core system(s). Actions like final invoice approval, contract editing approval and other key functions are part of this users permissions.