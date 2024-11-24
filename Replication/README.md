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

Let me extract the text content from the image:

## URL to Content and Scripts

Key Points:
◇ Content path extracted from request (URL) to locate resource
◇ When located sling resource type is extracted
◇ Locate the script for rendering the content

Path shown in request box:
`../content/corporate/jobs/developer.html (Request)`

Repository Structure:
```
/apps
/hr
/jobs
  /jobs.POST.esp
  /jobs.esp  
  /jobs.pdf.esp
  /jobs.print.esp
```

Content Structure:
```
/content
/corporate
/jobs
/developer.html
jcr:content:
  sling:resourceType = hr/jobs
```

Final Output:
Rendered Content

The diagram shows the flow from a URL request through content resolution in the repository to final rendered content, with repository paths in orange/brown and content paths in blue colors.

```mermaid
graph TD
    A["../content/corporate/jobs/developer.html (Request)"]

    subgraph "Repository"
        B["/apps"]
        C["/hr"]
        D["/jobs"]
        D1["/jobs.POST.esp"]
        D2["/jobs.esp"]
        D3["/jobs.pdf.esp"]
        D4["/jobs.print.esp"]

        B --> C
        C --> D
        D --> D1
        D --> D2
        D --> D3
        D --> D4
    end

    subgraph "Content Path"
        E["/content"]
        F["/corporate"]
        G["/jobs"]
        H["/developer.html"]
        I["jcr:content:<br>sling:resourceType = hr/jobs"]

        E --> F
        F --> G
        G --> H
        H --> I
    end

    J["Rendered Content"]
    I --> J
```