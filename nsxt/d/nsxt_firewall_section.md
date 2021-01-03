# nsxt_firewall_section

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
module "nsxt_firewall_section" {
  source = "./modules/nsxt/d/nsxt_firewall_section"

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
data "nsxt_firewall_section" "this" {
  description  = var.description
  display_name = var.display_name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nsxt_firewall_section.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_firewall_section.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_firewall_section.this.id
}

output "this" {
  value = nsxt_firewall_section.this
}
```

[top](#index)