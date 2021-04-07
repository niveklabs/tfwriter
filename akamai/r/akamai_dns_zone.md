# akamai_dns_zone

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_dns_zone" {
  source = "./modules/akamai/r/akamai_dns_zone"

  # comment - (optional) is a type of string
  comment = null
  # contract - (required) is a type of string
  contract = null
  # end_customer_id - (optional) is a type of string
  end_customer_id = null
  # group - (required) is a type of string
  group = null
  # masters - (optional) is a type of set of string
  masters = []
  # sign_and_serve - (optional) is a type of bool
  sign_and_serve = null
  # sign_and_serve_algorithm - (optional) is a type of string
  sign_and_serve_algorithm = null
  # target - (optional) is a type of string
  target = null
  # type - (required) is a type of string
  type = null
  # zone - (required) is a type of string
  zone = null

  tsig_key = [{
    algorithm = null
    name      = null
    secret    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "contract" {
  description = "(required)"
  type        = string
}

variable "end_customer_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group" {
  description = "(required)"
  type        = string
}

variable "masters" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "sign_and_serve" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "sign_and_serve_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "zone" {
  description = "(required)"
  type        = string
}

variable "tsig_key" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      algorithm = string
      name      = string
      secret    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "akamai_dns_zone" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # contract - (required) is a type of string
  contract = var.contract
  # end_customer_id - (optional) is a type of string
  end_customer_id = var.end_customer_id
  # group - (required) is a type of string
  group = var.group
  # masters - (optional) is a type of set of string
  masters = var.masters
  # sign_and_serve - (optional) is a type of bool
  sign_and_serve = var.sign_and_serve
  # sign_and_serve_algorithm - (optional) is a type of string
  sign_and_serve_algorithm = var.sign_and_serve_algorithm
  # target - (optional) is a type of string
  target = var.target
  # type - (required) is a type of string
  type = var.type
  # zone - (required) is a type of string
  zone = var.zone

  dynamic "tsig_key" {
    for_each = var.tsig_key
    content {
      # algorithm - (required) is a type of string
      algorithm = tsig_key.value["algorithm"]
      # name - (required) is a type of string
      name = tsig_key.value["name"]
      # secret - (required) is a type of string
      secret = tsig_key.value["secret"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "activation_state" {
  description = "returns a string"
  value       = akamai_dns_zone.this.activation_state
}

output "alias_count" {
  description = "returns a number"
  value       = akamai_dns_zone.this.alias_count
}

output "id" {
  description = "returns a string"
  value       = akamai_dns_zone.this.id
}

output "version_id" {
  description = "returns a string"
  value       = akamai_dns_zone.this.version_id
}

output "this" {
  value = akamai_dns_zone.this
}
```

[top](#index)