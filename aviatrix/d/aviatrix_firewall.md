# aviatrix_firewall

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_firewall" {
  source = "./modules/aviatrix/d/aviatrix_firewall"

  # gw_name - (required) is a type of string
  gw_name = null
}
```

[top](#index)

### Variables

```terraform
variable "gw_name" {
  description = "(required) - Name of the gateway the firewall is associated with."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aviatrix_firewall" "this" {
  # gw_name - (required) is a type of string
  gw_name = var.gw_name
}
```

[top](#index)

### Outputs

```terraform
output "base_log_enabled" {
  description = "returns a bool"
  value       = data.aviatrix_firewall.this.base_log_enabled
}

output "base_policy" {
  description = "returns a string"
  value       = data.aviatrix_firewall.this.base_policy
}

output "id" {
  description = "returns a string"
  value       = data.aviatrix_firewall.this.id
}

output "policies" {
  description = "returns a list of object"
  value       = data.aviatrix_firewall.this.policies
}

output "this" {
  value = aviatrix_firewall.this
}
```

[top](#index)