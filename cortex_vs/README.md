# Cortex vs *

## 1. Component

Cortex embraces the same philosophy as Component does, that is, a package, or called component, should not just consists of javascript, it should be a self contained unit which has css, images, fonts, templates, and etc. Cortex deals with all these kinds of resources well, thus making it esay to develop and share reusable web component.

Cortex's package manangement system and cli tools are much more like NPM, which most of our front end developers are quite familiar with, so it saves the study time to make your hands dirty.

Meanwhile, Cortex makes lots of efforts on handling dependency versions, it could analyze the dependency tree on-the-fly, allowing multiple versions of the same dependencies, also making it possible to push a specified version without touching the exsiting code(this is quite useful when you want to push a bug fix version to all its dependents).

Another major difference between Component and Cortex is that Component uses Github as its registry while Cortex uses couchdb(much more like npm). Although Github is so fancy that all our developers loves it so much, Establishing a private registry, which most company usually does, will require more efforts. In contrast, Cortex's registry could be easily installed, and with couchdb's replication system, you can synchronize packages from public registry without an additional sync tool.

