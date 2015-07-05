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

> **NOTE:** Transcluding HTTP links is not yet provided with hercule. A PR will
> be emitted in the next couple of days. So long you can use [this
> fork](https://github.com/MichaelHirn/hercule). Clone the repo and install
> hercule with `npm install -g /path/to/hercule/fork/clone`

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

## TODO

- Lay out a coherent file structure for this repository, which organizes the common
resources.
