# thunder_fw_vrid

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
module "thunder_fw_vrid" {
  source = "./modules/thunder/r/thunder_fw_vrid"

  # uuid - (optional) is a type of string
  uuid = null
  # vrid - (optional) is a type of number
  vrid = null
}
```

[top](#index)

### Variables

```terraform
variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrid" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_fw_vrid" "this" {
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # vrid - (optional) is a type of number
  vrid = var.vrid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_vrid.this.id
}

output "this" {
  value = thunder_fw_vrid.this
}
```

[top](#index)