# thunder_fw_gtp_in_gtp_filtering

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_fw_gtp_in_gtp_filtering" {
  source = "./modules/thunder/r/thunder_fw_gtp_in_gtp_filtering"

  # gtp_in_gtp_value - (optional) is a type of string
  gtp_in_gtp_value = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "gtp_in_gtp_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_fw_gtp_in_gtp_filtering" "this" {
  # gtp_in_gtp_value - (optional) is a type of string
  gtp_in_gtp_value = var.gtp_in_gtp_value
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_gtp_in_gtp_filtering.this.id
}

output "this" {
  value = thunder_fw_gtp_in_gtp_filtering.this
}
```

[top](#index)