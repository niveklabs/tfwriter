# triton_instance_template

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    triton = ">= 0.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "triton_instance_template" {
  source = "./modules/triton/r/triton_instance_template"

  # firewall_enabled - (optional) is a type of bool
  firewall_enabled = null
  # image - (required) is a type of string
  image = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # networks - (optional) is a type of list of string
  networks = []
  # package - (required) is a type of string
  package = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template_name - (required) is a type of string
  template_name = null
  # userdata - (optional) is a type of string
  userdata = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "firewall_enabled" {
  description = "(optional) - Whether to enable the firewall for group instances"
  type        = bool
  default     = null
}

variable "image" {
  description = "(required) - UUID of the image"
  type        = string
}

variable "metadata" {
  description = "(optional) - Metadata for group instances"
  type        = map(string)
  default     = null
}

variable "networks" {
  description = "(optional) - Network IDs for group instances"
  type        = list(string)
  default     = null
}

variable "package" {
  description = "(required) - Package name used for provisioning"
  type        = string
}

variable "tags" {
  description = "(optional) - Tags for group instances"
  type        = map(string)
  default     = null
}

variable "template_name" {
  description = "(required) - Friendly name for the instance template"
  type        = string
}

variable "userdata" {
  description = "(optional) - Data copied to instance on boot"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "triton_instance_template" "this" {
  # firewall_enabled - (optional) is a type of bool
  firewall_enabled = var.firewall_enabled
  # image - (required) is a type of string
  image = var.image
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # networks - (optional) is a type of list of string
  networks = var.networks
  # package - (required) is a type of string
  package = var.package
  # tags - (optional) is a type of map of string
  tags = var.tags
  # template_name - (required) is a type of string
  template_name = var.template_name
  # userdata - (optional) is a type of string
  userdata = var.userdata

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = triton_instance_template.this.id
}

output "metadata" {
  description = "returns a map of string"
  value       = triton_instance_template.this.metadata
}

output "networks" {
  description = "returns a list of string"
  value       = triton_instance_template.this.networks
}

output "tags" {
  description = "returns a map of string"
  value       = triton_instance_template.this.tags
}

output "userdata" {
  description = "returns a string"
  value       = triton_instance_template.this.userdata
}

output "this" {
  value = triton_instance_template.this
}
```

[top](#index)