# akamai_property_hostnames

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_property_hostnames" {
  source = "./modules/akamai/d/akamai_property_hostnames"

  # contract_id - (required) is a type of string
  contract_id = null
  # group_id - (required) is a type of string
  group_id = null
  # property_id - (required) is a type of string
  property_id = null
}
```

[top](#index)

### Variables

```terraform
variable "contract_id" {
  description = "(required)"
  type        = string
}

variable "group_id" {
  description = "(required)"
  type        = string
}

variable "property_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "akamai_property_hostnames" "this" {
  contract_id = var.contract_id
  group_id    = var.group_id
  property_id = var.property_id
}
```

[top](#index)

### Outputs

```terraform
output "hostnames" {
  description = "returns a list of object"
  value       = data.akamai_property_hostnames.this.hostnames
}

output "id" {
  description = "returns a string"
  value       = data.akamai_property_hostnames.this.id
}

output "version" {
  description = "returns a number"
  value       = data.akamai_property_hostnames.this.version
}

output "this" {
  value = akamai_property_hostnames.this
}
```

[top](#index)