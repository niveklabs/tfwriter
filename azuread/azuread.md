# azuread

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "azuread" {
  version = "1.1.1"

  # client_certificate_password - (optional) is a type of string
  client_certificate_password = null
  # client_certificate_path - (optional) is a type of string
  client_certificate_path = null
  # client_id - (optional) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # disable_terraform_partner_id - (optional) is a type of bool
  disable_terraform_partner_id = null
  # environment - (optional) is a type of string
  environment = null
  # metadata_host - (optional) is a type of string
  metadata_host = null
  # msi_endpoint - (optional) is a type of string
  msi_endpoint = null
  # partner_id - (optional) is a type of string
  partner_id = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
  # use_msi - (optional) is a type of bool
  use_msi = null
}
```

[top](#index)

### Resources


- [azuread_application](./r/azuread_application.md)

- [azuread_application_app_role](./r/azuread_application_app_role.md)

- [azuread_application_certificate](./r/azuread_application_certificate.md)

- [azuread_application_oauth2_permission](./r/azuread_application_oauth2_permission.md)

- [azuread_application_password](./r/azuread_application_password.md)

- [azuread_group](./r/azuread_group.md)

- [azuread_group_member](./r/azuread_group_member.md)

- [azuread_service_principal](./r/azuread_service_principal.md)

- [azuread_service_principal_certificate](./r/azuread_service_principal_certificate.md)

- [azuread_service_principal_password](./r/azuread_service_principal_password.md)

- [azuread_user](./r/azuread_user.md)


[top](#index)

### Datasources


- [azuread_application](./d/azuread_application.md)

- [azuread_client_config](./d/azuread_client_config.md)

- [azuread_domains](./d/azuread_domains.md)

- [azuread_group](./d/azuread_group.md)

- [azuread_groups](./d/azuread_groups.md)

- [azuread_service_principal](./d/azuread_service_principal.md)

- [azuread_user](./d/azuread_user.md)

- [azuread_users](./d/azuread_users.md)


[top](#index)