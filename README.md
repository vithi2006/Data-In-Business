

# Data In Business

In this project I was given the following scenario:

## Scenario Background
"Paws & Whiskers" is a growing pet shop that aims to improve its business by analysing sales, customer information, and inventory data. Currently, the data is collected manually or stored in spreadsheets. Management is interested in transitioning to Microsoft Azure to streamline data storage, analysis, and reporting, enabling them to make data-driven decisions.

This is how I would explain to management about their options:
## 2: DATA LAWS AND REGULATIONS;
 
## a) GDPR Compliance: Highlight the importance of adhering to the General Data Protection Regulation (GDPR), particularly as it relates to storing and processing customer information.
 
Even for a small business like a pet shop, GDPR applies if you collect or store personal data from EU customers. It's about being transparent, respectful, and secure with your customers’ information.
Simple Steps for the Pet Shop
•	Use a privacy policy on the website and in-store to explain how customer data is used.
•	Ask for explicit consent when collecting data (e.g., tick boxes on forms).
•	Implement data protection measures (passwords, encryption, limited access).
•	Make it easy for customers to request their data or have it deleted.
•	Customer data base must store only necessary personal info, protect it, and allow customers to update or delete it.
•	For online store, consent must be obtained before collecting data via forms or cookies.
•	Marketing emails, customers must opt-in, and you must give a clear way to unsubscribe.
•	Staff data is also subject to GDPR and must be protected.
•	If you have CCTV in-store, inform customers of surveillance and store footage securely.
## b) The Data Protection Act 2018 (DPA 2018) is the UK’s implementation of the General Data Protection Regulation (GDPR), and it governs how businesses, including pet stores, collect, use, store, and protect personal data.
Whether your pet shop is small or large, if you collect customer information (in-store or online), the DPA applies.
Examples of Data You May Collect:
•	Customer names, phone numbers, email addresses
•	Delivery or billing addresses
•	Pet details (for grooming, boarding, or medical services)
•	Payment information (via POS or online)
•	Loyalty program data
•	CCTV footage in-store
## Key Principles of DPA 2018 Compliance for a Pet Shop
 	 
Lawfulness, fairness, and transparency	Clearly inform customers how and why you collect their data. Use a privacy notice.
Purpose limitation	Only collect data needed for specific purposes (e.g., order delivery, pet appointments).
Data minimisation	Don’t ask for more information than necessary.
Accuracy	Keep customer data up to date (e.g., allow updates to contact info).
Storage limitation	Don’t keep data longer than necessary (e.g., delete inactive accounts after a set period).
Integrity and confidentiality	Use secure systems to store data (e.g., encrypted databases, password protection).
Accountability	Be able to show how your store complies with the DPA (e.g., policies, staff training).
The DPA 2018 requires your pet store to handle personal data responsibly and transparently, ensuring customers’ privacy is respected. It’s about building trust while staying compliant with UK law.
 
## C: Other Industry Standards
Payment Card Industry Data Security Standard (PCI DSS);
While not a UK law, PCI DSS compliance is enforced through contractual agreements with banks and payment processors. Failure to comply can result in fines, increased transaction fees, and potential loss of the ability to process card payments.
## Key PCI DSS Requirements:
•	Secure Storage: Protect stored cardholder data using encryption and secure access controls. 
•	Data Transmission: Encrypt cardholder data during transmission over open, public networks.
•	Access Control: Restrict access to cardholder data to authorized personnel only.
•	Regular Monitoring: Monitor and test networks regularly to identify vulnerabilities.
•	Security Policies: Maintain an information security policy addressing data protection practices. 
 
## 3. Azure Service Recommendations 
  
## Data Storage 
  
Azure SQL Database is ideal for structured data such as customer details, transactions, and inventory. It offers built-in high availability, security, and performance tuning. 
  
Azure Blob Storage provides scalable and cost-effective storage for unstructured and semi-structured data, such as customer-uploaded pet images, scanned documents, or raw data files. Blob Storage supports different access tiers (Hot, Cool, and Archive), allowing cost-effective management of infrequently accessed data while still enabling seamless integration with Azure analytics and AI services. 
  
To support large-scale analytics and long-term storage of structured and unstructured data, Azure Data Lake Storage Gen2 is recommended. It combines the scalability and cost benefits of Azure Blob Storage with hierarchical file system capabilities, making it ideal for big data analytics. This service allows Paws & Whiskers to store historical data, event logs, and aggregated reports in a centralized repository, which can be easily queried and transformed by Azure analytics tools. 
  
## Data Analysis Tools 
  
Azure Synapse Analytics enables real-time and large-scale analysis of data from across the business. It supports querying both structured and unstructured data, which is ideal for understanding sales performance, seasonal trends, and customer engagement. 
  
Power BI, which integrates with Synapse, can visualize this data through interactive dashboards accessible to staff and management. 
  
Azure Machine Learning can help build models for customer segmentation, churn prediction, and personalized marketing by using predictive capabilities. These insights can drive better decision-making and customer engagement. 
  
