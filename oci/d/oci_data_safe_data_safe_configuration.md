# oci_data_safe_data_safe_configuration

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_data_safe_data_safe_configuration" {
  source = "./modules/oci/d/oci_data_safe_data_safe_configuration"

  # compartment_id - (required) is a type of string
  compartment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_data_safe_data_safe_configuration" "this" {
  compartment_id = var.compartment_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_configuration.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = data.oci_data_safe_data_safe_configuration.this.is_enabled
}

output "state" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_configuration.this.state
}

output "time_enabled" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_configuration.this.time_enabled
}

output "url" {
  description = "returns a string"
  value       = data.oci_data_safe_data_safe_configuration.this.url
}

output "this" {
  value = oci_data_safe_data_safe_configuration.this
}
```

[top](#index)