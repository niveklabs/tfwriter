# nsxt_policy_group

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
    nsxt = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_group" {
  source = "./modules/nsxt/d/nsxt_policy_group"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # domain - (optional) is a type of string
  domain = null
}
```

[top](#index)

### Variables

```terraform
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
  description = "(optional) - The domain name to use for resources. If not specified 'default' is used"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_policy_group" "this" {
  description  = var.description
  display_name = var.display_name
  domain       = var.domain
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nsxt_policy_group.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_policy_group.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_policy_group.this.id
}

output "path" {
  description = "returns a string"
  value       = data.nsxt_policy_group.this.path
}

output "this" {
  value = nsxt_policy_group.this
}
```

[top](#index)