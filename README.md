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

Data for customizations is in `data` directory.

Data file | Role | Action
---|---|---
`std-prefix.ttl` | Definition for `std:` prefix corresponding to Data Standards code vocab. | Register in `/system/prefixes`.
`owl-bulk-reg.ttl` | Add OWL Ontology as a bulk upload type | Register in `/system/bulkCollecitonTypes`.
`data-standards.ttl` | Definition for Data Standards collection | Register in `/def` and set status to Experimental.
`std-vocab.tll` | Draft vocabulary for EA Data Standards data model | Register in `/def/data-standards` and set register and content to Experimental.
