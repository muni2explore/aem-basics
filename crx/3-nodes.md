# CRXDE - Nodes and Properties

## Nodes
- Provide the structure. Have parent and child nodes which are represented with paths
- Have a type. The node type sets rules about what kind of properties and child nodes a node can have
- Example: a node of type cq:Template must always have a child node named jcr:content of type cq:PageContent
- Any number of properties for storing information – Single or multi-valued (like an array)

## Properties
- Store the data. Have name and a value


# Common JCR Node types

| Node Type | Description |
|-----------|-------------|
| nt:file | Represents a file, as in a filesystem |
| nt:folder | Represents a folder, as in a filesystem |
| nt:unstructured | Used to store unstructured content<br>Allows any combination of properties<br>Commonly used for touch-enables UI dialogs |


# Common AEM Node types

| Node Type | Description |
|-----------|-------------|
| cq:Page | Stores content and properties for a page in a website |
| cq:Template | Defines a Template used to create Pages |
| cq:ClientLibraryFolder | Defines a library of Client-side JavaScript CSS |
| cq:EditConfig | Defines editing configuration for a component including drag and drop and in-place editing |