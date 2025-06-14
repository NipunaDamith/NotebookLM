## Scenario 1 Results
Input Sources: BUS5001-Wk06-Data

Prompt 1: 
-Generate 5 practice exam questions covering data storage models, database processing (OLTP vs OLAP), and cloud architectures.
              
Generated Outputs:
Practice Exam Questions: Data Management and Cloud Platforms
1.Database Processing: Differentiate between Online Transaction Processing (OLTP) and Online Analytical Processing (OLAP) based on their typical access patterns and primary users. Explain why organizations are usually reluctant to let business analysts run ad hoc analytic queries directly on an OLTP database.
2.ACID Properties: List and briefly explain each of the four ACID properties (Atomicity, Consistency, Isolation, Durability) for transactions. Provide a practical example for one of these properties as described in the sources.
3.Data Warehouses & ETL/ELT: Explain the primary purpose of a data warehouse within a company's data architecture. Describe the process of ETL (Extract, Transform, Load) in the context of populating a data warehouse, and briefly mention how this process has more recently evolved.
4.Big Data Characteristics: What are the three "Vs" commonly used to quantify Big Data? Choose one of these "Vs" and explain a business or technological factor that has contributed to its growth according to the sources.
5.Data Lakes: Define what a Data Lake is in the context of data storage and analytics. List two benefits of implementing a Data Lake and identify two key Data Governance considerations for a Data Lake to avoid it becoming a "Data Swamp".

Prompt 2: 
-Create a study guide summarizing NoSQL, ACID vs BASE, CAP theorem, and data lake concepts.

Generated Outputs:
1. NoSQL Databases
NoSQL (Not only SQL, Non SQL) databases emerged in the 2000s, driven by the Web 2.0 era's requirements for scale that traditional ACID-compliant relational databases struggled to meet.
Limitations of Relational Database Management Systems (RDBMS) that led to NoSQL:
•Scalability: RDBMS primarily scale up (on more powerful/expensive machines) rather than scale out (distribute across multiple servers). This makes joining tables across distributed systems difficult and complicates maintaining ACID properties.
•Restricted Representations: RDBMS require all data to be converted into tables, and SQL querying was developed for structured data, which became a limitation for evolving and diverse data types.
Key Characteristics & Advantages of NoSQL:
•Unlike RDBMS that store data in tables made of individual rows, NoSQL databases store data in "collections" made of "individual documents" (or columns, etc.).
•Often designed for schema-on-read, allowing for flexible data structures.
Types of NoSQL Databases:
•Column Databases:
◦Essence: Data for columns are grouped together on disk, not rows.
◦Advantages: Optimizes queries that aggregate values of specific columns because all values to be aggregated exist within the same disk blocks. Offers efficient compression by removing redundancy.
•Graph Databases:
◦Structure: Uses graph structures with Nodes, Edges (links between nodes), and Properties (key/value tuples associated with a node).
◦Use Case: Allows fast and simple querying of complex organizational data, particularly for connected data, where SQL queries would be more verbose and less performant.
◦Examples: Neo4J, Amazon Neptune, Dgraph.
◦Applications: Fraud detection, real-time recommendation engines, master data management (MDM), network and IT operations, identity and access management (IAM).
•Key-Value Pair (Cache) Databases:
◦Characteristics: Typically offer key/value in-memory storage for fast querying of volume-limited data.
◦Use Cases: Ideal for fast and cost-effective querying of frequently accessed, rarely changing data, or to reduce the load on an underlying database.
◦Examples: Redis, Memcached.
•Time Series Databases:
◦Optimization: Optimized for storing and querying time series data, which are values associated with a time key (e.g., IoT sensor status over time).
◦Use Cases: Monitoring analytics, IoT logging and status querying, trading history.
•Document Databases (e.g., MongoDB):
◦MongoDB is a JSON-oriented document database, internally using BSON (a binary encoded variant).
◦It is widely used and provides a developer-friendly ecosystem.
◦Data can be stored using "document embedding" (nesting related data within a single document, e.g., actors within a film document), which avoids joins but can lead to data duplication and inconsistencies. Alternatively, documents can be linked using identifiers, similar to foreign keys in relational databases.
2. ACID vs. BASE
ACID Properties (for transactions): ACID properties are a set of guarantees ensuring the reliability of database transactions.
•Atomicity: Guarantees that every transaction is "all-or-nothing"—either fully processed or not at all. For example, a payment and inventory update in a sale must both occur or neither occurs.
•Consistency: Ensures that transactions enforce business rules to maintain data accuracy. For instance, payments must match item prices and inventory must adjust accordingly.
•Isolation: Guarantees that concurrent transactions do not affect each other, meaning that even if multiple attempts are made simultaneously, only one customer can purchase the last item of a product.
•Durability: Ensures that completed transactions remain permanently recorded and survive system failures. Sale records, for example, are permanent, ensuring reliability in inventory and financial data post-transaction.
The term BASE is mentioned in the sources as a contrast to ACID for distributed systems, but its individual properties (Basically Available, Soft State, Eventually Consistent) are not elaborated upon in the provided text.
3. CAP Theorem in Distributed Systems
The CAP theorem states that a distributed system can only guarantee two out of three core properties: Consistency (C), Availability (A), and Partition Tolerance (P).
•Consistency (C): Ensures that all customers see the latest updates regardless of their location. The trade-off is that it may sacrifice access during network issues to ensure up-to-date data.
•Availability (A): Guarantees an "always-on" service, meaning customers can always access their points or services even during network failures. The trade-off is that they might not always see the most recent data.
•Partition Tolerance (P): Refers to the system's resilience to network failures or disruptions between different locations or nodes. This is generally considered "non-negotiable" for distributed systems to function.
The Trade-Offs: The CAP theorem dictates that you must choose which two properties to prioritize:
•Consistency + Partition Tolerance: If prioritized, during a network failure, customers might not be able to access their data at all locations, thus sacrificing Availability.
•Availability + Partition Tolerance: If prioritized, during a network issue, customers can still use the service, but they might not see the most recent data if it was updated in another location, thus sacrificing Consistency.
•Consistency + Availability: If prioritized, and the network between nodes fails, the system overall would fail to operate, thus sacrificing Partition Tolerance.
Example (International Coffee Shop Chain): Consider an international coffee shop chain with a shared rewards program using a distributed database across locations.
•Consistency: A customer sees their latest points update immediately, no matter where they are (e.g., earning points in New York and seeing them in Paris).
•Availability: Even with internal network issues, the customer can still check or use their points, avoiding service outages.
•Partition Tolerance: If the network connection between New York and Paris is disrupted, both locations continue to operate independently and provide service. The theorem implies the system cannot fully guarantee all three simultaneously in such a scenario.
4. Data Lake Concepts
A Data Lake is a central storage repository that holds data from many sources in a raw, granular format. It can store structured, semi-structured, or unstructured data, allowing for quick ingestion and flexible storage for future use cases.
Key Characteristics:
•Schema-on-read: The schema is applied when the data is read, rather than enforced upon write (as in traditional databases).
•A collection of data, not necessarily a rigid platform.
•An ideal place for evolving data sets.
Benefits of a Data Lake:
•Ability to quickly ingest high volumes of diverse data structures.
•Enables advanced analytics and data exploration.
•Offers scalability and reduced storage costs.
Data Governance Considerations (to avoid a "Data Swamp"): Without proper governance, a data lake can become a "data swamp," where data is unorganized and unusable. Key considerations include:
•Security and Compliance: Implementing access control at folder/file level and encryption at rest.
•Metadata Management: Essential for understanding and locating data.
•Data Quality: Ensuring the reliability and accuracy of the data.
•Lifecycle Management: Managing data retention and archival policies.
Data Lake Zones: A well-designed Data Lake often organizes data into different zones based on its processing stage and quality:
•Transient Landing Zone: Temporary storage for regulatory and quality control (optional).
•Raw Zone: Original source data, ready for consumption, with metadata publicly available but limited data access.
•Trusted Zone: Standardized and enriched datasets, ready for consumption with appropriate role-based access.
•Curated/Refined Zone: Data transformed from the Trusted Zone for specific business requirements.
•Sandbox Zone: A playground for Data Scientists for ad-hoc exploratory use cases.
Data Processing Evolution: Historically, data warehouses used ETL (Extract, Transform, Load) where data was extracted from OLTP systems, transformed into an analysis-friendly schema, cleaned, and then loaded. More recently, this has evolved to ELT (Extract, Load, Transform), where data is loaded into the data lake/warehouse first, and transformations occur later.
Delta Lake: An open-source project that builds upon the Parquet format, adding crucial features like ACID transactions on cloud object storage, time travel, schema evolution, and DML (CREATE/UPDATE/INSERT/DELETE/MERGE) commands. It enables data warehousing functionality on cloud object storage through an ordered transaction log.

