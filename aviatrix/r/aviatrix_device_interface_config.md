# aviatrix_device_interface_config

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_device_interface_config" {
  source = "./modules/aviatrix/r/aviatrix_device_interface_config"

  # device_name - (required) is a type of string
  device_name = null
  # wan_primary_interface - (required) is a type of string
  wan_primary_interface = null
  # wan_primary_interface_public_ip - (required) is a type of string
  wan_primary_interface_public_ip = null
}
```

[top](#index)

### Variables

```terraform
variable "device_name" {
  description = "(required) - Name of device."
  type        = string
}

variable "wan_primary_interface" {
  description = "(required) - Primary WAN interface of the device. For example, 'GigabitEthernet1'."
  type        = string
}

variable "wan_primary_interface_public_ip" {
  description = "(required) - Primary WAN interface public IP address."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_device_interface_config" "this" {
  device_name                     = var.device_name
  wan_primary_interface           = var.wan_primary_interface
  wan_primary_interface_public_ip = var.wan_primary_interface_public_ip
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_device_interface_config.this.id
}

output "this" {
  value = aviatrix_device_interface_config.this
}
```

[top](#index)