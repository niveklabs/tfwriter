# panos_panorama_snmptrap_server_profile

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
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_snmptrap_server_profile" {
  source = "./modules/panos/r/panos_panorama_snmptrap_server_profile"

  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
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
variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "panos_panorama_snmptrap_server_profile" "this" {
  device_group   = var.device_group
  name           = var.name
  template       = var.template
  template_stack = var.template_stack
  vsys           = var.vsys

  dynamic "v2c_server" {
    for_each = var.v2c_server
    content {
      community = v2c_server.value["community"]
      manager   = v2c_server.value["manager"]
      name      = v2c_server.value["name"]
    }
  }

  dynamic "v3_server" {
    for_each = var.v3_server
    content {
      auth_password = v3_server.value["auth_password"]
      engine_id     = v3_server.value["engine_id"]
      manager       = v3_server.value["manager"]
      name          = v3_server.value["name"]
      priv_password = v3_server.value["priv_password"]
      user          = v3_server.value["user"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auth_password_enc" {
  description = "returns a map of string"
  value       = panos_panorama_snmptrap_server_profile.this.auth_password_enc
  sensitive   = true
}

output "auth_password_raw" {
  description = "returns a map of string"
  value       = panos_panorama_snmptrap_server_profile.this.auth_password_raw
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = panos_panorama_snmptrap_server_profile.this.id
}

output "priv_password_enc" {
  description = "returns a map of string"
  value       = panos_panorama_snmptrap_server_profile.this.priv_password_enc
  sensitive   = true
}

output "priv_password_raw" {
  description = "returns a map of string"
  value       = panos_panorama_snmptrap_server_profile.this.priv_password_raw
  sensitive   = true
}

output "this" {
  value = panos_panorama_snmptrap_server_profile.this
}
```

[top](#index)