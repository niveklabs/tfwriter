# ecl_network_common_function_pool_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_network_common_function_pool_v2" {
  source = "./modules/ecl/d/ecl_network_common_function_pool_v2"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_network_common_function_pool_v2" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.ecl_network_common_function_pool_v2.this.description
}

output "id" {
  description = "returns a string"
  value       = data.ecl_network_common_function_pool_v2.this.id
}

output "name" {
  description = "returns a string"
  value       = data.ecl_network_common_function_pool_v2.this.name
}

output "this" {
  value = ecl_network_common_function_pool_v2.this
}
```

[top](#index)