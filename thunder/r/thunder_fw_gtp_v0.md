# thunder_fw_gtp_v0

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
module "thunder_fw_gtp_v0" {
  source = "./modules/thunder/r/thunder_fw_gtp_v0"

  # gtpv0_value - (optional) is a type of string
  gtpv0_value = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "gtpv0_value" {
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
resource "thunder_fw_gtp_v0" "this" {
  # gtpv0_value - (optional) is a type of string
  gtpv0_value = var.gtpv0_value
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_gtp_v0.this.id
}

output "this" {
  value = thunder_fw_gtp_v0.this
}
```

[top](#index)