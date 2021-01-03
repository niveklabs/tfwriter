# aviatrix_fqdn_pass_through

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_fqdn_pass_through" {
  source = "./modules/aviatrix/r/aviatrix_fqdn_pass_through"

  # gw_name - (required) is a type of string
  gw_name = null
  # pass_through_cidrs - (required) is a type of set of string
  pass_through_cidrs = []
}
```

[top](#index)

### Variables

```terraform
variable "gw_name" {
  description = "(required) - Gateway to apply FQDN pass-through rules to."
  type        = string
}

variable "pass_through_cidrs" {
  description = "(required) - CIDRs to allow originating requests to ignore FQDN filtering rules."
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_fqdn_pass_through" "this" {
  gw_name            = var.gw_name
  pass_through_cidrs = var.pass_through_cidrs
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_fqdn_pass_through.this.id
}

output "this" {
  value = aviatrix_fqdn_pass_through.this
}
```

[top](#index)