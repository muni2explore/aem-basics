
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


## OSGi

◇ Fundamental layer of AEM Stack

◇ OSGi application is a collection of bundles that interact using service interfaces

◇ OSGi bundles can contain compiled Java code, scripts, content that is to be loaded in the repository, and configuration or additional files

◇ Bundles may be independently developed and deployed

◇ OSGi Management Console:
http://localhost:4502/system/console


## Core vs Foundation Components

```mermaid
graph TD
   WCM[WCM Components] --> |Require v6.3| Core[Core Components]
   WCM --> Foundation[Foundation Components]
   Core --> CorePath[apps/core/wcm/components]
   Foundation --> FoundationPath[libs/foundation/components JSP based<br>/libs/wcm/foundation/components HTL and JS based]
```

# Core vs Foundation Components

| Feature | Core | Foundation |
|---------|------|------------|
| Markup | HTL | JSP code |
| Dialog Definition | Coral 3 | Coral2 + Classic UI |
| Apache License | Apache License | Proprietary of Adobe |
| Implementation | Java POJOs with Sling Models annotations | Implementation: JSP code |
| Delivery | Delivered in and through GitHub: https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components | Delivery is via QuickStart |
| Technology used | Sling Models, HTL, Touch UI etc. | JavaScript Use-API, JSP, Classic UI |