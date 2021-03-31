# linode_profile

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_profile" {
  source = "./modules/linode/d/linode_profile"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "linode_profile" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "authorized_keys" {
  description = "returns a list of string"
  value       = data.linode_profile.this.authorized_keys
}

output "email" {
  description = "returns a string"
  value       = data.linode_profile.this.email
}

output "email_notifications" {
  description = "returns a bool"
  value       = data.linode_profile.this.email_notifications
}

output "id" {
  description = "returns a string"
  value       = data.linode_profile.this.id
}

output "ip_whitelist_enabled" {
  description = "returns a bool"
  value       = data.linode_profile.this.ip_whitelist_enabled
}

output "lish_auth_method" {
  description = "returns a string"
  value       = data.linode_profile.this.lish_auth_method
}

output "referrals" {
  description = "returns a list of object"
  value       = data.linode_profile.this.referrals
}

output "restricted" {
  description = "returns a bool"
  value       = data.linode_profile.this.restricted
}

output "timezone" {
  description = "returns a string"
  value       = data.linode_profile.this.timezone
}

output "two_factor_auth" {
  description = "returns a bool"
  value       = data.linode_profile.this.two_factor_auth
}

output "username" {
  description = "returns a string"
  value       = data.linode_profile.this.username
}

output "this" {
  value = linode_profile.this
}
```

[top](#index)