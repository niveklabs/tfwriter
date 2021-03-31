# oci_metering_computation_configuration

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_metering_computation_configuration" {
  source = "./modules/oci/d/oci_metering_computation_configuration"

  # tenant_id - (required) is a type of string
  tenant_id = null
}
```

[top](#index)

### Variables

```terraform
variable "tenant_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_metering_computation_configuration" "this" {
  tenant_id = var.tenant_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_metering_computation_configuration.this.id
}

output "items" {
  description = "returns a list of object"
  value       = data.oci_metering_computation_configuration.this.items
}

output "this" {
  value = oci_metering_computation_configuration.this
}
```

[top](#index)