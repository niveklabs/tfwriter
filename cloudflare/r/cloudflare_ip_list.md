# cloudflare_ip_list

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
    cloudflare = ">= 2.15.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_ip_list" {
  source = "./modules/cloudflare/r/cloudflare_ip_list"

  # account_id - (required) is a type of string
  account_id = null
  # description - (optional) is a type of string
  description = null
  # kind - (required) is a type of string
  kind = null
  # name - (required) is a type of string
  name = null

  item = [{
    comment = null
    value   = null
  }]
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

variable "kind" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "item" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      comment = string
      value   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_ip_list" "this" {
  account_id  = var.account_id
  description = var.description
  kind        = var.kind
  name        = var.name

  dynamic "item" {
    for_each = var.item
    content {
      comment = item.value["comment"]
      value   = item.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_ip_list.this.id
}

output "this" {
  value = cloudflare_ip_list.this
}
```

[top](#index)