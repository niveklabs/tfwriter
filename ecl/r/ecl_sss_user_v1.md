# ecl_sss_user_v1

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_sss_user_v1" {
  source = "./modules/ecl/r/ecl_sss_user_v1"

  # login_id - (required) is a type of string
  login_id = null
  # mail_address - (required) is a type of string
  mail_address = null
  # notify_password - (optional) is a type of string
  notify_password = null
  # password - (optional) is a type of string
  password = null
}
```

[top](#index)

### Variables

```terraform
variable "login_id" {
  description = "(required)"
  type        = string
}

variable "mail_address" {
  description = "(required)"
  type        = string
}

variable "notify_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ecl_sss_user_v1" "this" {
  # login_id - (required) is a type of string
  login_id = var.login_id
  # mail_address - (required) is a type of string
  mail_address = var.mail_address
  # notify_password - (optional) is a type of string
  notify_password = var.notify_password
  # password - (optional) is a type of string
  password = var.password
}
```

[top](#index)

### Outputs

```terraform
output "brand_id" {
  description = "returns a string"
  value       = ecl_sss_user_v1.this.brand_id
}

output "contract_id" {
  description = "returns a string"
  value       = ecl_sss_user_v1.this.contract_id
}

output "contract_owner" {
  description = "returns a bool"
  value       = ecl_sss_user_v1.this.contract_owner
}

output "external_reference_id" {
  description = "returns a string"
  value       = ecl_sss_user_v1.this.external_reference_id
}

output "id" {
  description = "returns a string"
  value       = ecl_sss_user_v1.this.id
}

output "keystone_endpoint" {
  description = "returns a string"
  value       = ecl_sss_user_v1.this.keystone_endpoint
}

output "keystone_name" {
  description = "returns a string"
  value       = ecl_sss_user_v1.this.keystone_name
}

output "keystone_password" {
  description = "returns a string"
  value       = ecl_sss_user_v1.this.keystone_password
}

output "login_integration" {
  description = "returns a string"
  value       = ecl_sss_user_v1.this.login_integration
}

output "sss_endpoint" {
  description = "returns a string"
  value       = ecl_sss_user_v1.this.sss_endpoint
}

output "start_time" {
  description = "returns a string"
  value       = ecl_sss_user_v1.this.start_time
}

output "user_id" {
  description = "returns a string"
  value       = ecl_sss_user_v1.this.user_id
}

output "this" {
  value = ecl_sss_user_v1.this
}
```

[top](#index)