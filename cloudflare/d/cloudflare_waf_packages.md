# cloudflare_waf_packages

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
module "cloudflare_waf_packages" {
  source = "./modules/cloudflare/d/cloudflare_waf_packages"

  # zone_id - (required) is a type of string
  zone_id = null

  filter = [{
    action_mode    = null
    detection_mode = null
    name           = null
    sensitivity    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      action_mode    = string
      detection_mode = string
      name           = string
      sensitivity    = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "cloudflare_waf_packages" "this" {
  zone_id = var.zone_id

  dynamic "filter" {
    for_each = var.filter
    content {
      action_mode    = filter.value["action_mode"]
      detection_mode = filter.value["detection_mode"]
      name           = filter.value["name"]
      sensitivity    = filter.value["sensitivity"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.cloudflare_waf_packages.this.id
}

output "packages" {
  description = "returns a list of object"
  value       = data.cloudflare_waf_packages.this.packages
}

output "this" {
  value = cloudflare_waf_packages.this
}
```

[top](#index)