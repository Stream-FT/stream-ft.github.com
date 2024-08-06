# Usage 
The Usage object is the store of actual usage of products and services of your organization. Usage is associated with a Product (`product_id`) and a ProductContract (`contract_id`) that wraps billing information about an instance of that product. 

The above structure allows for customers to record usage for their clients against multi use-cases under the same contract.

**Example**

Company A sells an Employee Verification Product to both Youtube and Google Voice. 
However, they have a contract with their parent Google and invoice them once. 
```
Parent Contract: Google 
    Sub Contract: YouTube
        Product Contract: 
            - contract_id: xxxxxx
            - product: Employee Verification (`product_id`: yyyyyy)
    Sub Contract: Google Voice
        Product Contract: 
            - contract_id: aaaaaa
            - product: Employee Verification (`product_id`: yyyyyy)
```
Their usage data would therefore look like: 

| date       | contract_id | product_id | quantity |
|------------|-------------|------------|----------|
| 2024-1-1   | xxxxxx      | yyyyyy     | 123      |
| 2024-1-1   | aaaaaa      | yyyyyy     | 12      |
| 2024-1-2   | xxxxxx      | yyyyyy     | 56      |
| 2024-1-3   | xxxxxx      | yyyyyy     | 4      |
| 2024-1-3   | aaaaaa      | yyyyyy     | 7      |
| 2024-1-4   | xxxxxx      | yyyyyy     | 8      |
| 2024-1-5   | aaaaaa      | yyyyyy     | 9      |


The above structure would reflect billables toward YouTube and Google Voice separately but would also allow roll-ups to the parent Google.