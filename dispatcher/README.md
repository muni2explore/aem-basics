## Dispatcher

◇ Dispatcher is AEM's caching and/or load balancing tool.

◇ Installed and configured on web server

◇ Protects your AEM server from attack

◇ Provides Security as which URLs are accessible or filtered

◇ Provides load balancing like which requests to be forwarded to the application server or Publisher

◇ Provide Caching of web pages produced by Publisher instance to improve performance


```mermaid
graph LR
    P1[Publish] --> D
    P2[Publish] --> D
    P3[Publish] --> D
    
    subgraph Web Server
        D[Dispatcher] <--> S[Static HTML]
    end
    
    B[Browser] --> D
    D --> B

    %% Styling
    classDef publish fill:#f4a460,stroke:#000
    classDef dispatcher fill:#90EE90,stroke:#000
    classDef static fill:#87CEEB,stroke:#000
    classDef browser fill:#B0C4DE,stroke:#000
    classDef webserver fill:#D3D3D3,stroke:#000
    
    class P1,P2,P3 publish
    class D dispatcher
    class S static
    class B browser
```