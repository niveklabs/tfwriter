# nsxt_policy_ip_discovery_profile

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
module "nsxt_policy_ip_discovery_profile" {
  source = "./modules/nsxt/d/nsxt_policy_ip_discovery_profile"

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
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - Display name of this resource"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_policy_ip_discovery_profile" "this" {
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
  value       = data.nsxt_policy_ip_discovery_profile.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_policy_ip_discovery_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_policy_ip_discovery_profile.this.id
}

output "path" {
  description = "returns a string"
  value       = data.nsxt_policy_ip_discovery_profile.this.path
}

output "this" {
  value = nsxt_policy_ip_discovery_profile.this
}
```

[top](#index)