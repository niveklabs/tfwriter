# sdm_secret_store

[back](../sdm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/sdm/r/sdm_secret_store"


  aws = [{
    name   = null
    region = null
    tags   = {}
  }]

  timeouts = [{
    default = null
  }]

  vault_tls = [{
    ca_cert_path     = null
    client_cert_path = null
    client_key_path  = null
    name             = null
    server_address   = null
    tags             = {}
  }]

  vault_token = [{
    name           = null
    server_address = null
    tags           = {}
  }]
}
```

[top](#index)

### Variables

```terraform
variable "aws" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      region = string
      tags   = map(string)
    }
  ))
  default = []
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

variable "vault_tls" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ca_cert_path     = string
      client_cert_path = string
      client_key_path  = string
      name             = string
      server_address   = string
      tags             = map(string)
    }
  ))
  default = []
}

variable "vault_token" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name           = string
      server_address = string
      tags           = map(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "sdm_secret_store" "this" {

  dynamic "aws" {
    for_each = var.aws
    content {
      # name - (required) is a type of string
      name = aws.value["name"]
      # region - (required) is a type of string
      region = aws.value["region"]
      # tags - (optional) is a type of map of string
      tags = aws.value["tags"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

  dynamic "vault_tls" {
    for_each = var.vault_tls
    content {
      # ca_cert_path - (optional) is a type of string
      ca_cert_path = vault_tls.value["ca_cert_path"]
      # client_cert_path - (required) is a type of string
      client_cert_path = vault_tls.value["client_cert_path"]
      # client_key_path - (required) is a type of string
      client_key_path = vault_tls.value["client_key_path"]
      # name - (required) is a type of string
      name = vault_tls.value["name"]
      # server_address - (required) is a type of string
      server_address = vault_tls.value["server_address"]
      # tags - (optional) is a type of map of string
      tags = vault_tls.value["tags"]
    }
  }

  dynamic "vault_token" {
    for_each = var.vault_token
    content {
      # name - (required) is a type of string
      name = vault_token.value["name"]
      # server_address - (required) is a type of string
      server_address = vault_token.value["server_address"]
      # tags - (optional) is a type of map of string
      tags = vault_token.value["tags"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sdm_secret_store.this.id
}

output "this" {
  value = sdm_secret_store.this
}
```

[top](#index)