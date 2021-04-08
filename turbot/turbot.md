---
layout: resource
title: turbot
type: provider
resource: turbot
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "turbot" {
  version = "1.8.2"

  # access_key - (optional) is a type of string
  access_key = null
  # credentials_file - (optional) is a type of string
  credentials_file = null
  # profile - (optional) is a type of string
  profile = null
  # secret_key - (optional) is a type of string
  secret_key = null
  # workspace - (optional) is a type of string
  workspace = null
}
```

[top](#index)

### Resources


- [turbot_file](./r/turbot_file.md)

- [turbot_folder](./r/turbot_folder.md)

- [turbot_google_directory](./r/turbot_google_directory.md)

- [turbot_grant](./r/turbot_grant.md)

- [turbot_grant_activation](./r/turbot_grant_activation.md)

- [turbot_ldap_directory](./r/turbot_ldap_directory.md)

- [turbot_local_directory](./r/turbot_local_directory.md)

- [turbot_local_directory_user](./r/turbot_local_directory_user.md)

- [turbot_mod](./r/turbot_mod.md)

- [turbot_policy_setting](./r/turbot_policy_setting.md)

- [turbot_profile](./r/turbot_profile.md)

- [turbot_resource](./r/turbot_resource.md)

- [turbot_saml_directory](./r/turbot_saml_directory.md)

- [turbot_shadow_resource](./r/turbot_shadow_resource.md)

- [turbot_smart_folder](./r/turbot_smart_folder.md)

- [turbot_smart_folder_attachment](./r/turbot_smart_folder_attachment.md)

- [turbot_turbot_directory](./r/turbot_turbot_directory.md)


[top](#index)

### Datasources


- [turbot_control](./d/turbot_control.md)

- [turbot_policy_value](./d/turbot_policy_value.md)

- [turbot_resource](./d/turbot_resource.md)


[top](#index)