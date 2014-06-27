# Semantic versioning

Cortex owns fully support for sementic version.

Open cortex.json, you will find the dependency field:

```
"dependencies": {
    "jquery": "~1.9.2"
 }
 ```

When you install some dependency, by default the tilde operators is used, meaning "reasonably close to".

If you want to use a specifed version or define a different range, just edit the field and re-run `cortex install`. Cortex will ask for the registry and find the proper version.

For more Info about semantic version pattern, visit http://semver.org/
