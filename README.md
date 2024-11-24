
## AEM Technology Stack 


```mermaid
graph TD
    A[AEM] --> B[Apache Sling]
    B --> C["Java Content Repository<br>(CRX, Apache Jackrabbit)"]
    C --> D["OSGi<br>(Apache Felix)"]
    
    %% Styling to match image colors
    classDef blue fill:#E6E6FA,stroke:#666
    classDef orange fill:#FFDAB9,stroke:#666
    
    class A,C blue
    class B,D orange
```


Let me extract the text information from the Java Content Repository image:


## Java Content Repository


◇ JCR: Java Content Repository

◇ JackRabbit framework used to build JCR

◇ Query language called XPATH for retrieving information from XML. AEM is internally using XPATH to fetch the information

◇ Two storage implementations available: TAR and Mongo DB

◇ Mongo DB for high performance & clustered applications and TAR used by default

