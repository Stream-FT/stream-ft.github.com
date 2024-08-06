# Customer 
Information about your customer - existing or new. streamOS takes care of creating/reconciling this customer with existing customers on your accounting platform, ensuring alignment with your accounting practices and approval workflows. 

## The Customer Object:

### Essential Information

- **Customer Id**: The streamOS Id associated with the customer
- **Customer Name**: The name of the customer (Required)
- **Customer Email**: The email of the customer (Required)

### Accounting Specific Information (Optional - depending on your accounting practices)

- **Contact Name**: Name of the contact person at the customer
- **Phone Number**: Phone number of the contact person
- **Currency Code**: Currency Code associated with the customer
- **Notes**: Additional notes that you would like to register 
- **Address**:
    - **Type**: billing / shipping / po_bo /unknown
    - **Address1**: First line of the address
    - **Address2**: Second line of the address
    - **City**: City
    - **Region**: State
    - **Postal Code**

