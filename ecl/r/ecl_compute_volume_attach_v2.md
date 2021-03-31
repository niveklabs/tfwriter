# ecl_compute_volume_attach_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_compute_volume_attach_v2" {
  source = "./modules/ecl/r/ecl_compute_volume_attach_v2"

  # device - (optional) is a type of string
  device = null
  # region - (optional) is a type of string
  region = null
  # server_id - (required) is a type of string
  server_id = null
  # volume_id - (required) is a type of string
  volume_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "device" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_id" {
  description = "(required)"
  type        = string
}

variable "volume_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_compute_volume_attach_v2" "this" {
  device    = var.device
  region    = var.region
  server_id = var.server_id
  volume_id = var.volume_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "device" {
  description = "returns a string"
  value       = ecl_compute_volume_attach_v2.this.device
}

output "id" {
  description = "returns a string"
  value       = ecl_compute_volume_attach_v2.this.id
}

output "region" {
  description = "returns a string"
  value       = ecl_compute_volume_attach_v2.this.region
}

output "this" {
  value = ecl_compute_volume_attach_v2.this
}
```

[top](#index)