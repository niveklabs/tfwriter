# oci_core_console_history_data

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
module "oci_core_console_history_data" {
  source = "./modules/oci/d/oci_core_console_history_data"

  # console_history_id - (required) is a type of string
  console_history_id = null
  # length - (optional) is a type of number
  length = null
  # offset - (optional) is a type of number
  offset = null
}
```

[top](#index)

### Variables

```terraform
variable "console_history_id" {
  description = "(required)"
  type        = string
}

variable "length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "offset" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_console_history_data" "this" {
  # console_history_id - (required) is a type of string
  console_history_id = var.console_history_id
  # length - (optional) is a type of number
  length = var.length
  # offset - (optional) is a type of number
  offset = var.offset
}
```

[top](#index)

### Outputs

```terraform
output "data" {
  description = "returns a string"
  value       = data.oci_core_console_history_data.this.data
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_console_history_data.this.id
}

output "this" {
  value = oci_core_console_history_data.this
}
```

[top](#index)