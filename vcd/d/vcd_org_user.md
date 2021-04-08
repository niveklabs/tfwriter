# vcd_org_user

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_org_user" {
  source = "./modules/vcd/d/vcd_org_user"

  # name - (optional) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # user_id - (optional) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - User's name. Required if \"user_id\" is not set"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "user_id" {
  description = "(optional) - User's id. Required if \"name\" is not set"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_org_user" "this" {
  # name - (optional) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # user_id - (optional) is a type of string
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "deployed_vm_quota" {
  description = "returns a number"
  value       = data.vcd_org_user.this.deployed_vm_quota
}

output "description" {
  description = "returns a string"
  value       = data.vcd_org_user.this.description
}

output "email_address" {
  description = "returns a string"
  value       = data.vcd_org_user.this.email_address
}

output "enabled" {
  description = "returns a bool"
  value       = data.vcd_org_user.this.enabled
}

output "full_name" {
  description = "returns a string"
  value       = data.vcd_org_user.this.full_name
}

output "id" {
  description = "returns a string"
  value       = data.vcd_org_user.this.id
}

output "instant_messaging" {
  description = "returns a string"
  value       = data.vcd_org_user.this.instant_messaging
}

output "is_group_role" {
  description = "returns a bool"
  value       = data.vcd_org_user.this.is_group_role
}

output "is_locked" {
  description = "returns a bool"
  value       = data.vcd_org_user.this.is_locked
}

output "provider_type" {
  description = "returns a string"
  value       = data.vcd_org_user.this.provider_type
}

output "role" {
  description = "returns a string"
  value       = data.vcd_org_user.this.role
}

output "stored_vm_quota" {
  description = "returns a number"
  value       = data.vcd_org_user.this.stored_vm_quota
}

output "telephone" {
  description = "returns a string"
  value       = data.vcd_org_user.this.telephone
}

output "this" {
  value = vcd_org_user.this
}
```

[top](#index)