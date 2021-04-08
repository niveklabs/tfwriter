# auth0_email

[back](../auth0.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    auth0 = ">= 0.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "auth0_email" {
  source = "./modules/auth0/r/auth0_email"

  # default_from_address - (required) is a type of string
  default_from_address = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null

  credentials = [{
    access_key_id     = null
    api_key           = null
    api_user          = null
    domain            = null
    region            = null
    secret_access_key = null
    smtp_host         = null
    smtp_pass         = null
    smtp_port         = null
    smtp_user         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_from_address" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "credentials" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      access_key_id     = string
      api_key           = string
      api_user          = string
      domain            = string
      region            = string
      secret_access_key = string
      smtp_host         = string
      smtp_pass         = string
      smtp_port         = number
      smtp_user         = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "auth0_email" "this" {
  # default_from_address - (required) is a type of string
  default_from_address = var.default_from_address
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name

  dynamic "credentials" {
    for_each = var.credentials
    content {
      # access_key_id - (optional) is a type of string
      access_key_id = credentials.value["access_key_id"]
      # api_key - (optional) is a type of string
      api_key = credentials.value["api_key"]
      # api_user - (optional) is a type of string
      api_user = credentials.value["api_user"]
      # domain - (optional) is a type of string
      domain = credentials.value["domain"]
      # region - (optional) is a type of string
      region = credentials.value["region"]
      # secret_access_key - (optional) is a type of string
      secret_access_key = credentials.value["secret_access_key"]
      # smtp_host - (optional) is a type of string
      smtp_host = credentials.value["smtp_host"]
      # smtp_pass - (optional) is a type of string
      smtp_pass = credentials.value["smtp_pass"]
      # smtp_port - (optional) is a type of number
      smtp_port = credentials.value["smtp_port"]
      # smtp_user - (optional) is a type of string
      smtp_user = credentials.value["smtp_user"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = auth0_email.this.id
}

output "this" {
  value = auth0_email.this
}
```

[top](#index)