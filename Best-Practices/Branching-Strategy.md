# DevRel Branching Strategy

We always work on three branches in all repositories:

### Feature & bugfix branches

We always work in feature/bugfix branches on any new additions or updates.
These branches are merged **only** into `staging` and always through a PR. 

**PR Merging Strategy: ** Squash and merge

### Staging branch

The `staging` branch is our pre-production branch. It should never be behind `main` and 
it can only ever PR into the `main` branch. 

**PR Merging Strategy: ** Normal merge (merge commit)


### Main branch

The `main` branch is our production branch. It should only ever be PR'ed into from the `staging` branch.
No commits should ever occur directly to the `main` branch on a repository where a `staging` branch exists. 

