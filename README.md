# Approved third-party GitHub Actions for D2L

All third-party authored GitHub Actions at D2L have to be approved.
We mirror the repos into independent branches of [Brightspace/third-party-actions](https://github.com/brightspace/third-party-actions).

## Usage

Instead of using third-party actions directly, like this:

```yaml
uses: actions/checkout@v2
```

Use the mirrors from this repo, like this:

```yaml
- uses: Brightspace/third-party-actions@actions/checkout
```

There is no `@v2` (etc.) when using this repo.
We try to stick to a consistent version of each action across our org (configured and maintained by Dependabot in [third-party-actions-config](https://github.com/Brightspace/third-party-actions-config).

## Available actions

Here's what's available so far:

Repository | Description
-----------|------------
[NuGet/setup-nuget](https://github.com/Brightspace/third-party-actions/tree/NuGet/setup-nuget) | Official NuGet.exe setup action that supports cross-platform installation of specific NuGet.exe versions.
[actions/cache](https://github.com/Brightspace/third-party-actions/tree/actions/cache) | Cache artifacts like dependencies and build outputs to improve workflow execution time
[actions/checkout](https://github.com/Brightspace/third-party-actions/tree/actions/checkout) | Checkout a Git repository at a particular version
[actions/github-script](https://github.com/Brightspace/third-party-actions/tree/actions/github-script) | Run simple scripts using the GitHub client
[actions/labeler](https://github.com/Brightspace/third-party-actions/tree/actions/labeler) | Label pull requests by files altered
[actions/setup-dotnet](https://github.com/Brightspace/third-party-actions/tree/actions/setup-dotnet) | Used to build and publish .NET source. Set up a specific version of the .NET and authentication to private NuGet repository
[actions/setup-go](https://github.com/Brightspace/third-party-actions/tree/actions/setup-go) | **DEPRECATED** Setup a Go environment and add it to the PATH
[actions/setup-java](https://github.com/Brightspace/third-party-actions/tree/actions/setup-java) | Set up a specific version of the Java JDK and add the
[actions/setup-node](https://github.com/Brightspace/third-party-actions/tree/actions/setup-node) | Setup a Node.js environment by adding problem matchers and optionally downloading and adding it to the PATH.
[actions/setup-python](https://github.com/Brightspace/third-party-actions/tree/actions/setup-python) | Set up a specific version of Python and add the command-line tools to the PATH.
[actions/stale](https://github.com/Brightspace/third-party-actions/tree/actions/stale) | Close issues and pull requests with no recent activity
[amannn/action-semantic-pull-request](https://github.com/Brightspace/third-party-actions/tree/amannn/action-semantic-pull-request) | Ensure your PR title matches the Conventional Commits spec (https://www.conventionalcommits.org/).
[aws-actions/amazon-ecr-login](https://github.com/Brightspace/third-party-actions/tree/aws-actions/amazon-ecr-login) | Logs in the local Docker client to one or more Amazon ECR Private registries or an Amazon ECR Public registry
[aws-actions/amazon-ecs-deploy-task-definition](https://github.com/Brightspace/third-party-actions/tree/aws-actions/amazon-ecs-deploy-task-definition) | Registers an Amazon ECS task definition, and deploys it to an ECS service
[aws-actions/amazon-ecs-render-task-definition](https://github.com/Brightspace/third-party-actions/tree/aws-actions/amazon-ecs-render-task-definition) | Inserts a container image URI into a container definition in an Amazon ECS task definition JSON file, creating a new file.
[aws-actions/configure-aws-credentials](https://github.com/Brightspace/third-party-actions/tree/aws-actions/configure-aws-credentials) | Configure AWS credential and region environment variables for use with the AWS CLI and AWS SDKs
[cemkiy/action-slacker](https://github.com/Brightspace/third-party-actions/tree/cemkiy/action-slacker) | Send slack messages with attachments, auto username, branch and other actions
[codelytv/pr-size-labeler](https://github.com/Brightspace/third-party-actions/tree/codelytv/pr-size-labeler) | Label a PR based on the amount of changes
[coverallsapp/github-action](https://github.com/Brightspace/third-party-actions/tree/coverallsapp/github-action) | Send test coverage data to Coveralls.io for analysis, change tracking, and notifications.
[dorny/paths-filter](https://github.com/Brightspace/third-party-actions/tree/dorny/paths-filter) | Execute your workflow steps only if relevant files are modified.
[hashicorp/packer-github-actions](https://github.com/Brightspace/third-party-actions/tree/hashicorp/packer-github-actions) | Run Packer commands
[hashicorp/setup-terraform](https://github.com/Brightspace/third-party-actions/tree/hashicorp/setup-terraform) | Sets up Terraform CLI in your GitHub Actions workflow.
[hashicorp/terraform-github-actions](https://github.com/Brightspace/third-party-actions/tree/hashicorp/terraform-github-actions) | **DEPRECATED** Runs Terraform commands via GitHub Actions.
[hmarr/auto-approve-action](https://github.com/Brightspace/third-party-actions/tree/hmarr/auto-approve-action) | Automatically approve pull requests

## Adding more

This repo is generated and maintained by [Brightspace/third-party-actions-config](https://github.com/Brightspace/third-party-actions-config).

## Why?

We are forking all third-party-actions into this repo and disabling the ability to use external actions in our org.
We're doing this to have more control over the third-party code that we use:

* **We need to make sure that license is acceptable.** e.g. Apache 2.0, ...
* **We want to vet the actions we use**: there is a wide range of quality in third-party code. The approval process gives us a place and time to do a gut check (with peer review).
* **We want to try and coordinate**: having one solution to a problem is usually better than 10 solutions to the same problem.
* **We want a bit more pinning**: the status quo for actions is to do something like `uses: actions/checkout@v2`. This means that your workflow may grab a new version of the action on every run. With this setup we at least get the chance to review every change to third-party code (with diffs) at the org level first.
* **We want someone responsible for doing upgrades**: we use [`CODEOWNERS` in Brightspace/third-party-actions-config](https://github.com/Brightspace/third-party-actions-config/blob/master/CODEOWNERS) to put specific people in charge of rolling out updates to each action.
* **We don't want builds to break if a repo disappears**: we've had workflows break when someone (in our case, GitHub themselves) deprecates and deletes their repo. [Brightspace/third-party-actions](https://github.com/brightspace/third-party-actions) acts as a mirror so that won't happen to us out-of-the-blue.

Our hope is that this is a low-friction process.

## Why two repos?

The third-party actions we mirror in this repo often have their own workflows.
We don't want to run them, because that could cause security problems (e.g. via self-hosted runners, etc.)
So we've disabled actions in this repo.

However, the automatic syncing is itself built on actions.
There is no way to only enable particular workflows, so we went with a split repo setup.
