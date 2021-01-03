# cloudflare_waf_rules

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "cloudflare_waf_rules" {
  source = "./modules/cloudflare/d/cloudflare_waf_rules"

  # package_id - (optional) is a type of string
  package_id = null
  # zone_id - (required) is a type of string
  zone_id = null

  filter = [{
    description = null
    group_id    = null
    mode        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "package_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      group_id    = string
      mode        = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "cloudflare_waf_rules" "this" {
  package_id = var.package_id
  zone_id    = var.zone_id

  dynamic "filter" {
    for_each = var.filter
    content {
      description = filter.value["description"]
      group_id    = filter.value["group_id"]
      mode        = filter.value["mode"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.cloudflare_waf_rules.this.id
}

output "rules" {
  description = "returns a list of object"
  value       = data.cloudflare_waf_rules.this.rules
}

output "this" {
  value = cloudflare_waf_rules.this
}
```

[top](#index)