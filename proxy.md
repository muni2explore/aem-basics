# Proxy Components

- Core components are hidden by default, you cannot use them directly.
- Core components are designed in such a way that it should be accessed using proxy components only. The advantage of adding one more layer of proxy components is that your core components will be as it is and you can refer to any version of core component just by changing sling:resourceSuperType to new version.


# Overlay/Override Components

Creating a custom component involves copying a foundation component to your project and modifying it based on requirements. For example:

- Source: `/libs/foundation/components/image`
- Destination: `/apps/testsite/components/image`

After copying, you can customize the component according to your needs. However, this approach has a significant drawback:

When upgrading AEM, if the original component at `/libs/foundation/components/image` is updated with new implementations, these changes won't automatically appear in your custom component at `/apps/testsite/components/image`. This means you'll need to manually update your custom component to incorporate any new changes from the foundation component.

This creates maintenance overhead as you need to track and manually implement any updates from the foundation components into your custom implementations.

# Extend Components

To create a custom component through extension:

1. Create all necessary nodes manually
2. Set the "sling:superResourceType" property to "/libs/foundation/components/image"

This approach allows you to inherit all features of the base image component. The key benefit is that even after AEM upgrades, your component will continue to inherit any new features or improvements made to the base image component, unlike with the overlay approach.

This is a more maintainable way to create custom components since it preserves the connection to the original component while allowing customization.


# Proxy Components vs Extend Components

Here's a comparison of both approaches:

## Proxy Components
- Used primarily with Core Components which are hidden by default
- Creates a proxy layer between core components and your implementation
- Version management is handled by changing sling:resourceSuperType to point to new version
- Ideal for using Core Components with minimal customization
- Key benefit: Easy version management of core components

## Extend Components
- Used with Foundation Components
- Creates custom components by manually setting up nodes and sling:superResourceType
- Directly inherits features from the base component
- Maintains inheritance even after AEM upgrades
- Key benefit: Combines custom functionality while keeping base component features

Key Differences:
1. Usage: Proxy Components are specifically for Core Components, while Extend Components are used with Foundation Components
2. Implementation: Proxy is a lighter wrapper, while Extend requires manual node creation
3. Version Management: Proxy makes version changes easier through sling:resourceSuperType updates
4. Default Access: Core Components (used with Proxy) are hidden by default, Foundation Components (used with Extend) are directly accessible