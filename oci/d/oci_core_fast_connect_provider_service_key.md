# oci_core_fast_connect_provider_service_key

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_fast_connect_provider_service_key" {
  source = "./modules/oci/d/oci_core_fast_connect_provider_service_key"

  # provider_service_id - (required) is a type of string
  provider_service_id = null
  # provider_service_key_name - (required) is a type of string
  provider_service_key_name = null
}
```

[top](#index)

### Variables

```terraform
variable "provider_service_id" {
  description = "(required)"
  type        = string
}

variable "provider_service_key_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_fast_connect_provider_service_key" "this" {
  # provider_service_id - (required) is a type of string
  provider_service_id = var.provider_service_id
  # provider_service_key_name - (required) is a type of string
  provider_service_key_name = var.provider_service_key_name
}
```

[top](#index)

### Outputs

```terraform
output "bandwidth_shape_name" {
  description = "returns a string"
  value       = data.oci_core_fast_connect_provider_service_key.this.bandwidth_shape_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_fast_connect_provider_service_key.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_core_fast_connect_provider_service_key.this.name
}

output "peering_location" {
  description = "returns a string"
  value       = data.oci_core_fast_connect_provider_service_key.this.peering_location
}

output "this" {
  value = oci_core_fast_connect_provider_service_key.this
}
```

[top](#index)