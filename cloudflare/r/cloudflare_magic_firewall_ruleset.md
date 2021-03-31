# cloudflare_magic_firewall_ruleset

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_magic_firewall_ruleset" {
  source = "./modules/cloudflare/r/cloudflare_magic_firewall_ruleset"

  # account_id - (required) is a type of string
  account_id = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # rules - (optional) is a type of list of map of string
  rules = [{}]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rules" {
  description = "(optional)"
  type        = list(map(string))
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_magic_firewall_ruleset" "this" {
  account_id  = var.account_id
  description = var.description
  name        = var.name
  rules       = var.rules
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_magic_firewall_ruleset.this.id
}

output "this" {
  value = cloudflare_magic_firewall_ruleset.this
}
```

[top](#index)