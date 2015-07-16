# Example API Blueprint

This is an example to show you how you might structure your API blueprint, for
a streamlined and DRY experience while writing your API Blueprint and testing it
with [Dredd](https://github.com/apiaryio/dredd).  

For this example we create a sample API blueprint for our imagined **Door API**.  

This structure might actually be a good place to start your real API blueprint
from.  

## Short guidelines

- The atomic elements of a blueprint are the
  [MSON](https://github.com/apiaryio/mson) defined Attributes.
- Write those atomic elements with
  [hercule](https://github.com/jamesramsay/hercule) in mind, as this makes them
reusable and keeps the blueprint super tidy and amazingly fast editable. Check
out the files at `data-structures/{resource-name}/items/*`.
- One atomic element per file. This concept should be reused for every higher
  order elements. Just browse the directory, this makes everything clear.
- Create your main API blueprint file in the root directory of `blueprint`.
- The response/request Attributes should match the name of the Action to which it belongs. For more information see `resources/door.md`.
- **About _default_**: MSON allows default values, which seem to have the same behavior as sample values. But a default value might be handy, especially for requests, with optional parameters. So to tell the user what happens if an optional value is not defined, we should include this explicitly into the description. This is because we have some problems to transclude this with hercule on the fly. A possible solution might look like this (pretty ugly though) `[:Object Item Id](path/to/id.md default:"- Default\n  - \`default value\``.

## Generate the finished API Blueprint

To generate a complete and valid blueprint for all the files inside the
`blueprint` directory, run the following command (inside of this directory
"`examples`")

```
hercule blueprint/door.md -o apiary.apib
```
