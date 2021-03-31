# vault

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "vault" {
  version = "2.19.0"

  # add_address_to_env - (optional) is a type of string
  add_address_to_env = null
  # address - (required) is a type of string
  address = null
  # ca_cert_dir - (optional) is a type of string
  ca_cert_dir = null
  # ca_cert_file - (optional) is a type of string
  ca_cert_file = null
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = null
  # max_retries - (optional) is a type of number
  max_retries = null
  # namespace - (optional) is a type of string
  namespace = null
  # skip_tls_verify - (optional) is a type of bool
  skip_tls_verify = null
  # token - (optional) is a type of string
  token = null
  # token_name - (optional) is a type of string
  token_name = null

  # NestingList
  auth_login {
    # namespace - (optional) is a type of string
    namespace = null
    # parameters - (optional) is a type of map of string
    parameters = {}
    # path - (required) is a type of string
    path = null
  }

  # NestingList
  client_auth {
    # cert_file - (optional) is a type of string
    cert_file = null
    # key_file - (optional) is a type of string
    key_file = null
  }

  # NestingList
  headers {
    # name - (required) is a type of string
    name = null
    # value - (required) is a type of string
    value = null
  }
}
```

[top](#index)

### Resources


- [vault_ad_secret_backend](./r/vault_ad_secret_backend.md)

- [vault_ad_secret_library](./r/vault_ad_secret_library.md)

- [vault_ad_secret_role](./r/vault_ad_secret_role.md)

- [vault_alicloud_auth_backend_role](./r/vault_alicloud_auth_backend_role.md)

- [vault_approle_auth_backend_login](./r/vault_approle_auth_backend_login.md)

- [vault_approle_auth_backend_role](./r/vault_approle_auth_backend_role.md)

- [vault_approle_auth_backend_role_secret_id](./r/vault_approle_auth_backend_role_secret_id.md)

- [vault_audit](./r/vault_audit.md)

- [vault_auth_backend](./r/vault_auth_backend.md)

- [vault_aws_auth_backend_cert](./r/vault_aws_auth_backend_cert.md)

- [vault_aws_auth_backend_client](./r/vault_aws_auth_backend_client.md)

- [vault_aws_auth_backend_identity_whitelist](./r/vault_aws_auth_backend_identity_whitelist.md)

- [vault_aws_auth_backend_login](./r/vault_aws_auth_backend_login.md)

- [vault_aws_auth_backend_role](./r/vault_aws_auth_backend_role.md)

- [vault_aws_auth_backend_role_tag](./r/vault_aws_auth_backend_role_tag.md)

- [vault_aws_auth_backend_roletag_blacklist](./r/vault_aws_auth_backend_roletag_blacklist.md)

- [vault_aws_auth_backend_sts_role](./r/vault_aws_auth_backend_sts_role.md)

- [vault_aws_secret_backend](./r/vault_aws_secret_backend.md)

- [vault_aws_secret_backend_role](./r/vault_aws_secret_backend_role.md)

- [vault_azure_auth_backend_config](./r/vault_azure_auth_backend_config.md)

- [vault_azure_auth_backend_role](./r/vault_azure_auth_backend_role.md)

- [vault_azure_secret_backend](./r/vault_azure_secret_backend.md)

- [vault_azure_secret_backend_role](./r/vault_azure_secret_backend_role.md)

- [vault_cert_auth_backend_role](./r/vault_cert_auth_backend_role.md)

- [vault_consul_secret_backend](./r/vault_consul_secret_backend.md)

- [vault_consul_secret_backend_role](./r/vault_consul_secret_backend_role.md)

- [vault_database_secret_backend_connection](./r/vault_database_secret_backend_connection.md)

- [vault_database_secret_backend_role](./r/vault_database_secret_backend_role.md)

- [vault_database_secret_backend_static_role](./r/vault_database_secret_backend_static_role.md)

- [vault_egp_policy](./r/vault_egp_policy.md)

- [vault_gcp_auth_backend](./r/vault_gcp_auth_backend.md)

- [vault_gcp_auth_backend_role](./r/vault_gcp_auth_backend_role.md)

- [vault_gcp_secret_backend](./r/vault_gcp_secret_backend.md)

- [vault_gcp_secret_roleset](./r/vault_gcp_secret_roleset.md)

- [vault_generic_endpoint](./r/vault_generic_endpoint.md)

- [vault_generic_secret](./r/vault_generic_secret.md)

- [vault_github_auth_backend](./r/vault_github_auth_backend.md)

- [vault_github_team](./r/vault_github_team.md)

- [vault_github_user](./r/vault_github_user.md)

- [vault_identity_entity](./r/vault_identity_entity.md)

- [vault_identity_entity_alias](./r/vault_identity_entity_alias.md)

- [vault_identity_entity_policies](./r/vault_identity_entity_policies.md)

- [vault_identity_group](./r/vault_identity_group.md)

- [vault_identity_group_alias](./r/vault_identity_group_alias.md)

- [vault_identity_group_member_entity_ids](./r/vault_identity_group_member_entity_ids.md)

- [vault_identity_group_policies](./r/vault_identity_group_policies.md)

- [vault_identity_oidc](./r/vault_identity_oidc.md)

- [vault_identity_oidc_key](./r/vault_identity_oidc_key.md)

- [vault_identity_oidc_key_allowed_client_id](./r/vault_identity_oidc_key_allowed_client_id.md)

- [vault_identity_oidc_role](./r/vault_identity_oidc_role.md)

- [vault_jwt_auth_backend](./r/vault_jwt_auth_backend.md)

- [vault_jwt_auth_backend_role](./r/vault_jwt_auth_backend_role.md)

- [vault_kubernetes_auth_backend_config](./r/vault_kubernetes_auth_backend_config.md)

- [vault_kubernetes_auth_backend_role](./r/vault_kubernetes_auth_backend_role.md)

- [vault_ldap_auth_backend](./r/vault_ldap_auth_backend.md)

- [vault_ldap_auth_backend_group](./r/vault_ldap_auth_backend_group.md)

- [vault_ldap_auth_backend_user](./r/vault_ldap_auth_backend_user.md)

- [vault_mfa_duo](./r/vault_mfa_duo.md)

- [vault_mount](./r/vault_mount.md)

- [vault_namespace](./r/vault_namespace.md)

- [vault_nomad_secret_backend](./r/vault_nomad_secret_backend.md)

- [vault_nomad_secret_role](./r/vault_nomad_secret_role.md)

- [vault_okta_auth_backend](./r/vault_okta_auth_backend.md)

- [vault_okta_auth_backend_group](./r/vault_okta_auth_backend_group.md)

- [vault_okta_auth_backend_user](./r/vault_okta_auth_backend_user.md)

- [vault_password_policy](./r/vault_password_policy.md)

- [vault_pki_secret_backend](./r/vault_pki_secret_backend.md)

- [vault_pki_secret_backend_cert](./r/vault_pki_secret_backend_cert.md)

- [vault_pki_secret_backend_config_ca](./r/vault_pki_secret_backend_config_ca.md)

- [vault_pki_secret_backend_config_urls](./r/vault_pki_secret_backend_config_urls.md)

- [vault_pki_secret_backend_crl_config](./r/vault_pki_secret_backend_crl_config.md)

- [vault_pki_secret_backend_intermediate_cert_request](./r/vault_pki_secret_backend_intermediate_cert_request.md)

- [vault_pki_secret_backend_intermediate_set_signed](./r/vault_pki_secret_backend_intermediate_set_signed.md)

- [vault_pki_secret_backend_role](./r/vault_pki_secret_backend_role.md)

- [vault_pki_secret_backend_root_cert](./r/vault_pki_secret_backend_root_cert.md)

- [vault_pki_secret_backend_root_sign_intermediate](./r/vault_pki_secret_backend_root_sign_intermediate.md)

- [vault_pki_secret_backend_sign](./r/vault_pki_secret_backend_sign.md)

- [vault_policy](./r/vault_policy.md)

- [vault_quota_rate_limit](./r/vault_quota_rate_limit.md)

- [vault_rabbitmq_secret_backend](./r/vault_rabbitmq_secret_backend.md)

- [vault_rabbitmq_secret_backend_role](./r/vault_rabbitmq_secret_backend_role.md)

- [vault_rgp_policy](./r/vault_rgp_policy.md)

- [vault_ssh_secret_backend_ca](./r/vault_ssh_secret_backend_ca.md)

- [vault_ssh_secret_backend_role](./r/vault_ssh_secret_backend_role.md)

- [vault_terraform_cloud_secret_backend](./r/vault_terraform_cloud_secret_backend.md)

- [vault_terraform_cloud_secret_creds](./r/vault_terraform_cloud_secret_creds.md)

- [vault_terraform_cloud_secret_role](./r/vault_terraform_cloud_secret_role.md)

- [vault_token](./r/vault_token.md)

- [vault_token_auth_backend_role](./r/vault_token_auth_backend_role.md)

- [vault_transform_alphabet](./r/vault_transform_alphabet.md)

- [vault_transform_role](./r/vault_transform_role.md)

- [vault_transform_template](./r/vault_transform_template.md)

- [vault_transform_transformation](./r/vault_transform_transformation.md)

- [vault_transit_secret_backend_key](./r/vault_transit_secret_backend_key.md)

- [vault_transit_secret_cache_config](./r/vault_transit_secret_cache_config.md)


[top](#index)

### Datasources


- [vault_ad_access_credentials](./d/vault_ad_access_credentials.md)

- [vault_approle_auth_backend_role_id](./d/vault_approle_auth_backend_role_id.md)

- [vault_auth_backend](./d/vault_auth_backend.md)

- [vault_aws_access_credentials](./d/vault_aws_access_credentials.md)

- [vault_azure_access_credentials](./d/vault_azure_access_credentials.md)

- [vault_generic_secret](./d/vault_generic_secret.md)

- [vault_identity_entity](./d/vault_identity_entity.md)

- [vault_identity_group](./d/vault_identity_group.md)

- [vault_kubernetes_auth_backend_config](./d/vault_kubernetes_auth_backend_config.md)

- [vault_kubernetes_auth_backend_role](./d/vault_kubernetes_auth_backend_role.md)

- [vault_nomad_access_token](./d/vault_nomad_access_token.md)

- [vault_policy_document](./d/vault_policy_document.md)

- [vault_transform_decode](./d/vault_transform_decode.md)

- [vault_transform_encode](./d/vault_transform_encode.md)

- [vault_transit_decrypt](./d/vault_transit_decrypt.md)

- [vault_transit_encrypt](./d/vault_transit_encrypt.md)


[top](#index)