# sdm_secret_store

[back](../sdm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sdm = ">= 1.0.19"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sdm_secret_store" {
  source = "./modules/sdm/d/sdm_secret_store"

  # ca_cert_path - (optional) is a type of string
  ca_cert_path = null
  # client_cert_path - (optional) is a type of string
  client_cert_path = null
  # client_key_path - (optional) is a type of string
  client_key_path = null
  # name - (optional) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
  # server_address - (optional) is a type of string
  server_address = null
  # type - (optional) is a type of string
  type = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ca_cert_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_cert_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_key_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
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

### Datasource

```terraform
data "sdm_secret_store" "this" {
  # ca_cert_path - (optional) is a type of string
  ca_cert_path = var.ca_cert_path
  # client_cert_path - (optional) is a type of string
  client_cert_path = var.client_cert_path
  # client_key_path - (optional) is a type of string
  client_key_path = var.client_key_path
  # name - (optional) is a type of string
  name = var.name
  # region - (optional) is a type of string
  region = var.region
  # server_address - (optional) is a type of string
  server_address = var.server_address
  # type - (optional) is a type of string
  type = var.type

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
output "id" {
  description = "returns a string"
  value       = data.sdm_secret_store.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.sdm_secret_store.this.ids
}

output "secret_stores" {
  description = "returns a list of object"
  value       = data.sdm_secret_store.this.secret_stores
}

output "this" {
  value = sdm_secret_store.this
}
```

[top](#index)