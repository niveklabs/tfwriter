# avi_trafficcloneprofile

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_trafficcloneprofile" {
  source = "./modules/avi/r/avi_trafficcloneprofile"

  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # name - (required) is a type of string
  name = null
  # preserve_client_ip - (optional) is a type of bool
  preserve_client_ip = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  clone_servers = [{
    ip_address = [{
      addr = null
      type = null
    }]
    mac         = null
    network_ref = null
    subnet = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "preserve_client_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "clone_servers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address = set(object(
        {
          addr = string
          type = string
        }
      ))
      mac         = string
      network_ref = string
      subnet = set(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_trafficcloneprofile" "this" {
  cloud_ref          = var.cloud_ref
  name               = var.name
  preserve_client_ip = var.preserve_client_ip
  tenant_ref         = var.tenant_ref
  uuid               = var.uuid

  dynamic "clone_servers" {
    for_each = var.clone_servers
    content {
      mac         = clone_servers.value["mac"]
      network_ref = clone_servers.value["network_ref"]

      dynamic "ip_address" {
        for_each = clone_servers.value.ip_address
        content {
          addr = ip_address.value["addr"]
          type = ip_address.value["type"]
        }
      }

      dynamic "subnet" {
        for_each = clone_servers.value.subnet
        content {
          mask = subnet.value["mask"]

          dynamic "ip_addr" {
            for_each = subnet.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_ref" {
  description = "returns a string"
  value       = avi_trafficcloneprofile.this.cloud_ref
}

output "id" {
  description = "returns a string"
  value       = avi_trafficcloneprofile.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_trafficcloneprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_trafficcloneprofile.this.uuid
}

output "this" {
  value = avi_trafficcloneprofile.this
}
```

[top](#index)