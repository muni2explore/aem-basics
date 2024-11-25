# Client Libs


# Client-side Libraries in AEM - Problem and Solution

## The Problem - Traditional Inclusion
Standard way to include client-side libraries resulted in potential issues:

```html
<head>
    ...
    <script type="text/javascript" 
    src="/etc/clientlibs/granite/jquery/source/1.8.1/jquery-1.8.1.js"></script>
    ...
</head>
```

**Issue:** Multiple copies of the same JS library may be included in the final HTML output.

## The Solution - ClientLib Management

```mermaid
graph TD
    A[Client-Side Library Management] --> B[Repository Storage]
    A --> C[Resource Management]
    A --> D[Optimization]
    B[Repository Storage] --> E[cq:ClientLibraryFolder]
    C --> F[JavaScript Files]
    C --> G[CSS Files]
    D --> H[Dependency Management]
    D --> I[File Merging]
    D --> J[Content Minification]
```

### Key Features:
- Client-Side Library Folder for repository storage
- ClientLib manages JavaScript and CSS resources
- Handles:
  - Dependency management
  - File merging
  - Content minification
- Uses cq:ClientLibraryFolder node type
- Can be included via HTL or JSP in AEM

This approach provides better organization and optimization of client-side resources compared to traditional direct inclusion.


# How Client Libraries work?

```mermaid
graph TD
    A[cq:ClientLibraryFolder] --> B[Properties Configuration]
    B --> C[categories]
    B --> D[dependencies]
    B --> E[embed]
    A --> F[Content]
    F --> G[JS files]
    F --> H[CSS files]
    F --> I[Supporting files]
```

Each cq:ClientLibraryFolder is populated with:
- JS and/or CSS files 
- Supporting files
- Configuration properties:
  - categories
  - dependencies
  - embed

This structure allows for organized management and configuration of client-side resources in AEM.


# Properties of Client Libraries

## Key Properties
- **categories**: list of identifiers to publish a clientlib under
- **dependencies**: causes extra requests to other clientlibs (external "subscribe")
- **embed**: "aggregates" other clientlibs INTO the current clientlib (internal subscribe)

## Example Implementation

```mermaid
graph TD
   subgraph Dependencies
       depA["depA<br>categories=['depA']"]
       depB["depB<br>categories=['depB']"]
       depC["depC<br>categories=['depC']"]
   end
   
   subgraph Usage Libraries
       useA["useA<br>categories=['useA']<br>dependencies=['depA','depB']"]
       useB["useB<br>categories=['useB']<br>embed=['depB','depC']"]
   end
   
   useA --> depA
   useA --> depB
   useB -.->|embeds| depB
   useB -.->|embeds| depC
```

### Usage Scenarios:
1. When using "useA" (`<cq:includeClientLib categories="useA"/>`):
   - HTML requests: depA, depB, useA
   - Accessed via: /etc/clientlibs/depA.css etc.

2. When using "useB" (`<cq:includeClientLib categories="useB"/>`):
   - Single HTML request: useB
   - Contents: concatenation of depB, depC, useB


# Debugging Client Libraries

```mermaid
graph TB
    subgraph Debugging Tools
        A[Dump Libs] --> D[List all registered<br>client libraries]
        B[Test Output] --> E[View expected HTML<br>output by category]
        C[Dependencies Validation] --> F[Highlight missing<br>dependencies/embeds]
        G[Rebuild Client Libraries] --> H[Force rebuild/<br>invalidate cache]
    end
```

## Available Tools

1. **Dump Libs**
   - Purpose: Lists all client libraries registered in AEM
   - URL: `http://localhost:4502/libs/granite/ui/content/dumplibs.html`

2. **Test Output**
   - Purpose: Shows expected HTML output of clientlib includes by category
   - URL: `http://localhost:4502/libs/granite/ui/content/dumplibs.test.html`

3. **Libraries Dependencies Validation**
   - Purpose: Highlights missing dependencies or embedded categories
   - URL: `http://localhost:4502/libs/granite/ui/content/dumplibs.validate.html`

4. **Rebuild Client Libraries**
   - Purpose: Forces AEM to rebuild libraries or invalidate cache
   - Best Practices:
     - Particularly useful when developing with LESS
     - Generally more effective to invalidate caches and refresh versus full rebuild
   - URL: `http://localhost:4502/libs/granite/ui/content/dumplibs.rebuild.html`

# Using Client-side Libraries - The Solution

```mermaid
graph LR
    A[cq:ClientLibraryFolder] --> B[js.txt]
    A --> C[css.txt]
    B --> D[JS source files]
    C --> E[CSS source files]
    F[HTML Library Manager<br>cs:includeClientLib] --> D
    F --> E
```

## Client-Side Libraries Overview
- Client-Side Library Folder allows you to store client side code in the repository
- Client Library (or ClientLib) will manage all your JavaScript and CSS resources in your application
- Takes care of dependency management, merging files and minifying content
- A client-side library folder is a repository node of type cq:ClientLibraryFolder
- Use HTL or JSP to include Client-side Libraries in AEM

## ClientLib Components
- The JS and/or CSS source files to merge
- Resources that support CSS styles, such as image files
- One js.txt file - Use this file name to generate a JavaScript file
- One css.txt file - Use this file name to generate a Cascading Style Sheet

This shows how ClientLib manages and processes JS and CSS resources through the HTML Library Manager for efficient client-side resource delivery.