# heroku

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "heroku" {
  version = "4.1.0"

  # api_key - (optional) is a type of string
  api_key = null
  # email - (optional) is a type of string
  email = null
  # headers - (optional) is a type of string
  headers = null
  # url - (optional) is a type of string
  url = null

  # NestingList
  customizations {
    # set_app_all_config_vars_in_state - (optional) is a type of bool
    set_app_all_config_vars_in_state = null
  }

  # NestingList
  delays {
    # post_app_create_delay - (optional) is a type of number
    post_app_create_delay = null
    # post_domain_create_delay - (optional) is a type of number
    post_domain_create_delay = null
    # post_space_create_delay - (optional) is a type of number
    post_space_create_delay = null
  }

  # NestingList
  timeouts {
    # addon_create_timeout - (optional) is a type of number
    addon_create_timeout = null
  }
}
```

[top](#index)

### Resources


- [heroku_account_feature](./r/heroku_account_feature.md)

- [heroku_addon](./r/heroku_addon.md)

- [heroku_addon_attachment](./r/heroku_addon_attachment.md)

- [heroku_app](./r/heroku_app.md)

- [heroku_app_config_association](./r/heroku_app_config_association.md)

- [heroku_app_feature](./r/heroku_app_feature.md)

- [heroku_app_release](./r/heroku_app_release.md)

- [heroku_app_webhook](./r/heroku_app_webhook.md)

- [heroku_build](./r/heroku_build.md)

- [heroku_cert](./r/heroku_cert.md)

- [heroku_collaborator](./r/heroku_collaborator.md)

- [heroku_config](./r/heroku_config.md)

- [heroku_domain](./r/heroku_domain.md)

- [heroku_drain](./r/heroku_drain.md)

- [heroku_formation](./r/heroku_formation.md)

- [heroku_pipeline](./r/heroku_pipeline.md)

- [heroku_pipeline_config_var](./r/heroku_pipeline_config_var.md)

- [heroku_pipeline_coupling](./r/heroku_pipeline_coupling.md)

- [heroku_slug](./r/heroku_slug.md)

- [heroku_space](./r/heroku_space.md)

- [heroku_space_app_access](./r/heroku_space_app_access.md)

- [heroku_space_inbound_ruleset](./r/heroku_space_inbound_ruleset.md)

- [heroku_space_peering_connection_accepter](./r/heroku_space_peering_connection_accepter.md)

- [heroku_space_vpn_connection](./r/heroku_space_vpn_connection.md)

- [heroku_team_collaborator](./r/heroku_team_collaborator.md)

- [heroku_team_member](./r/heroku_team_member.md)


[top](#index)

### Datasources


- [heroku_addon](./d/heroku_addon.md)

- [heroku_app](./d/heroku_app.md)

- [heroku_pipeline](./d/heroku_pipeline.md)

- [heroku_space](./d/heroku_space.md)

- [heroku_space_peering_info](./d/heroku_space_peering_info.md)

- [heroku_team](./d/heroku_team.md)


[top](#index)