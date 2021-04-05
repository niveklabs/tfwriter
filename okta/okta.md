---
layout: resource
title: okta
type: provider
resource: okta
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "okta" {
  version = "3.11.0"

  # api_token - (optional) is a type of string
  api_token = null
  # backoff - (optional) is a type of bool
  backoff = null
  # base_url - (optional) is a type of string
  base_url = null
  # client_id - (optional) is a type of string
  client_id = null
  # log_level - (optional) is a type of number
  log_level = null
  # max_retries - (optional) is a type of number
  max_retries = null
  # max_wait_seconds - (optional) is a type of number
  max_wait_seconds = null
  # min_wait_seconds - (optional) is a type of number
  min_wait_seconds = null
  # org_name - (optional) is a type of string
  org_name = null
  # parallelism - (optional) is a type of number
  parallelism = null
  # private_key - (optional) is a type of string
  private_key = null
  # request_timeout - (optional) is a type of number
  request_timeout = null
  # scopes - (optional) is a type of set of string
  scopes = []
}
```

[top](#index)

### Resources


- [okta_admin_role_targets](./r/okta_admin_role_targets.md)

- [okta_app_auto_login](./r/okta_app_auto_login.md)

- [okta_app_basic_auth](./r/okta_app_basic_auth.md)

- [okta_app_bookmark](./r/okta_app_bookmark.md)

- [okta_app_group_assignment](./r/okta_app_group_assignment.md)

- [okta_app_oauth](./r/okta_app_oauth.md)

- [okta_app_oauth_api_scope](./r/okta_app_oauth_api_scope.md)

- [okta_app_oauth_redirect_uri](./r/okta_app_oauth_redirect_uri.md)

- [okta_app_saml](./r/okta_app_saml.md)

- [okta_app_secure_password_store](./r/okta_app_secure_password_store.md)

- [okta_app_swa](./r/okta_app_swa.md)

- [okta_app_three_field](./r/okta_app_three_field.md)

- [okta_app_user](./r/okta_app_user.md)

- [okta_app_user_base_schema](./r/okta_app_user_base_schema.md)

- [okta_app_user_schema](./r/okta_app_user_schema.md)

- [okta_auth_server](./r/okta_auth_server.md)

- [okta_auth_server_claim](./r/okta_auth_server_claim.md)

- [okta_auth_server_claim_default](./r/okta_auth_server_claim_default.md)

- [okta_auth_server_default](./r/okta_auth_server_default.md)

- [okta_auth_server_policy](./r/okta_auth_server_policy.md)

- [okta_auth_server_policy_rule](./r/okta_auth_server_policy_rule.md)

- [okta_auth_server_scope](./r/okta_auth_server_scope.md)

- [okta_auto_login_app](./r/okta_auto_login_app.md)

- [okta_bookmark_app](./r/okta_bookmark_app.md)

- [okta_event_hook](./r/okta_event_hook.md)

- [okta_factor](./r/okta_factor.md)

- [okta_group](./r/okta_group.md)

- [okta_group_membership](./r/okta_group_membership.md)

- [okta_group_role](./r/okta_group_role.md)

- [okta_group_roles](./r/okta_group_roles.md)

- [okta_group_rule](./r/okta_group_rule.md)

- [okta_idp](./r/okta_idp.md)

- [okta_idp_oidc](./r/okta_idp_oidc.md)

- [okta_idp_saml](./r/okta_idp_saml.md)

- [okta_idp_saml_key](./r/okta_idp_saml_key.md)

- [okta_idp_social](./r/okta_idp_social.md)

- [okta_inline_hook](./r/okta_inline_hook.md)

- [okta_mfa_policy](./r/okta_mfa_policy.md)

- [okta_mfa_policy_rule](./r/okta_mfa_policy_rule.md)

- [okta_network_zone](./r/okta_network_zone.md)

- [okta_oauth_app](./r/okta_oauth_app.md)

- [okta_oauth_app_redirect_uri](./r/okta_oauth_app_redirect_uri.md)

- [okta_password_policy](./r/okta_password_policy.md)

- [okta_password_policy_rule](./r/okta_password_policy_rule.md)

- [okta_policy_mfa](./r/okta_policy_mfa.md)

- [okta_policy_mfa_default](./r/okta_policy_mfa_default.md)

- [okta_policy_password](./r/okta_policy_password.md)

- [okta_policy_password_default](./r/okta_policy_password_default.md)

- [okta_policy_rule_idp_discovery](./r/okta_policy_rule_idp_discovery.md)

- [okta_policy_rule_mfa](./r/okta_policy_rule_mfa.md)

- [okta_policy_rule_password](./r/okta_policy_rule_password.md)

- [okta_policy_rule_signon](./r/okta_policy_rule_signon.md)

- [okta_policy_signon](./r/okta_policy_signon.md)

- [okta_profile_mapping](./r/okta_profile_mapping.md)

- [okta_saml_app](./r/okta_saml_app.md)

- [okta_saml_idp](./r/okta_saml_idp.md)

- [okta_saml_idp_signing_key](./r/okta_saml_idp_signing_key.md)

- [okta_secure_password_store_app](./r/okta_secure_password_store_app.md)

- [okta_signon_policy](./r/okta_signon_policy.md)

- [okta_signon_policy_rule](./r/okta_signon_policy_rule.md)

- [okta_social_idp](./r/okta_social_idp.md)

- [okta_swa_app](./r/okta_swa_app.md)

- [okta_template_email](./r/okta_template_email.md)

- [okta_template_sms](./r/okta_template_sms.md)

- [okta_three_field_app](./r/okta_three_field_app.md)

- [okta_trusted_origin](./r/okta_trusted_origin.md)

- [okta_user](./r/okta_user.md)

- [okta_user_base_schema](./r/okta_user_base_schema.md)

- [okta_user_schema](./r/okta_user_schema.md)

- [okta_user_type](./r/okta_user_type.md)


[top](#index)

### Datasources


- [okta_app](./d/okta_app.md)

- [okta_app_metadata_saml](./d/okta_app_metadata_saml.md)

- [okta_app_oauth](./d/okta_app_oauth.md)

- [okta_app_saml](./d/okta_app_saml.md)

- [okta_auth_server](./d/okta_auth_server.md)

- [okta_auth_server_policy](./d/okta_auth_server_policy.md)

- [okta_auth_server_scopes](./d/okta_auth_server_scopes.md)

- [okta_default_policies](./d/okta_default_policies.md)

- [okta_default_policy](./d/okta_default_policy.md)

- [okta_everyone_group](./d/okta_everyone_group.md)

- [okta_group](./d/okta_group.md)

- [okta_groups](./d/okta_groups.md)

- [okta_idp_metadata_saml](./d/okta_idp_metadata_saml.md)

- [okta_idp_oidc](./d/okta_idp_oidc.md)

- [okta_idp_saml](./d/okta_idp_saml.md)

- [okta_idp_social](./d/okta_idp_social.md)

- [okta_policy](./d/okta_policy.md)

- [okta_user](./d/okta_user.md)

- [okta_user_profile_mapping_source](./d/okta_user_profile_mapping_source.md)

- [okta_user_type](./d/okta_user_type.md)

- [okta_users](./d/okta_users.md)


[top](#index)