# cloudflare_zones

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
module "cloudflare_zones" {
  source = "./modules/cloudflare/d/cloudflare_zones"


  filter = [{
    lookup_type = null
    match       = null
    name        = null
    paused      = null
    status      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      lookup_type = string
      match       = string
      name        = string
      paused      = bool
      status      = string
    }
  ))
}
```

[top](#index)

### Datasource

```terraform
data "cloudflare_zones" "this" {

  dynamic "filter" {
    for_each = var.filter
    content {
      lookup_type = filter.value["lookup_type"]
      match       = filter.value["match"]
      name        = filter.value["name"]
      paused      = filter.value["paused"]
      status      = filter.value["status"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.cloudflare_zones.this.id
}

output "zones" {
  description = "returns a list of object"
  value       = data.cloudflare_zones.this.zones
}

output "this" {
  value = cloudflare_zones.this
}
```

[top](#index)