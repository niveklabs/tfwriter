---
layout: resource
title: gitlab
type: provider
resource: gitlab
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "gitlab" {
  version = "3.5.0"

  # base_url - (optional) is a type of string
  base_url = null
  # cacert_file - (optional) is a type of string
  cacert_file = null
  # client_cert - (optional) is a type of string
  client_cert = null
  # client_key - (optional) is a type of string
  client_key = null
  # insecure - (optional) is a type of bool
  insecure = null
  # token - (required) is a type of string
  token = null
}
```

[top](#index)

### Resources


- [gitlab_branch_protection](./r/gitlab_branch_protection.md)

- [gitlab_deploy_key](./r/gitlab_deploy_key.md)

- [gitlab_deploy_key_enable](./r/gitlab_deploy_key_enable.md)

- [gitlab_deploy_token](./r/gitlab_deploy_token.md)

- [gitlab_group](./r/gitlab_group.md)

- [gitlab_group_cluster](./r/gitlab_group_cluster.md)

- [gitlab_group_label](./r/gitlab_group_label.md)

- [gitlab_group_ldap_link](./r/gitlab_group_ldap_link.md)

- [gitlab_group_membership](./r/gitlab_group_membership.md)

- [gitlab_group_share_group](./r/gitlab_group_share_group.md)

- [gitlab_group_variable](./r/gitlab_group_variable.md)

- [gitlab_instance_cluster](./r/gitlab_instance_cluster.md)

- [gitlab_instance_variable](./r/gitlab_instance_variable.md)

- [gitlab_label](./r/gitlab_label.md)

- [gitlab_pipeline_schedule](./r/gitlab_pipeline_schedule.md)

- [gitlab_pipeline_schedule_variable](./r/gitlab_pipeline_schedule_variable.md)

- [gitlab_pipeline_trigger](./r/gitlab_pipeline_trigger.md)

- [gitlab_project](./r/gitlab_project.md)

- [gitlab_project_approval_rule](./r/gitlab_project_approval_rule.md)

- [gitlab_project_cluster](./r/gitlab_project_cluster.md)

- [gitlab_project_freeze_period](./r/gitlab_project_freeze_period.md)

- [gitlab_project_hook](./r/gitlab_project_hook.md)

- [gitlab_project_level_mr_approvals](./r/gitlab_project_level_mr_approvals.md)

- [gitlab_project_membership](./r/gitlab_project_membership.md)

- [gitlab_project_mirror](./r/gitlab_project_mirror.md)

- [gitlab_project_share_group](./r/gitlab_project_share_group.md)

- [gitlab_project_variable](./r/gitlab_project_variable.md)

- [gitlab_service_github](./r/gitlab_service_github.md)

- [gitlab_service_jira](./r/gitlab_service_jira.md)

- [gitlab_service_pipelines_email](./r/gitlab_service_pipelines_email.md)

- [gitlab_service_slack](./r/gitlab_service_slack.md)

- [gitlab_tag_protection](./r/gitlab_tag_protection.md)

- [gitlab_user](./r/gitlab_user.md)


[top](#index)

### Datasources


- [gitlab_group](./d/gitlab_group.md)

- [gitlab_group_membership](./d/gitlab_group_membership.md)

- [gitlab_project](./d/gitlab_project.md)

- [gitlab_projects](./d/gitlab_projects.md)

- [gitlab_user](./d/gitlab_user.md)

- [gitlab_users](./d/gitlab_users.md)


[top](#index)