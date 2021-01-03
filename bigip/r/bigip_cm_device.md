# bigip_cm_device

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_cm_device" {
  source = "./modules/bigip/r/bigip_cm_device"

  # configsync_ip - (required) is a type of string
  configsync_ip = null
  # mirror_ip - (optional) is a type of string
  mirror_ip = null
  # mirror_secondary_ip - (optional) is a type of string
  mirror_secondary_ip = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "configsync_ip" {
  description = "(required) - IP address used for config sync"
  type        = string
}

variable "mirror_ip" {
  description = "(optional) - IP address used for state mirroring"
  type        = string
  default     = null
}

variable "mirror_secondary_ip" {
  description = "(optional) - Secondary IP address used for state mirroring"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Address of the Device which needs to be Deviceensed"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "bigip_cm_device" "this" {
  configsync_ip       = var.configsync_ip
  mirror_ip           = var.mirror_ip
  mirror_secondary_ip = var.mirror_secondary_ip
  name                = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_cm_device.this.id
}

output "this" {
  value = bigip_cm_device.this
}
```

[top](#index)