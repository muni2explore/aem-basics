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