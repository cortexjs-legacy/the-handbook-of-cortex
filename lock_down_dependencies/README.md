# Lock down dependencies

In production, you always need to control exactly which versions of each dependency will be used when your package is installed, that's why `cortex-shrinkwrap` comes in.

By locking down the dependencies, run `cortex shrinkwrap` in the project root path, once the command finishes, a file called 'cortex-shrinkwrap.json' will be genenerated, it contains a dependency tree describing the exact version of each dependency.

when you run `cortex install`, if 'cortex-shrinkwrap.json' exists, it will be parsed to decide the required version of a dependency.
