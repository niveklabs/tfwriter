# alicloud_vpn_connection

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_vpn_connection" {
  source = "./modules/alicloud/r/alicloud_vpn_connection"

  # customer_gateway_id - (required) is a type of string
  customer_gateway_id = null
  # effect_immediately - (optional) is a type of bool
  effect_immediately = null
  # local_subnet - (required) is a type of set of string
  local_subnet = []
  # name - (optional) is a type of string
  name = null
  # remote_subnet - (required) is a type of set of string
  remote_subnet = []
  # vpn_gateway_id - (required) is a type of string
  vpn_gateway_id = null

  ike_config = [{
    ike_auth_alg  = null
    ike_enc_alg   = null
    ike_lifetime  = null
    ike_local_id  = null
    ike_mode      = null
    ike_pfs       = null
    ike_remote_id = null
    ike_version   = null
    psk           = null
  }]

  ipsec_config = [{
    ipsec_auth_alg = null
    ipsec_enc_alg  = null
    ipsec_lifetime = null
    ipsec_pfs      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "customer_gateway_id" {
  description = "(required)"
  type        = string
}

variable "effect_immediately" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "local_subnet" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_subnet" {
  description = "(required)"
  type        = set(string)
}

variable "vpn_gateway_id" {
  description = "(required)"
  type        = string
}

variable "ike_config" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ike_auth_alg  = string
      ike_enc_alg   = string
      ike_lifetime  = number
      ike_local_id  = string
      ike_mode      = string
      ike_pfs       = string
      ike_remote_id = string
      ike_version   = string
      psk           = string
    }
  ))
  default = []
}

variable "ipsec_config" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ipsec_auth_alg = string
      ipsec_enc_alg  = string
      ipsec_lifetime = number
      ipsec_pfs      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_vpn_connection" "this" {
  # customer_gateway_id - (required) is a type of string
  customer_gateway_id = var.customer_gateway_id
  # effect_immediately - (optional) is a type of bool
  effect_immediately = var.effect_immediately
  # local_subnet - (required) is a type of set of string
  local_subnet = var.local_subnet
  # name - (optional) is a type of string
  name = var.name
  # remote_subnet - (required) is a type of set of string
  remote_subnet = var.remote_subnet
  # vpn_gateway_id - (required) is a type of string
  vpn_gateway_id = var.vpn_gateway_id

  dynamic "ike_config" {
    for_each = var.ike_config
    content {
      # ike_auth_alg - (optional) is a type of string
      ike_auth_alg = ike_config.value["ike_auth_alg"]
      # ike_enc_alg - (optional) is a type of string
      ike_enc_alg = ike_config.value["ike_enc_alg"]
      # ike_lifetime - (optional) is a type of number
      ike_lifetime = ike_config.value["ike_lifetime"]
      # ike_local_id - (optional) is a type of string
      ike_local_id = ike_config.value["ike_local_id"]
      # ike_mode - (optional) is a type of string
      ike_mode = ike_config.value["ike_mode"]
      # ike_pfs - (optional) is a type of string
      ike_pfs = ike_config.value["ike_pfs"]
      # ike_remote_id - (optional) is a type of string
      ike_remote_id = ike_config.value["ike_remote_id"]
      # ike_version - (optional) is a type of string
      ike_version = ike_config.value["ike_version"]
      # psk - (optional) is a type of string
      psk = ike_config.value["psk"]
    }
  }

  dynamic "ipsec_config" {
    for_each = var.ipsec_config
    content {
      # ipsec_auth_alg - (optional) is a type of string
      ipsec_auth_alg = ipsec_config.value["ipsec_auth_alg"]
      # ipsec_enc_alg - (optional) is a type of string
      ipsec_enc_alg = ipsec_config.value["ipsec_enc_alg"]
      # ipsec_lifetime - (optional) is a type of number
      ipsec_lifetime = ipsec_config.value["ipsec_lifetime"]
      # ipsec_pfs - (optional) is a type of string
      ipsec_pfs = ipsec_config.value["ipsec_pfs"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_vpn_connection.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_vpn_connection.this.status
}

output "this" {
  value = alicloud_vpn_connection.this
}
```

[top](#index)