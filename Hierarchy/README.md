# Component Hierarchy and Inheritance

## 3 Hierarchies
- Resource Type Hierarchy
  This is used to extend components using the property sling:resourceSuperType. This enables the component to inherit. For example a text component will inherit various attributes from the standard component.
  
  What is inherited:
  - scripts (resolved by Sling)
  - Dialogs
  - descriptions (including thumbnail images, icons, etc)

## Container Hierarchy
  This is used to populate configuration settings to the child component and is most commonly used in a parsys scenario. For example, configuration settings for the edit bar buttons, control set layout (editbars, rollover), dialog layout (inline, floating) can be defined on the parent component and propagated to the child components.
  Configuration settings (related to edit functionality) in cq:editConfig and cq:childEditConfig are propagated.

## Include Hierarchy
  This is imposed at runtime by the sequence of includes.