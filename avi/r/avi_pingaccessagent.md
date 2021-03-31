# avi_pingaccessagent

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
module "avi_pingaccessagent" {
  source = "./modules/avi/r/avi_pingaccessagent"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # pingaccess_pool_ref - (optional) is a type of string
  pingaccess_pool_ref = null
  # properties_file_data - (optional) is a type of string
  properties_file_data = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  primary_server = [{
    hostname = null
    ip = [{
      addr = null
      type = null
    }]
    port = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pingaccess_pool_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "properties_file_data" {
  description = "(optional)"
  type        = string
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

variable "primary_server" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      hostname = string
      ip = set(object(
        {
          addr = string
          type = string
        }
      ))
      port = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_pingaccessagent" "this" {
  description          = var.description
  name                 = var.name
  pingaccess_pool_ref  = var.pingaccess_pool_ref
  properties_file_data = var.properties_file_data
  tenant_ref           = var.tenant_ref
  uuid                 = var.uuid

  dynamic "primary_server" {
    for_each = var.primary_server
    content {
      hostname = primary_server.value["hostname"]
      port     = primary_server.value["port"]

      dynamic "ip" {
        for_each = primary_server.value.ip
        content {
          addr = ip.value["addr"]
          type = ip.value["type"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_pingaccessagent.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_pingaccessagent.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_pingaccessagent.this.name
}

output "pingaccess_pool_ref" {
  description = "returns a string"
  value       = avi_pingaccessagent.this.pingaccess_pool_ref
}

output "properties_file_data" {
  description = "returns a string"
  value       = avi_pingaccessagent.this.properties_file_data
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_pingaccessagent.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_pingaccessagent.this.uuid
}

output "this" {
  value = avi_pingaccessagent.this
}
```

[top](#index)