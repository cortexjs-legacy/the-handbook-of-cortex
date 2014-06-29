# Deploy

Cortex doesn't put any constraint on how you depoy the static resources.

Here is some approaches we recommend:

### 1. for small project
Just serve the built result as static resources and use `facade` to load the module.

### 2. for company use
Usually in company you push code to a private code repositry with ci tools intergrated. You can add hooks on every push to inform the ci to publish that package to the registry and transfer it to the static resource server.
