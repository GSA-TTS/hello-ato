# hello-ato
A TTS-flavored [Copier](https://copier.readthedocs.io/) template for an ATO-ready system

## Why this project

This template supports scaffolding and maintaining a federal system, configured to the local tastes of TTS, ready for ATO from day one. It accomplishes this by composing [other `GSA-TTS/hello-*` templates](https://github.com/orgs/GSA-TTS/repositories?type=all&q=hello-) for managing various attributes of the system.

## Features

### Implemented

* Manages multiple ([Astro](https://github.com/GSA-TTS/hello-terraform-cloudgov)) applications within the boundary
* Deploys to [cloud.gov using Terraform](https://github.com/GSA-TTS/hello-terraform-cloudgov)
  * Deploy in personal sandboxes or to fully-managed spaces

### Planned (_help wanted!_ 😘 )

* Automation for CI/CD
  * GitHub Actions 
  * GitLab CI 
* Turnkey capabilities 
  * Workflow service (via SpiffWorkflow)
  * Backend service (via Supabase)
* Proxies egress traffic
* Drains logs to off-site ELPs
  * ELK (ingested from S3 bucket)
  * New Relic
* Generates compliance docs
  * Scaffolds OSCAL 
  * Auto-generates Mermaid diagrams
* Captures auditing artifacts (using auditree)
* Moar application frameworks
  * Drupal
  * Django
  * Rails

## Requirements
- [uv](https://docs.astral.sh/uv/getting-started/installation/) (for running Copier)
- [git](https://git-scm.com/)

## Usage

### Creating a system
1. [Install uv](https://docs.astral.sh/uv/getting-started/installation/) (if you haven't already)
2. Run copier...\
  ...from your local clone of the repository:
   ```sh
   uvx copier copy --trust ./hello-ato <destination-folder>
   ```
   ...or directly from the repository on GitHub:
   ```sh
   uvx copier copy --trust gh:GSA-TTS/hello-ato <destination-folder>
   ```
3. Name the apps in your system

4. Answer questions about the apps as needed. If you don't know the answer right then, just accept the defaults. You can always update the app with later with different answers.

Follow instructions in the README.md in the destination folder to work with the new system.

### Updating the application later

If you'd like to...

- change your answers or 
- incorporate improvements made after you copied this template

...you can run the Copier `update` command: 

1. Make sure that your destination folder contains no uncommitted changes 
2. Update your destination folder from the most recently-tagged version of the template:
    ```
    uvx copier update --trust <destination-folder>
    ```
   If necessary, you can specify a specific tag or gitref:
    ```
    uvx copier update --trust -r GITREF <destination-folder>
    ```

To learn how updating works and what additional options are available, read [the Copier `update` documentation](https://copier.readthedocs.io/en/stable/updating/) .

## Directory Structure
- `templates/`: Template for the monorepo

## Developing

To ensure that copies reflect your local changes to the template, specify the HEAD revision on the command-line. For example...

When copying:
```
uvx copier copy --trust -r HEAD <template-folder> <destination-folder>
```

When recopying:

```
uvx copier recopy --trust -r HEAD <destination-folder>
```

When updating: 

```
uvx copier update --trust -r HEAD <destination-folder>
```

There's [more information about this](https://copier.readthedocs.io/en/stable/faq/#while-developing-why-the-template-doesnt-include-dirty-changes) in the Copier docs.

## Contributing

See [CONTRIBUTING](CONTRIBUTING.md) for additional information.

## Public domain

This project is in the worldwide [public domain](LICENSE.md). As stated in [CONTRIBUTING](CONTRIBUTING.md):

> This project is in the public domain within the United States, and copyright and related rights in the work worldwide are waived through the [CC0 1.0 Universal public domain dedication](https://creativecommons.org/publicdomain/zero/1.0/).
>
> All contributions to this project will be released under the CC0 dedication. By submitting a pull request, you are agreeing to comply with this waiver of copyright interest.

