# digitalocean_record

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_record" {
  source = "./modules/digitalocean/r/digitalocean_record"

  # domain - (required) is a type of string
  domain = null
  # flags - (optional) is a type of number
  flags = null
  # name - (required) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # priority - (optional) is a type of number
  priority = null
  # tag - (optional) is a type of string
  tag = null
  # ttl - (optional) is a type of number
  ttl = null
  # type - (required) is a type of string
  type = null
  # value - (required) is a type of string
  value = null
  # weight - (optional) is a type of number
  weight = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required)"
  type        = string
}

variable "flags" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_record" "this" {
  # domain - (required) is a type of string
  domain = var.domain
  # flags - (optional) is a type of number
  flags = var.flags
  # name - (required) is a type of string
  name = var.name
  # port - (optional) is a type of number
  port = var.port
  # priority - (optional) is a type of number
  priority = var.priority
  # tag - (optional) is a type of string
  tag = var.tag
  # ttl - (optional) is a type of number
  ttl = var.ttl
  # type - (required) is a type of string
  type = var.type
  # value - (required) is a type of string
  value = var.value
  # weight - (optional) is a type of number
  weight = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "fqdn" {
  description = "returns a string"
  value       = digitalocean_record.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = digitalocean_record.this.id
}

output "ttl" {
  description = "returns a number"
  value       = digitalocean_record.this.ttl
}

output "this" {
  value = digitalocean_record.this
}
```

[top](#index)