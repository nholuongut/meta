# Meta files for [nholuongut/terraform-aws-modules organization](https://github.com/nholuongut/terraform-aws-modules)

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

This repository contains Terraform configurations for all Terraform modules managed as part of [nholuongut/terraform-aws-modules](https://github.com/nholuongut/terraform-aws-modules) organization on GitHub.


## What exactly is managed here?

1. [GitHub resources](https://github.com/nholuongut/terraform-aws-modules/meta/tree/master/github/main):
    - Repositories (with issue labels)
    - Branch protections (status checks, pull-request reviews, restrictions)
    - Teams
    - Team repositories
    - Team memberships
    - Organization memberships (admins and members)

2. [Common files in GitHub repositories](https://github.com/nholuongut/terraform-aws-modules/meta/tree/master/github/repositories) is disabled. Should update to use [github_repository_file](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/repository_file) instead of `githubfile` provider:
    - .pre-commit-hooks.yml
    - .github issues and PR templates
    - CODEOWNERS
    - Makefile
    - GitHub Actions
    - LICENSE
    - README.md
    - ...


## Why here and not in each individual repository?

It is hard to keep things identical, predictable, and with high-quality, while focusing on maintaining Terraform modules.

GitHub allows to have a special repository named [.github](https://github.com/nholuongut/terraform-aws-modules/.github) where common files like `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `FUNDING.yml`, `PULL_REQUEST_TEMPLATE.md` and `SECURITY.md` are stored. Those files are automatically used by all repositories across the whole GitHub organization.

Ideally, individual Terraform module repository should contain only Terraform configurations and have standard procedures for releasing, updating, testing, documenting, defined in a central place (this repo).


## Pre-requirements

- [Terraform 1.0+](https://github.com/hashicorp/terraform)
- [Terragrunt 0.31+](https://terragrunt.gruntwork.io/)
- [Terraform Docs](https://github.com/terraform-docs/terraform-docs)
- [pre-commit hooks](https://github.com/nholuongut/pre-commit-hooks)

If you are using Mac, you can install all dependencies using Homebrew:

    $ brew install terraform terragrunt terraform-docs pre-commit


## 🔒 GitHub Token 

GitHub Personal Access Token is stored using [SecretHub.io](https://secrethub.io/) and populated during execution by Terragrunt.

Give [SecretHub.io](https://secrethub.io/) a try if you are tired of struggling with secrets already. Remember to mention that you have read about it here. :)


### Manage GitHub resources (repositories, teams, members):

    $ cd github/main
    $ terragrunt apply


### Manage files in one repository (eg, `nholuongut/terraform-aws-modules/terraform-aws-vpc`):

    $ cd github/repositories/nholuongut/terraform-aws-modules/terraform-aws-vpc
    $ terragrunt apply


### Manage files in all repositories (not supported):

Currently, it is not well implemented still. Due to a large amount of API calls to GitHub and inability of terragrunt to limit execution to a single process.
 
    $ cd github/repositories
    $ terragrunt run-all plan    # <- it is a good idea to see changes :)
    $ terragrunt run-all apply

There is a simple script to run commands in a loop - `scripts/update_repo_files.sh`.


## Ideas for later

- [x] Use [SecretHub](https://www.secrethub.io/) for storing secret Github Token
- [ ] Prevent making changes in files managed by this repo in repositories (tell users during PR checks)
- [ ] Finish running code in this repo - `nholuongut/terraform-aws-modules/terraform-aws-eks`
- [ ] Verify if GitHub is actually using the files in "ISSUE_TEMPLATE" directory from `.github` repository. Verify and update if necessary.

## Authors

This repository is managed by [Anton Babenko](https://github.com/nholuongut).


# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