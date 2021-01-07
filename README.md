<!-- badges: start -->

[![tic](https://github.com/ropenscilabs/circle/workflows/tic/badge.svg?branch=main)](https://github.com/ropenscilabs/circle/actions)
[![CircleCI](https://img.shields.io/circleci/build/gh/ropenscilabs/circle/main?label=Linux&logo=circle&logoColor=green&style=flat-square)](https://circleci.com/gh/ropenscilabs/circle)
[![codecov](https://codecov.io/gh/ropenscilabs/circle/branch/main/graph/badge.svg)](https://codecov.io/gh/ropenscilabs/circle)
[![Lifecycle:maturing](https://img.shields.io/badge/lifecycle-maturing-blue.svg)](https://www.tidyverse.org/lifecycle/#maturing)

<!-- badges: end -->

# circle

R client package for the Continuous Integration (CI) provider 'Circle CI'.
[Circle CI](https://circleci.com/) stands in line with [GitHub Actions](https://github.com/features/actions), [Travis CI](https://www.travis-ci.com/), [AppVeyor](https://ci.appveyor.com/login) and many more CI providers.
[Circle CI](https://circleci.com/) heavily relies on Docker containers for runner execution.

This package aims to execute tasks such as build restarts, log queries or setting environment variables for the CI service provider [Circle CI](https://circleci.com/) from within R.
It also simplifies the setup process for build deployments via `use_circle_deploy()`.
All functionality relies on calls to the Circle CI REST API.

There are two ways to use this package:

- Via the high-level functions of this package wrapping common API calls
  - `get_pipelines()`
  - `get_checkout_keys()`
  - `set_env_var()`
  - etc.
- Via direct API calls through the workhorse function `circle()`

{circle} does not come with an option to setup Circle CI YAML files.
Please see the related [{tic}](https://github.com/ropensci/tic) package for such functionality and more CI workflow related tools.
{circle} aims to provide a handy and flexible high-level interface to the [Circle CI API](https://circleci.com/docs/api/v2/) without shipping opinionated workflow functionality.

## API versions

All functionality uses the Circle CI [API v2](https://github.com/CircleCI-Public/api-preview-docs) which follows the **pipelines** -> **workflows** -> **jobs** approach.
This API version is still in beta and might undergo some changes in the near future.

Some functions/endpoints can also be used via API versions v1.1 and v1 by setting the `api_version` argument.
However, this will only work if the respective API endpoint is available for the chosen API version.
Usually, there should be no need in practice to fall back to API version < 2.

For more information on the differences between the [Circle CI API](https://circleci.com/docs/api/v2/) versions, have a look at the [document explaining changes between v1.1 and v2](https://github.com/CircleCI-Public/api-preview-docs/blob/master/docs/api-changes.md).

## Installation

Development Version:

```r
remotes::install_github("ropenscilabs/circle")
```

## Get Started

See the [Getting Started](https://ropenscilabs.github.io/circle/articles/circle.html) vignette for an introduction.

## Note to Developers

This packages relies on private API keys for local testing.
See [CONTRIBUTING.md#testing-the-package](https://github.com/ropenscilabs/circle/blob/main/.github/CONTRIBUTING.md#testing-the-package) for detailed instructions.

# Acknowledgments

This package was inspired by the work of [Thomas J. Leeper](https://github.com/leeper) on the (discontinued) [cloudyr/circleci](https://github.com/cloudyr/circleci) package and by the (archived) [ropenscilabs/travis](https://github.com/ropenscilabs/travis) package.
