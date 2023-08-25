# PDK custom Templates

This forke of puppetlabs/pdk-templates has been create of the need to manage again a `.gitlab-ci.yml` for private maintained repos on a non public git server. It also contain dummy fles to workaround puppetlabs/pdk#924 to remove the dropped files of puppetlabs/pdk-templates#510 on every repo.

The community is welcome to use this forge as they wish, but at their own risk!  Both puppetlabs and pixelpark do not guarantee any support for that forge.

## Basic Usage

See [puppetlabs/pdk-templates](https://github.com/puppetlabs/pdk-templates) and [puppetlabs/pdk](https://github.com/puppetlabs/pdk)

### Use this forge as template for pdk

```bash
pdk convert pdk convert --template-url=https://github.com/pixelpark/pdk-custom-templates --template-ref=main
```

## Possible overrides / Changes

### .gitlab-ci.yml

> A workflow CI/CD file for gitlab that runs puppet validation and spec tests

> **Note**: There is NO support for litmus and breaker jobs. Please define your own via the `custom_jobs` key.

> **Note**: The usage `default` keyword has been removed. Update your `custom_jobs` when you did depend on it.

### .github/workflows/*

> **Note**: They are set to `delete: true` which will enforced removed and not simple unmange them.
> In case you are on GitHub use
>
> ```yaml
> delete: false
> unmanage: true
> ```
>
> to ensure that they are not deleted when needed.

### Rakefile

Added `linter_fail_on_warnings: true`.

### .gitignore

Added:

- '*.bak'
- '.rbenv*'
- '.rvmrc*'
- '.ruby-*'

### Addintional files that will be removed

- .devcontainer/Dockerfile
- .devcontainer/README.md
- .devcontainer/devcontainer.json
- .editorconfig
- .gitpod.Dockerfile
- .gitpot.yml
- .travis.yml
- appveyor.yml
