# akamai_properties

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
module "akamai_properties" {
  source = "./modules/akamai/d/akamai_properties"

  # contract_id - (required) is a type of string
  contract_id = null
  # group_id - (required) is a type of string
  group_id = null
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
```

[top](#index)

### Datasource

```terraform
data "akamai_properties" "this" {
  # contract_id - (required) is a type of string
  contract_id = var.contract_id
  # group_id - (required) is a type of string
  group_id = var.group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.akamai_properties.this.id
}

output "properties" {
  description = "returns a list of object"
  value       = data.akamai_properties.this.properties
}

output "this" {
  value = akamai_properties.this
}
```

[top](#index)