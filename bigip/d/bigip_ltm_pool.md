# bigip_ltm_pool

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_pool" {
  source = "./modules/bigip/d/bigip_ltm_pool"

  # name - (required) is a type of string
  name = null
  # partition - (required) is a type of string
  partition = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the certificate"
  type        = string
}

variable "partition" {
  description = "(required) - partition of resource group"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "bigip_ltm_pool" "this" {
  # name - (required) is a type of string
  name = var.name
  # partition - (required) is a type of string
  partition = var.partition
}
```

[top](#index)

### Outputs

```terraform
output "full_path" {
  description = "returns a string"
  value       = data.bigip_ltm_pool.this.full_path
}

output "id" {
  description = "returns a string"
  value       = data.bigip_ltm_pool.this.id
}

output "this" {
  value = bigip_ltm_pool.this
}
```

[top](#index)