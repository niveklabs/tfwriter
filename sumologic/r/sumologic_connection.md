# sumologic_connection

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_connection" {
  source = "./modules/sumologic/r/sumologic_connection"

  # custom_headers - (optional) is a type of map of string
  custom_headers = {}
  # default_payload - (required) is a type of string
  default_payload = null
  # description - (optional) is a type of string
  description = null
  # headers - (optional) is a type of map of string
  headers = {}
  # name - (required) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
  # url - (required) is a type of string
  url = null
  # webhook_type - (optional) is a type of string
  webhook_type = null
}
```

[top](#index)

### Variables

```terraform
variable "custom_headers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "default_payload" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "headers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "url" {
  description = "(required)"
  type        = string
}

variable "webhook_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_connection" "this" {
  custom_headers  = var.custom_headers
  default_payload = var.default_payload
  description     = var.description
  headers         = var.headers
  name            = var.name
  type            = var.type
  url             = var.url
  webhook_type    = var.webhook_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_connection.this.id
}

output "this" {
  value = sumologic_connection.this
}
```

[top](#index)