# Replication



 Author -> Publish 


 ##  Reverse Replication

 Publish -> Author

 ex. blog comments

 ## Replication Agent

 From author whenever we activate it keeps adding to bucket which is called Replication Queue (On Author). The publisher has listener which keeps checking the Author's queue and whenever it finds something it picks up and replicates itself.


```mermaid
 graph TD
    A[Home.html] --> B[Node created Home]
    B --> C[Properties]
    C --> D[Sling.resourceType] 
```



```mermaid
graph LR
    %% Adding a note at the top
    subgraph Process Flow
        note1[Processing is driven by URL of the user request]
        note2[Content to be displayed by the appropriate scripts]
    end

    %% Main flow
    A[URL] -->|Process| B[Content]
    B -->|Display| C[Properties + Script]

    %% Styling
    classDef default fill:#fff,stroke:#d46536,stroke-width:2px
    classDef notes fill:none,stroke:none
    class note1,note2 notes
```