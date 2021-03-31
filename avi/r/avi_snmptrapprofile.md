# avi_snmptrapprofile

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
module "avi_snmptrapprofile" {
  source = "./modules/avi/r/avi_snmptrapprofile"

  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  trap_servers = [{
    community = null
    ip_addr = [{
      addr = null
      type = null
    }]
    port = null
    user = [{
      auth_passphrase = null
      auth_type       = null
      priv_passphrase = null
      priv_type       = null
      username        = null
    }]
    version = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
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

variable "trap_servers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      community = string
      ip_addr = set(object(
        {
          addr = string
          type = string
        }
      ))
      port = number
      user = set(object(
        {
          auth_passphrase = string
          auth_type       = string
          priv_passphrase = string
          priv_type       = string
          username        = string
        }
      ))
      version = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_snmptrapprofile" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid

  dynamic "trap_servers" {
    for_each = var.trap_servers
    content {
      community = trap_servers.value["community"]
      port      = trap_servers.value["port"]
      version   = trap_servers.value["version"]

      dynamic "ip_addr" {
        for_each = trap_servers.value.ip_addr
        content {
          addr = ip_addr.value["addr"]
          type = ip_addr.value["type"]
        }
      }

      dynamic "user" {
        for_each = trap_servers.value.user
        content {
          auth_passphrase = user.value["auth_passphrase"]
          auth_type       = user.value["auth_type"]
          priv_passphrase = user.value["priv_passphrase"]
          priv_type       = user.value["priv_type"]
          username        = user.value["username"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_snmptrapprofile.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_snmptrapprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_snmptrapprofile.this.uuid
}

output "this" {
  value = avi_snmptrapprofile.this
}
```

[top](#index)