## Data Integration and Automation 
Azure Data Factory is recommended to automate data movement and transformation. It connects to various sources like point-of-sale systems, websites, and third-party platforms. This reduces manual work and ensures consistent, accurate data is available for reporting and analysis. 
These services together provide a modern, scalable solution that supports daily operations and long-term business intelligence needs. 
  
To protect critical data, Azure Backup should be used for automatic, encrypted backups of databases and file systems. Azure Site Recovery offers disaster recovery by replicating applications and data to alternate regions, allowing operations to resume quickly in case of failure. Geo-redundant storage ensures further resilience by duplicating data across locations. 

## 4. Data Types and Data Modelling
Paws and Whiskers will need to work with various types of structured data.
## Data types: The key data types will be,
Customer Information: Name, email, address, phone number and pet preference
Transaction: Purchase date, items bought, quantity, total amount and payment method.
Product categories: Item names, types, price, supplier, stock level.
Pet Inventory: Species, breed, age, availability and care instructions
## Data Modelling: A Relational database model is recommended. This approach involves organising the data into related tables:
•	Customers table stores customer details where the primary key is Customer ID.
•	Products table contains product information, where Product ID will be the Primary Key.
•	Pets table tracks pets available or sold. here, the primary key will be PetID.
•	Transactions table linked to customers and products where the primary key is Transaction ID and Foreign Keys are Customer ID and ProductID.
The Relationship database model supports data integrity. It avoids duplication and makes it easier to run queries for reporting and decision making. Relationships describes how tables are linked using primary and foreign keys.
One to many: Customer 🡪 Transaction
One customer can make many transactions. Customer id is the primary key in the customers table and a foreign key in the Transactions table.
Many-to-Many: Transactions🡨🡪 Products
One transaction can include many products, and each product can appear in many transactions

## 5. Data Storage Formats and Structures in Azure
 
Selecting the appropriate data storage formats and structures in Microsoft Azure is crucial for "Paws & Whiskers" to ensure efficient data management, seamless analytics, and robust security in compliance with data protection laws.
 
Azure offers a range of storage solutions and data formats tailored to different business needs. For instance, Azure Blob Storage is ideal for storing unstructured data, while Azure SQL Database and Azure Data Lake are suitable for structured and analytical workloads. Common data formats such as CSV and JSON are widely supported and optimised for different use cases. Additionally, Azure provides built-in security features like Transparent Data Encryption (TDE), Azure Key Vault, role-based access control (RBAC) to safeguard sensitive information based on user rights and advanced auditing and threat detection tools, enabling "Paws & Whiskers" to monitor data access and respond to potential security incidents promptly.
 
Transitioning from manual or spreadsheet-based data management to Azure’s cloud-native data storage and structures represents a significant shift for "Paws & Whiskers." Currently, the business relies on manual entry and spreadsheets, which often leads to data duplication, inconsistencies, and limited accessibility. These traditional methods are prone to human error, make it difficult to enforce robust security, and are not scalable as the business grows.
 
By adopting Azure’s structured storage solutions-such as Azure Blob Storage for unstructured data, Azure SQL Database for transactional records, and Azure Data Lake for analytics-"Paws & Whiskers" can centralise all data in secure, scalable, and easily accessible repositories. This modern approach eliminates the risk of data loss from local hardware failures and reduces the administrative burden of maintaining disparate files. Azure’s built-in encryption, role-based access controls, and compliance features ensure that sensitive customer and business data is protected far beyond what is possible with spreadsheets or local files.
 
The proposed benefits of this change for Paws & Whiskers are substantial:
 
1.	Improved Data Integrity and Consistency: Centralised, cloud-based databases prevent duplication and ensure everyone accesses the most up-to-date information, unlike spreadsheets that can quickly become outdated or fragmented. Industry use cases support the use of Azure’s data management ecosystem in directly improving organisational data quality and reliability for decision making (Duncan, 2024).
2.	Enhanced Security and Compliance: Azure’s advanced security features-including encryption at rest and in transit, Azure Key Vault for key management, and granular access controls-help meet GDPR and Data Protection Act requirements, reducing the risk of data breaches and regulatory penalties (Duncan, 2024; Ravindran, 2024).
3.	Automated Backups and Disaster Recovery: Azure provides automated backup and disaster recovery solutions, minimizing downtime and safeguarding against data loss from accidental deletion or system failure (Apple, 2024).
4.	Scalability and Flexibility: As the business grows, Azure’s services can seamlessly scale to accommodate larger datasets and more complex analytics, without the need for costly hardware upgrades or manual intervention (Wright, 2018).
5.	Faster, Data-Driven Decision-Making: With structured, queryable data and integration with analytics tools, management can generate real-time insights into sales, inventory, and customer trends, empowering more informed strategic decisions (Duncan, 2024).
 
## In conclusion, moving to Azure transforms data management from a fragmented, manual process to a streamlined, secure, and scalable system. This not only boosts operational efficiency and data reliability but also positions "Paws & Whiskers" for sustained growth and regulatory compliance in a data-driven marketplace.

  
