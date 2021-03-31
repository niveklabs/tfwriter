# nsxt_policy_security_policy

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_security_policy" {
  source = "./modules/nsxt/d/nsxt_policy_security_policy"

  # category - (optional) is a type of string
  category = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # domain - (optional) is a type of string
  domain = null
  # is_default - (optional) is a type of bool
  is_default = null
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(optional) - Category"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - Display name of this resource"
  type        = string
  default     = null
}

variable "domain" {
  description = "(optional) - The domain name. If not specified 'default' is used"
  type        = string
  default     = null
}

variable "is_default" {
  description = "(optional) - Is this a default policy"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_policy_security_policy" "this" {
  category     = var.category
  description  = var.description
  display_name = var.display_name
  domain       = var.domain
  is_default   = var.is_default
}
```

[top](#index)

### Outputs

```terraform
output "category" {
  description = "returns a string"
  value       = data.nsxt_policy_security_policy.this.category
}

output "description" {
  description = "returns a string"
  value       = data.nsxt_policy_security_policy.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_policy_security_policy.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_policy_security_policy.this.id
}

output "path" {
  description = "returns a string"
  value       = data.nsxt_policy_security_policy.this.path
}

output "this" {
  value = nsxt_policy_security_policy.this
}
```

[top](#index)