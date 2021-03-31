# cloudflare_waf_groups

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
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_waf_groups" {
  source = "./modules/cloudflare/d/cloudflare_waf_groups"

  # package_id - (optional) is a type of string
  package_id = null
  # zone_id - (required) is a type of string
  zone_id = null

  filter = [{
    mode = null
    name = null
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
      mode = string
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "cloudflare_waf_groups" "this" {
  package_id = var.package_id
  zone_id    = var.zone_id

  dynamic "filter" {
    for_each = var.filter
    content {
      mode = filter.value["mode"]
      name = filter.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "groups" {
  description = "returns a list of object"
  value       = data.cloudflare_waf_groups.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.cloudflare_waf_groups.this.id
}

output "this" {
  value = cloudflare_waf_groups.this
}
```

[top](#index)