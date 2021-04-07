# nsxt_policy_lb_monitor

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
module "nsxt_policy_lb_monitor" {
  source = "./modules/nsxt/d/nsxt_policy_lb_monitor"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # type - (optional) is a type of string
  type = null
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

variable "type" {
  description = "(optional) - Load Balancer Monitor Type"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_policy_lb_monitor" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nsxt_policy_lb_monitor.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_policy_lb_monitor.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_policy_lb_monitor.this.id
}

output "path" {
  description = "returns a string"
  value       = data.nsxt_policy_lb_monitor.this.path
}

output "this" {
  value = nsxt_policy_lb_monitor.this
}
```

[top](#index)