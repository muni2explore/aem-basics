A **Java Content Repository (JCR)** is a specification for a hierarchical content repository API in Java. It is not tied to any specific storage mechanism; the way data is stored depends on the specific JCR-compliant implementation. Here’s a breakdown of how JCR stores data conceptually and physically:

### **Conceptual Data Storage**
JCR is designed to store data in a hierarchical structure similar to a filesystem:
- **Nodes**: Represent items in the repository, such as folders or files.
- **Properties**: Contain metadata or data values associated with nodes.
- **Tree Structure**: Data is stored in a tree-like hierarchy, where each node can have child nodes and properties.

### **Physical Data Storage**
The actual storage mechanism depends on the specific implementation of JCR. Some popular JCR-compliant implementations are **Apache Jackrabbit** and **Magnolia CMS**, which may use one or more of the following approaches:

1. **Flat Files**:
   - Data is serialized and stored as flat files, often in formats like JSON or XML.
   - Jackrabbit, for example, can use the file system for storage by storing node structures and properties in files.

2. **Relational Databases**:
   - Some implementations use relational databases (e.g., MySQL, PostgreSQL) to store data.
   - Node hierarchies are mapped to tables, with rows representing nodes and columns representing properties.

3. **NoSQL Databases**:
   - JCR implementations can also use NoSQL databases (e.g., MongoDB) to store data for better scalability and performance in some use cases.

4. **In-Memory Databases**:
   - For testing or lightweight use, data can be stored in-memory, without persistence.

5. **Custom Pluggable Backends**:
   - JCR implementations may allow users to plug in their custom storage backends to meet specific needs.

### **Example: Apache Jackrabbit Storage Mechanism**
- Jackrabbit uses a **Persistence Manager** to handle storage.
- The **default setup** often involves a combination of:
  - A **local filesystem** for binaries (e.g., images, videos).
  - A **relational database** or **file-based storage** for metadata and the node hierarchy.

### Summary
JCR doesn't mandate how data must be stored but provides an abstraction that implementations follow. Whether data is stored in flat files, databases, or other systems depends on the specific JCR implementation and configuration choices.