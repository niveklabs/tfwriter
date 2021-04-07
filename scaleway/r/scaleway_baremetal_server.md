# scaleway_baremetal_server

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_baremetal_server" {
  source = "./modules/scaleway/r/scaleway_baremetal_server"

  # description - (optional) is a type of string
  description = null
  # hostname - (optional) is a type of string
  hostname = null
  # name - (optional) is a type of string
  name = null
  # offer - (required) is a type of string
  offer = null
  # os - (required) is a type of string
  os = null
  # project_id - (optional) is a type of string
  project_id = null
  # ssh_key_ids - (required) is a type of list of string
  ssh_key_ids = []
  # tags - (optional) is a type of list of string
  tags = []
  # zone - (optional) is a type of string
  zone = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Some description to associate to the server, max 255 characters"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional) - Hostname of the server"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the server"
  type        = string
  default     = null
}

variable "offer" {
  description = "(required) - ID or name of the server offer"
  type        = string
}

variable "os" {
  description = "(required) - The base image of the server"
  type        = string
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "ssh_key_ids" {
  description = "(required) - Array of SSH key IDs allowed to SSH to the server"
  type        = list(string)
}

variable "tags" {
  description = "(optional) - Array of tags to associate with the server"
  type        = list(string)
  default     = null
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_baremetal_server" "this" {
  # description - (optional) is a type of string
  description = var.description
  # hostname - (optional) is a type of string
  hostname = var.hostname
  # name - (optional) is a type of string
  name = var.name
  # offer - (required) is a type of string
  offer = var.offer
  # os - (required) is a type of string
  os = var.os
  # project_id - (optional) is a type of string
  project_id = var.project_id
  # ssh_key_ids - (required) is a type of list of string
  ssh_key_ids = var.ssh_key_ids
  # tags - (optional) is a type of list of string
  tags = var.tags
  # zone - (optional) is a type of string
  zone = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "domain" {
  description = "returns a string"
  value       = scaleway_baremetal_server.this.domain
}

output "id" {
  description = "returns a string"
  value       = scaleway_baremetal_server.this.id
}

output "ips" {
  description = "returns a list of object"
  value       = scaleway_baremetal_server.this.ips
}

output "name" {
  description = "returns a string"
  value       = scaleway_baremetal_server.this.name
}

output "offer_id" {
  description = "returns a string"
  value       = scaleway_baremetal_server.this.offer_id
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_baremetal_server.this.organization_id
}

output "os_id" {
  description = "returns a string"
  value       = scaleway_baremetal_server.this.os_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_baremetal_server.this.project_id
}

output "zone" {
  description = "returns a string"
  value       = scaleway_baremetal_server.this.zone
}

output "this" {
  value = scaleway_baremetal_server.this
}
```

[top](#index)