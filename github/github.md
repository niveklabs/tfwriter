---
layout: resource
title: github
type: provider
resource: github
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "github" {
  version = "4.6.0"

  # base_url - (optional) is a type of string
  base_url = null
  # insecure - (optional) is a type of bool
  insecure = null
  # organization - (optional) is a type of string
  organization = null
  # owner - (optional) is a type of string
  owner = null
  # token - (optional) is a type of string
  token = null
}
```

[top](#index)

### Resources


- [github_actions_organization_secret](./r/github_actions_organization_secret.md)

- [github_actions_secret](./r/github_actions_secret.md)

- [github_app_installation_repository](./r/github_app_installation_repository.md)

- [github_branch](./r/github_branch.md)

- [github_branch_default](./r/github_branch_default.md)

- [github_branch_protection](./r/github_branch_protection.md)

- [github_branch_protection_v3](./r/github_branch_protection_v3.md)

- [github_issue_label](./r/github_issue_label.md)

- [github_membership](./r/github_membership.md)

- [github_organization_block](./r/github_organization_block.md)

- [github_organization_project](./r/github_organization_project.md)

- [github_organization_webhook](./r/github_organization_webhook.md)

- [github_project_card](./r/github_project_card.md)

- [github_project_column](./r/github_project_column.md)

- [github_repository](./r/github_repository.md)

- [github_repository_collaborator](./r/github_repository_collaborator.md)

- [github_repository_deploy_key](./r/github_repository_deploy_key.md)

- [github_repository_file](./r/github_repository_file.md)

- [github_repository_milestone](./r/github_repository_milestone.md)

- [github_repository_project](./r/github_repository_project.md)

- [github_repository_webhook](./r/github_repository_webhook.md)

- [github_team](./r/github_team.md)

- [github_team_membership](./r/github_team_membership.md)

- [github_team_repository](./r/github_team_repository.md)

- [github_team_sync_group_mapping](./r/github_team_sync_group_mapping.md)

- [github_user_gpg_key](./r/github_user_gpg_key.md)

- [github_user_invitation_accepter](./r/github_user_invitation_accepter.md)

- [github_user_ssh_key](./r/github_user_ssh_key.md)


[top](#index)

### Datasources


- [github_actions_public_key](./d/github_actions_public_key.md)

- [github_branch](./d/github_branch.md)

- [github_collaborators](./d/github_collaborators.md)

- [github_ip_ranges](./d/github_ip_ranges.md)

- [github_membership](./d/github_membership.md)

- [github_organization](./d/github_organization.md)

- [github_organization_team_sync_groups](./d/github_organization_team_sync_groups.md)

- [github_release](./d/github_release.md)

- [github_repositories](./d/github_repositories.md)

- [github_repository](./d/github_repository.md)

- [github_repository_milestone](./d/github_repository_milestone.md)

- [github_team](./d/github_team.md)

- [github_user](./d/github_user.md)


[top](#index)