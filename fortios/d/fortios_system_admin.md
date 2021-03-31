# fortios_system_admin

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_admin" {
  source = "./modules/fortios/d/fortios_system_admin"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_admin" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "accprofile" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.accprofile
}

output "accprofile_override" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.accprofile_override
}

output "allow_remove_admin_session" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.allow_remove_admin_session
}

output "comments" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.comments
}

output "email_to" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.email_to
}

output "force_password_change" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.force_password_change
}

output "fortitoken" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.fortitoken
}

output "guest_auth" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.guest_auth
}

output "guest_lang" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.guest_lang
}

output "guest_usergroups" {
  description = "returns a list of object"
  value       = data.fortios_system_admin.this.guest_usergroups
}

output "gui_dashboard" {
  description = "returns a list of object"
  value       = data.fortios_system_admin.this.gui_dashboard
}

output "gui_global_menu_favorites" {
  description = "returns a list of object"
  value       = data.fortios_system_admin.this.gui_global_menu_favorites
}

output "gui_new_feature_acknowledge" {
  description = "returns a list of object"
  value       = data.fortios_system_admin.this.gui_new_feature_acknowledge
}

output "gui_vdom_menu_favorites" {
  description = "returns a list of object"
  value       = data.fortios_system_admin.this.gui_vdom_menu_favorites
}

output "hidden" {
  description = "returns a number"
  value       = data.fortios_system_admin.this.hidden
}

output "history0" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.history0
  sensitive   = true
}

output "history1" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.history1
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.id
}

output "ip6_trusthost1" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ip6_trusthost1
}

output "ip6_trusthost10" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ip6_trusthost10
}

output "ip6_trusthost2" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ip6_trusthost2
}

output "ip6_trusthost3" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ip6_trusthost3
}

output "ip6_trusthost4" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ip6_trusthost4
}

output "ip6_trusthost5" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ip6_trusthost5
}

output "ip6_trusthost6" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ip6_trusthost6
}

output "ip6_trusthost7" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ip6_trusthost7
}

output "ip6_trusthost8" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ip6_trusthost8
}

output "ip6_trusthost9" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ip6_trusthost9
}

output "login_time" {
  description = "returns a list of object"
  value       = data.fortios_system_admin.this.login_time
}

output "password" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.password
  sensitive   = true
}

output "password_expire" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.password_expire
}

output "peer_auth" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.peer_auth
}

output "peer_group" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.peer_group
}

output "radius_vdom_override" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.radius_vdom_override
}

output "remote_auth" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.remote_auth
}

output "remote_group" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.remote_group
}

output "schedule" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.schedule
}

output "sms_custom_server" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.sms_custom_server
}

output "sms_phone" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.sms_phone
}

output "sms_server" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.sms_server
}

output "ssh_certificate" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ssh_certificate
}

output "ssh_public_key1" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ssh_public_key1
  sensitive   = true
}

output "ssh_public_key2" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ssh_public_key2
  sensitive   = true
}

output "ssh_public_key3" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.ssh_public_key3
  sensitive   = true
}

output "trusthost1" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.trusthost1
}

output "trusthost10" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.trusthost10
}

output "trusthost2" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.trusthost2
}

output "trusthost3" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.trusthost3
}

output "trusthost4" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.trusthost4
}

output "trusthost5" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.trusthost5
}

output "trusthost6" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.trusthost6
}

output "trusthost7" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.trusthost7
}

output "trusthost8" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.trusthost8
}

output "trusthost9" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.trusthost9
}

output "two_factor" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.two_factor
}

output "two_factor_authentication" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.two_factor_authentication
}

output "two_factor_notification" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.two_factor_notification
}

output "vdom" {
  description = "returns a list of object"
  value       = data.fortios_system_admin.this.vdom
}

output "wildcard" {
  description = "returns a string"
  value       = data.fortios_system_admin.this.wildcard
}

output "this" {
  value = fortios_system_admin.this
}
```

[top](#index)