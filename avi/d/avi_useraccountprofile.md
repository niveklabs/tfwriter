# avi_useraccountprofile

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_useraccountprofile" {
  source = "./modules/avi/d/avi_useraccountprofile"

  # name - (optional) is a type of string
  name = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_useraccountprofile" "this" {
  # name - (optional) is a type of string
  name = var.name
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "account_lock_timeout" {
  description = "returns a number"
  value       = data.avi_useraccountprofile.this.account_lock_timeout
}

output "credentials_timeout_threshold" {
  description = "returns a number"
  value       = data.avi_useraccountprofile.this.credentials_timeout_threshold
}

output "id" {
  description = "returns a string"
  value       = data.avi_useraccountprofile.this.id
}

output "max_concurrent_sessions" {
  description = "returns a number"
  value       = data.avi_useraccountprofile.this.max_concurrent_sessions
}

output "max_login_failure_count" {
  description = "returns a number"
  value       = data.avi_useraccountprofile.this.max_login_failure_count
}

output "max_password_history_count" {
  description = "returns a number"
  value       = data.avi_useraccountprofile.this.max_password_history_count
}

output "name" {
  description = "returns a string"
  value       = data.avi_useraccountprofile.this.name
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_useraccountprofile.this.uuid
}

output "this" {
  value = avi_useraccountprofile.this
}
```

[top](#index)