Prompt 3: 
- Explain the CAP theorem using a real-world example mentioned in the notes (e.g., coffee shop rewards)

Generated Outputs:
The CAP theorem states that a distributed system can only guarantee two out of three core properties at any given time: Consistency (C), Availability (A), and Partition Tolerance (P).
Here's an explanation of each component and the trade-offs, using the real-world example of an international coffee shop chain with a shared rewards program:
•Consistency (C): This ensures that all customers see the latest updates, regardless of their location. The trade-off is that it might sacrifice access during network issues to guarantee up-to-date data.
◦Coffee Shop Example: If a customer earns points in New York, they can immediately see their updated points balance when checking their account in Paris. Every time they check their points, they see the latest update, no matter where they are.
•Availability (A): This guarantees an "always-on" service, meaning customers can always access their points or services, even during network failures. The trade-off is that they might not always see the most recent data.
◦Coffee Shop Example: Even if the coffee shop's system has internal issues, such as network problems between locations, customers can still check their points or use their rewards without facing a service outage.
•Partition Tolerance (P): This refers to the system's resilience to network failures or disruptions between different locations or nodes. This property is generally considered "non-negotiable" for distributed systems to function effectively.
◦Coffee Shop Example: If the network connection between the New York and Paris locations is disrupted, both locations will still operate independently and continue to provide service to customers.
The Trade-Offs (You can only have two of the three):
The CAP theorem dictates that you must choose which two properties to prioritize:
•Prioritize Consistency and Partition Tolerance: If these two are chosen, during a network failure (a "partition" between nodes), customers might not be able to access their points at all locations. This sacrifices Availability because the system might become unavailable in certain areas to ensure data consistency.
•Prioritize Availability and Partition Tolerance: If these two are chosen, during a network issue, customers can still use their points and access the service. However, they might not see the most recent points balance if it was updated in another city. This sacrifices Consistency because the data might not be immediately synchronized across all locations.
•Prioritize Consistency and Availability: If these two were prioritized (ignoring Partition Tolerance), then if the network between nodes failed, the system overall would fail to operate. This means it would not be resilient to network disruptions, thus sacrificing Partition Tolerance.
