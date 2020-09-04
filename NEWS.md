# circle 0.5.0.9002

- Copy over GitHub auth and SSH helpers from {travis}
- print informative message when creating a user key errors with status code 500


# circle 0.5.0.9001

* `*_env_var()`: Use owner info instead of user info to query repo

# circle 0.5.0

## Major

- Add new authentication mechanism: `browse_circle_token()` to to query the API token and store it in an env variable `R_CIRCLE` as an alternative method to store it in `~/.circleci/cli.yml`
- Remove `auth_travis()`
- Rename `circleHTTP()` to `circle()`
- add `github_repo()`
- `get_pipelines()`, `get_workflows()` and `get_jobs()` are now formatted as class `circle_builds`, `circle_collection()` and have a somewhat pretty print output
- `*_checkout_key()`: Optimize printer, catch errors, add info messages, add test
- make `get_pipelines()`, `get_workflows()` and `get_jobs()` work with API v2
- rename `list_artifacts()` -> `get_build_artifacts()`

## Bugfixes

- Pipelines without a workflow ID caused `get_builds()` to error. Now pipelines without a workflow ID are removed internally before continuing. 
- setting env vars now works
- make `create_checkout_key()` work with API v2

# circle 0.4.0

- update "cache" function with new user/owner logic from v0.3.0
- new `has_checkout_key()` to check if a specific checkout key exists in the project

# circle 0.3.0

- Rename argument `project` to `repo` to stay consistent with _travis_ pkg.

- Add Github helper functions to easily query owners and users for the repository operating on. This change requires the _git2r_ package from now on.

# circle 0.2.0

- Fix `api_version` in `create_ssh_key()`
- rename `ssh_key*` functions to `checkout_key*`
- `create_checkout_key()` change default for arg `type` from "github-user-key" to "deploy-key"
- add argument `encode` to `circleHTTP()`
- add `use_circle_deploy()`

# circleci 0.1.0

* First working version
