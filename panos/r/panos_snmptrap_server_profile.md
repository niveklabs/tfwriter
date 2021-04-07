# panos_snmptrap_server_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_snmptrap_server_profile" {
  source = "./modules/panos/r/panos_snmptrap_server_profile"

  # name - (required) is a type of string
  name = null
  # vsys - (optional) is a type of string
  vsys = null

  v2c_server = [{
    community = null
    manager   = null
    name      = null
  }]

  v3_server = [{
    auth_password = null
    engine_id     = null
    manager       = null
    name          = null
    priv_password = null
    user          = null
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

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "v2c_server" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      community = string
      manager   = string
      name      = string
    }
  ))
  default = []
}

variable "v3_server" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth_password = string
      engine_id     = string
      manager       = string
      name          = string
      priv_password = string
      user          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_snmptrap_server_profile" "this" {
  # name - (required) is a type of string
  name = var.name
  # vsys - (optional) is a type of string
  vsys = var.vsys

  dynamic "v2c_server" {
    for_each = var.v2c_server
    content {
      # community - (required) is a type of string
      community = v2c_server.value["community"]
      # manager - (required) is a type of string
      manager = v2c_server.value["manager"]
      # name - (required) is a type of string
      name = v2c_server.value["name"]
    }
  }

  dynamic "v3_server" {
    for_each = var.v3_server
    content {
      # auth_password - (required) is a type of string
      auth_password = v3_server.value["auth_password"]
      # engine_id - (optional) is a type of string
      engine_id = v3_server.value["engine_id"]
      # manager - (required) is a type of string
      manager = v3_server.value["manager"]
      # name - (required) is a type of string
      name = v3_server.value["name"]
      # priv_password - (required) is a type of string
      priv_password = v3_server.value["priv_password"]
      # user - (required) is a type of string
      user = v3_server.value["user"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auth_password_enc" {
  description = "returns a map of string"
  value       = panos_snmptrap_server_profile.this.auth_password_enc
  sensitive   = true
}

output "auth_password_raw" {
  description = "returns a map of string"
  value       = panos_snmptrap_server_profile.this.auth_password_raw
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = panos_snmptrap_server_profile.this.id
}

output "priv_password_enc" {
  description = "returns a map of string"
  value       = panos_snmptrap_server_profile.this.priv_password_enc
  sensitive   = true
}

output "priv_password_raw" {
  description = "returns a map of string"
  value       = panos_snmptrap_server_profile.this.priv_password_raw
  sensitive   = true
}

output "this" {
  value = panos_snmptrap_server_profile.this
}
```

[top](#index)