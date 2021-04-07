# avi_hardwaresecuritymodulegroup

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
module "avi_hardwaresecuritymodulegroup" {
  source = "./modules/avi/r/avi_hardwaresecuritymodulegroup"

  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  hsm = [{
    cloudhsm = [{
      cluster_cert         = null
      crypto_user_name     = null
      crypto_user_password = null
      hsm_ip               = []
    }]
    nethsm = [{
      esn       = null
      keyhash   = null
      module_id = null
      priority  = null
      remote_ip = [{
        addr = null
        type = null
      }]
      remote_port = null
    }]
    rfs = [{
      ip = [{
        addr = null
        type = null
      }]
      port = null
    }]
    sluna = [{
      ha_group_num = null
      is_ha        = null
      node_info = [{
        chrystoki_conf       = null
        client_cert          = null
        client_ip            = null
        client_priv_key      = null
        session_major_number = null
        session_minor_number = null
      }]
      server = [{
        index                   = null
        partition_passwd        = null
        partition_serial_number = null
        remote_ip               = null
        server_cert             = null
      }]
      server_pem            = null
      use_dedicated_network = null
    }]
    type = null
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

variable "hsm" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      cloudhsm = set(object(
        {
          cluster_cert         = string
          crypto_user_name     = string
          crypto_user_password = string
          hsm_ip               = list(string)
        }
      ))
      nethsm = list(object(
        {
          esn       = string
          keyhash   = string
          module_id = number
          priority  = number
          remote_ip = set(object(
            {
              addr = string
              type = string
            }
          ))
          remote_port = number
        }
      ))
      rfs = set(object(
        {
          ip = set(object(
            {
              addr = string
              type = string
            }
          ))
          port = number
        }
      ))
      sluna = set(object(
        {
          ha_group_num = number
          is_ha        = bool
          node_info = list(object(
            {
              chrystoki_conf       = string
              client_cert          = string
              client_ip            = string
              client_priv_key      = string
              session_major_number = number
              session_minor_number = number
            }
          ))
          server = list(object(
            {
              index                   = number
              partition_passwd        = string
              partition_serial_number = string
              remote_ip               = string
              server_cert             = string
            }
          ))
          server_pem            = string
          use_dedicated_network = bool
        }
      ))
      type = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "avi_hardwaresecuritymodulegroup" "this" {
  # name - (required) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "hsm" {
    for_each = var.hsm
    content {
      # type - (required) is a type of string
      type = hsm.value["type"]

      dynamic "cloudhsm" {
        for_each = hsm.value.cloudhsm
        content {
          # cluster_cert - (optional) is a type of string
          cluster_cert = cloudhsm.value["cluster_cert"]
          # crypto_user_name - (optional) is a type of string
          crypto_user_name = cloudhsm.value["crypto_user_name"]
          # crypto_user_password - (optional) is a type of string
          crypto_user_password = cloudhsm.value["crypto_user_password"]
          # hsm_ip - (optional) is a type of list of string
          hsm_ip = cloudhsm.value["hsm_ip"]
        }
      }

      dynamic "nethsm" {
        for_each = hsm.value.nethsm
        content {
          # esn - (required) is a type of string
          esn = nethsm.value["esn"]
          # keyhash - (required) is a type of string
          keyhash = nethsm.value["keyhash"]
          # module_id - (optional) is a type of number
          module_id = nethsm.value["module_id"]
          # priority - (required) is a type of number
          priority = nethsm.value["priority"]
          # remote_port - (optional) is a type of number
          remote_port = nethsm.value["remote_port"]

          dynamic "remote_ip" {
            for_each = nethsm.value.remote_ip
            content {
              # addr - (required) is a type of string
              addr = remote_ip.value["addr"]
              # type - (required) is a type of string
              type = remote_ip.value["type"]
            }
          }

        }
      }

      dynamic "rfs" {
        for_each = hsm.value.rfs
        content {
          # port - (optional) is a type of number
          port = rfs.value["port"]

          dynamic "ip" {
            for_each = rfs.value.ip
            content {
              # addr - (required) is a type of string
              addr = ip.value["addr"]
              # type - (required) is a type of string
              type = ip.value["type"]
            }
          }

        }
      }

      dynamic "sluna" {
        for_each = hsm.value.sluna
        content {
          # ha_group_num - (optional) is a type of number
          ha_group_num = sluna.value["ha_group_num"]
          # is_ha - (required) is a type of bool
          is_ha = sluna.value["is_ha"]
          # server_pem - (optional) is a type of string
          server_pem = sluna.value["server_pem"]
          # use_dedicated_network - (optional) is a type of bool
          use_dedicated_network = sluna.value["use_dedicated_network"]

          dynamic "node_info" {
            for_each = sluna.value.node_info
            content {
              # chrystoki_conf - (optional) is a type of string
              chrystoki_conf = node_info.value["chrystoki_conf"]
              # client_cert - (optional) is a type of string
              client_cert = node_info.value["client_cert"]
              # client_ip - (required) is a type of string
              client_ip = node_info.value["client_ip"]
              # client_priv_key - (optional) is a type of string
              client_priv_key = node_info.value["client_priv_key"]
              # session_major_number - (optional) is a type of number
              session_major_number = node_info.value["session_major_number"]
              # session_minor_number - (optional) is a type of number
              session_minor_number = node_info.value["session_minor_number"]
            }
          }

          dynamic "server" {
            for_each = sluna.value.server
            content {
              # index - (optional) is a type of number
              index = server.value["index"]
              # partition_passwd - (optional) is a type of string
              partition_passwd = server.value["partition_passwd"]
              # partition_serial_number - (optional) is a type of string
              partition_serial_number = server.value["partition_serial_number"]
              # remote_ip - (required) is a type of string
              remote_ip = server.value["remote_ip"]
              # server_cert - (required) is a type of string
              server_cert = server.value["server_cert"]
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
output "id" {
  description = "returns a string"
  value       = avi_hardwaresecuritymodulegroup.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_hardwaresecuritymodulegroup.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_hardwaresecuritymodulegroup.this.uuid
}

output "this" {
  value = avi_hardwaresecuritymodulegroup.this
}
```

[top](#index)