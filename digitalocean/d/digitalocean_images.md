# digitalocean_images

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "digitalocean_images" {
  source = "./modules/digitalocean/d/digitalocean_images"


  filter = [{
    all      = null
    key      = null
    match_by = null
    values   = []
  }]

  sort = [{
    direction = null
    key       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      all      = bool
      key      = string
      match_by = string
      values   = list(string)
    }
  ))
  default = []
}

variable "sort" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      direction = string
      key       = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_images" "this" {

  dynamic "filter" {
    for_each = var.filter
    content {
      # all - (optional) is a type of bool
      all = filter.value["all"]
      # key - (required) is a type of string
      key = filter.value["key"]
      # match_by - (optional) is a type of string
      match_by = filter.value["match_by"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

  dynamic "sort" {
    for_each = var.sort
    content {
      # direction - (optional) is a type of string
      direction = sort.value["direction"]
      # key - (required) is a type of string
      key = sort.value["key"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.digitalocean_images.this.id
}

output "images" {
  description = "returns a list of object"
  value       = data.digitalocean_images.this.images
}

output "this" {
  value = digitalocean_images.this
}
```

[top](#index)