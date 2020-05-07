# Approved third-party GitHub Actions for D2L

All third-party authored GitHub Actions at D2L have to be approved.
We mirror the repos into independent branches of [Brightspace/third-party-actions](https://github.com/brightspace/third-party-actions).
Here's what's available so far:

(Note that this list is maintained manually for the time being)

* [actions/checkout](https://github.com/Brightspace/third-party-actions/tree/actions/checkout): Checkout a Git repository at a particular version
* [actions/github-script](https://github.com/Brightspace/third-party-actions/tree/actions/github-script): Run simple scripts using the GitHub client
* [actions/labeler](https://github.com/Brightspace/third-party-actions/tree/actions/labeler): Label pull requests by files altered
* [actions/setup-dotnet](https://github.com/Brightspace/third-party-actions/tree/actions/setup-dotnet): Set up a specific version of the .NET Core CLI in the PATH and set up authentication to a private NuGet repository
* [actions/setup-node](https://github.com/Brightspace/third-party-actions/tree/actions/setup-node): Setup a Node.js environment and add it to the PATH, additionally providing proxy support
* [actions/stale](https://github.com/Brightspace/third-party-actions/tree/geertvdc/stale): Close issues and pull requests with no recent activity
* [aws-actions/amazon-ecs-deploy-task-definition](https://github.com/Brightspace/third-party-actions/tree/aws-actions/amazon-ecs-deploy-task-definition): Registers an Amazon ECS task definition, and deploys it to an ECS service
* [aws-actions/amazon-ecs-render-task-definition](https://github.com/Brightspace/third-party-actions/tree/aws-actions/amazon-ecs-render-task-definition): Inserts a container image URI into a container definition in an Amazon ECS task definition JSON file, creating a new file.
* [geertvdc/setup-hub](https://github.com/Brightspace/third-party-actions/tree/geertvdc/setup-hub): Setup your Github Actions runner with Hub CLI
* [hashicorp/setup-terraform](https://github.com/Brightspace/third-party-actions/tree/hashicorp/setup-terraform): Sets up Terraform CLI in your GitHub Actions workflow.
* **DEPRECATED** [hashicorp/terraform-github-actions](https://github.com/Brightspace/third-party-actions/tree/hashicorp/terraform-github-actions): Runs Terraform commands via GitHub Actions.
* [jakejarvis/hugo-build-action](https://github.com/Brightspace/third-party-actions/tree/jakejarvis/hugo-build-action): Hugo as an action, with extended support and legacy versions
* [omsmith/actions-tasklists](https://github.com/Brightspace/third-party-actions/tree/omsmith/actions-tasklists): Turn Pull Request tasklists into actionable PR statuses

The configuration lives in [Brightspace/third-party-actions-config](https://github.com/Brightspace/third-party-actions-config) so that we can disable (other peoples) actions in the this repo.
