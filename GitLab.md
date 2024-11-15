# GitLab

## CI Job Token

Every repository that has pushed a package in the registry needs to add the client repositories in the CI Job Token Allow List (Settings > CI/CD > Job token permissions).
This will permit the package manager to retrieve the resulting package during the execution of build pipelines of the client repositories.
