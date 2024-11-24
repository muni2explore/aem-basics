# Basics

- AEM components built using Sling, Web Application Framework
- AEM components are (usually) located under:
  HTL: /libs/wcm/foundation/components
  JSP: /libs/foundation/components
- Project/Site specific components are (usually) located under:
  /apps/<myApp>/components
- AEM standard components are defined as cq:Component and have key elements: jcr properties, Resources and Scripts
- Properties also include: jcr:title, jcr:description and sling:resourceSuperType (path of inheritance when extending a component)

# Dialogs and Design Dialogs

- Dialogs are a key element of your component as they provide an interface for authors to configure and provide input to that component
- Use cq:dialog for Touch-enabled UI and dialog for Classic UI
- Design dialogs are very similar to the dialogs used to edit and configure content, but they provide the interface for authors to configure and provide design details for that component.