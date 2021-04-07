# nsxt_switching_profile

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
module "nsxt_switching_profile" {
  source = "./modules/nsxt/d/nsxt_switching_profile"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_switching_profile" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nsxt_switching_profile.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_switching_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_switching_profile.this.id
}

output "resource_type" {
  description = "returns a string"
  value       = data.nsxt_switching_profile.this.resource_type
}

output "this" {
  value = nsxt_switching_profile.this
}
```

[top](#index)