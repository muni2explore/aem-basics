
# Dialog va cq:Dialog

- Dialog (Classic UI)
- cq:Dialog (Touch UI)

## Key Concepts

- EXTJS Framework - Dialog
- CORAL UI Framework - cqDialog
- Sightly: HTML templating language, introduced with AEM 6.0


## Coral UI

- Implementation of Adobe's visual style for touch-enabled UI
- Set of CSS and JS files designed and built for Adobe Cloud products
- Provides a wide range of HTML components pre developed for your website like:
  - buttons
  - navigation bar
  - toolbar
  - tables
  - grid
  - dialogs
  etc.
- Saves your time from developing the components so that you can focus more on your product.


## Coral UI Architecture

Collection of building blocks for developing web applications, structured in layers:

1. Utility Library (glue/plumbing)
   - Top level utilities for application development

2. Widgets
   - Higher level UI building blocks

3. Element Plugins
   - Handles behavioral aspects of components

4. HTML Elements
   - Base layer providing look and feel foundations

This layered architecture provides a comprehensive framework for building web applications, with each layer serving a specific purpose in the development stack.

| Layer | Purpose |
|-------|----------|
| Utility Library | (glue / plumbing) |
| Widgets | (higher level UI building blocks) |
| Element Plugins | (behavior) |
| HTML Elements | (look and feel) |

The table represents the layered architecture of Coral UI, showing each component's role in building web applications, from base HTML elements up to utility functions.



# Coral UI Components

## HTML Elements
- Provide basic UI elements with a common look-and-feel
- Implemented using HTML tags with Styles

## Element Plug-ins
- Provide dynamic behaviour for HTML Elements
- Provide custom layouts
- Perform form validation
- Implemented using jQuery plug-in

## Widgets
- A widget combines one or more basic elements with a JavaScript plug-in to form "higher level" UI elements
- Triggering and handling events
- jQuery plug-in + HTML markup

## Utility Library
- Collection of JavaScript helper plug-ins and functions
- Used for Client-side templates


# Granite UI

- Provides a foundation UI framework provided by Adobe to develop modular and reusable components
- Consists of Client-side and Server-side
- Provides a default standardized UI
- Designed for both mobile and desktop devices

This framework serves as Adobe's foundation for creating consistent, responsive UI components that work across different platforms and devices.

# Granite UI

Implements component libraries intended for building content-centric web applications, consisting of:

| Component Type | Purpose |
|----------------|----------|
| granite.components | (content driven components) |
| administration components | (building blocks for administration UIs) |

Granite UI provides a layered approach with specific components for both content management and administrative interfaces.

# Granite UI - Building Blocks

## Foundation Components
- Provide the basic building blocks needed for building any UI
- Examples: Buttons, Hyperlink etc.
- Components can be found in `/libs/granite/ui/components/foundation`
- Libraries can be used or extended by other libraries

## Administration Components
- Unified look-and-feel for administration applications
- Examples: Global Navigation Bar, Search Panel etc.
- Implemented using foundation components 

This two-tier structure allows for:
1. Basic UI elements through Foundation Components
2. Consistent admin interfaces through Administration Components built on top of the foundation


# Coral UI vs Granite UI

## Coral UI
- Implementation of Adobe's visual style for the touch-enabled UI
- Provides everything your product/project/web application needs to adopt the UI visual style

## Granite UI
- Components are built with Coral UI

The key difference is that Coral UI provides the visual style and UI components, while Granite UI uses these Coral UI components as building blocks for creating more complex functionality and administrative interfaces.

Think of it as:
- Coral UI = Visual Framework & UI Components
- Granite UI = Implementation using Coral UI components