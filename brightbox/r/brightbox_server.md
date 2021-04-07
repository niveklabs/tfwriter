# brightbox_server

[back](../brightbox.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    brightbox = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "brightbox_server" {
  source = "./modules/brightbox/r/brightbox_server"

  # disk_encrypted - (optional) is a type of bool
  disk_encrypted = null
  # image - (required) is a type of string
  image = null
  # locked - (optional) is a type of bool
  locked = null
  # name - (optional) is a type of string
  name = null
  # server_groups - (required) is a type of set of string
  server_groups = []
  # type - (optional) is a type of string
  type = null
  # user_data - (optional) is a type of string
  user_data = null
  # user_data_base64 - (optional) is a type of string
  user_data_base64 = null
  # zone - (optional) is a type of string
  zone = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "disk_encrypted" {
  description = "(optional) - Is true if the server has been built with an encrypted disk"
  type        = bool
  default     = null
}

variable "image" {
  description = "(required) - Image used to create the server"
  type        = string
}

variable "locked" {
  description = "(optional) - Is true if resource has been set as locked and cannot be deleted"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - Editable user label"
  type        = string
  default     = null
}

variable "server_groups" {
  description = "(required) - Array of server groups to add server to"
  type        = set(string)
}

variable "type" {
  description = "(optional) - Server type of the server"
  type        = string
  default     = null
}

variable "user_data" {
  description = "(optional) - Data made available to Cloud Init"
  type        = string
  default     = null
}

variable "user_data_base64" {
  description = "(optional) - Base64 encoded data made available to Cloud Init"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - Zone where server is located"
  type        = string
  default     = null
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
resource "brightbox_server" "this" {
  # disk_encrypted - (optional) is a type of bool
  disk_encrypted = var.disk_encrypted
  # image - (required) is a type of string
  image = var.image
  # locked - (optional) is a type of bool
  locked = var.locked
  # name - (optional) is a type of string
  name = var.name
  # server_groups - (required) is a type of set of string
  server_groups = var.server_groups
  # type - (optional) is a type of string
  type = var.type
  # user_data - (optional) is a type of string
  user_data = var.user_data
  # user_data_base64 - (optional) is a type of string
  user_data_base64 = var.user_data_base64
  # zone - (optional) is a type of string
  zone = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "disk_encrypted" {
  description = "returns a bool"
  value       = brightbox_server.this.disk_encrypted
}

output "fqdn" {
  description = "returns a string"
  value       = brightbox_server.this.fqdn
}

output "hostname" {
  description = "returns a string"
  value       = brightbox_server.this.hostname
}

output "id" {
  description = "returns a string"
  value       = brightbox_server.this.id
}

output "interface" {
  description = "returns a string"
  value       = brightbox_server.this.interface
}

output "ipv4_address" {
  description = "returns a string"
  value       = brightbox_server.this.ipv4_address
}

output "ipv4_address_private" {
  description = "returns a string"
  value       = brightbox_server.this.ipv4_address_private
}

output "ipv6_address" {
  description = "returns a string"
  value       = brightbox_server.this.ipv6_address
}

output "ipv6_hostname" {
  description = "returns a string"
  value       = brightbox_server.this.ipv6_hostname
}

output "public_hostname" {
  description = "returns a string"
  value       = brightbox_server.this.public_hostname
}

output "status" {
  description = "returns a string"
  value       = brightbox_server.this.status
}

output "type" {
  description = "returns a string"
  value       = brightbox_server.this.type
}

output "username" {
  description = "returns a string"
  value       = brightbox_server.this.username
}

output "zone" {
  description = "returns a string"
  value       = brightbox_server.this.zone
}

output "this" {
  value = brightbox_server.this
}
```

[top](#index)