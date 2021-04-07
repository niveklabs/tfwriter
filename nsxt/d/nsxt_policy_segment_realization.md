# nsxt_policy_segment_realization

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
module "nsxt_policy_segment_realization" {
  source = "./modules/nsxt/d/nsxt_policy_segment_realization"

  # path - (required) is a type of string
  path = null
}
```

[top](#index)

### Variables

```terraform
variable "path" {
  description = "(required) - The path for the policy segment"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_policy_segment_realization" "this" {
  # path - (required) is a type of string
  path = var.path
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.nsxt_policy_segment_realization.this.id
}

output "network_name" {
  description = "returns a string"
  value       = data.nsxt_policy_segment_realization.this.network_name
}

output "state" {
  description = "returns a string"
  value       = data.nsxt_policy_segment_realization.this.state
}

output "this" {
  value = nsxt_policy_segment_realization.this
}
```

[top](#index)