# Semantic versioning

Cortex fully support semantic version, thus making it trivial work to deliver a patched or bug fixed version without touching the code.

Open cortex.json, check the `dependencies` field:

```
"dependencies": {
    "jquery": "~1.9.2"
 }
 ```

When you install some dependency, by default the tilde operators is used, meaning "reasonably close to".

If you want to use a specifed version or define a different range, just edit the field and re-run `cortex install`. Cortex will ask for the registry and find the proper version.

For more Information about semantic version pattern, visit http://semver.org/.
