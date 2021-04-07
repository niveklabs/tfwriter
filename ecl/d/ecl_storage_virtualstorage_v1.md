# ecl_storage_virtualstorage_v1

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
module "ecl_storage_virtualstorage_v1" {
  source = "./modules/ecl/d/ecl_storage_virtualstorage_v1"

  # name - (optional) is a type of string
  name = null
  # virtual_storage_id - (optional) is a type of string
  virtual_storage_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_storage_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_storage_virtualstorage_v1" "this" {
  # name - (optional) is a type of string
  name = var.name
  # virtual_storage_id - (optional) is a type of string
  virtual_storage_id = var.virtual_storage_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.ecl_storage_virtualstorage_v1.this.description
}

output "host_routes" {
  description = "returns a list of object"
  value       = data.ecl_storage_virtualstorage_v1.this.host_routes
}

output "id" {
  description = "returns a string"
  value       = data.ecl_storage_virtualstorage_v1.this.id
}

output "ip_addr_pool" {
  description = "returns a map of string"
  value       = data.ecl_storage_virtualstorage_v1.this.ip_addr_pool
}

output "network_id" {
  description = "returns a string"
  value       = data.ecl_storage_virtualstorage_v1.this.network_id
}

output "subnet_id" {
  description = "returns a string"
  value       = data.ecl_storage_virtualstorage_v1.this.subnet_id
}

output "volume_type_id" {
  description = "returns a string"
  value       = data.ecl_storage_virtualstorage_v1.this.volume_type_id
}

output "this" {
  value = ecl_storage_virtualstorage_v1.this
}
```

[top](#index)