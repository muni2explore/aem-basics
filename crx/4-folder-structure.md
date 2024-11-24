# CRXDE - Folder Structure

- `/apps` - stores all custom templates, components and definitions related to your website. When you inherit from foundation components, it is done from the libs folder. Always copy the contents from the libs folder to apps folder and then modify in apps folder
- `/libs` - stores all library and definitions that belong to AEM code. Referred to as foundation components. Avoid making any modifications to any component in libs
- `/content` - all the content of your website is stored here
- `/conf` - all configurations for your site
- `/etc` - all resources related to utilities and tools  
- `/home` - all information related to users and groups
- `/var` - files that change and updated by the system such as audit logs
- `/tmp` - serves as temporary working area