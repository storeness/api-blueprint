# API Blueprint

This repository provides common resources for modeling micro services for the
API with the [apiblueprint](https://github.com/apiaryio/api-blueprint) standard.

At the moment the API-Blueprint specification is not in a state, in which a DRY
blueprint could be written - especially not for different micro services that
share similar origins.

To compensate this problem, we make use of
[hercule](https://github.com/jamesramsay/hercule), a very easy to use tool, for 
`Markdown` transclusions. This allows us, to share resources like 
`Schemas`, `Data Structures`, `(Error) Responses`, `Attributes`, `Actions`, ...
between all our micro services, which keeps things DRY and consistent.
This repository is the place where these resources live and from which they can
be transcluded into the different service blueprints.

> **NOTE:** For transcluding the files into the finished API Blueprint we make
> use of *default* values, which are at the moment not a part of the official
> hercule project. But until a PR got created and the code merged into the
> official project you can use [this fork](https://github.com/MichaelHirn/hercule). Clone the repo and install
> hercule with `npm install -g /path/to/hercule/fork/clone`

## How does it work?

In order to gain all the benefits (higher DRYness, multi-file support,
increased readability) we add one simple step, that can be completely automated.  

You can see an working example inside the `examples` directory.  

The workflow looks as followed:

(1) **Write your blueprint**  
    *Thanks to resource transcluding, this step becomes quicker and easier then
ever. There sunk also some thoughts into how to lay out the blueprint as the
process described by apiary is not quite efficient. With the new process, one
has only to write descriptions of resources and actions and model the data
structure. All the other parts are already developed and can simply transcluded
to gain a coherent API documentation.*  

(2) **Transclude the file with `hercule`**  
    *All the specified ressources get transcluded and the final api blueprint
generated, with just one simple command: `hercule service-blueprint.md -o
apiary.apib`*  

(3) **Finished docs and api blueprint**  
    *To validate and print the finished docs use [drafter](https://github.com/apiaryio/drafter) and the [apiary client](https://github.com/apiaryio/apiary-client)*


## Why?

Following through on the api blueprint standard leads to many desired outputs:

- Great documentation of APIs which makes it easy for everyone to join,
  integrate and build upon.
- Simplifies testing, as the optional Schema is a powerful and continuous tool
  to test responses without overhead on the code site.
- Makes it easy provide a consistent user experience across many micro services.

API blueprint is a step in the right direction and with this repository (that
serves as the collective resource hub) and `hercule`s power, we gain the
promised benefits already.
