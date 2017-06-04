# registry-deploy-testenv

This is a clone of the Environment Registry deployment configuration (2016) release,
adapted to include API documentation and wireframe to support Environment Agency data standards.

This in turn makes it a slightly modified clone of `registry-config-base`

Should set upstream to enable changes to be pulled in:

    git remote add upstream git@github.com:UKGovLD/registry-config-base.git

N.B. Requires registry-core 1.2.0 or higher

## Installation

While this includes the `install` and `scripts` areas they are not used, this is deployed using a separate chef cookbook.

Directory | Role
---|---
`ldregistry` | A starting set of configuration files and templates which should be install in `/opt/ldregistry` on the target system. For details of the role of these files see [Configuration](https://github.com/UKGovLD/registry-core/wiki/Configuration)
`install` | Files used to configure the front end nginx proxy
`scripts` | Example installation scripts

## Customizations from Environment Registry

`data/data-standards.ttl` Definition for Data Standards collection, register in `/def` and set to Experimental.

`data/std-prefix.ttl` Definition for `std:` prefix corresponding to Data Standards code vocab. Register in `/system/prefixes`.

`data/owl-bulk-reg.ttl` Add OWL Ontology as a bulk upload type, register in `/system/bulkCollecitonTypes`.

