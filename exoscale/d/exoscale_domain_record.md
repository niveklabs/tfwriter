# exoscale_domain_record

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_domain_record" {
  source = "./modules/exoscale/d/exoscale_domain_record"

  # domain - (required) is a type of string
  domain = null

  filter = [{
    content_regex = null
    id            = null
    name          = null
    record_type   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required) - Domain of the Record"
  type        = string
}

variable "filter" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      content_regex = string
      id            = number
      name          = string
      record_type   = string
    }
  ))
}
```

[top](#index)

### Datasource

```terraform
data "exoscale_domain_record" "this" {
  domain = var.domain

  dynamic "filter" {
    for_each = var.filter
    content {
      content_regex = filter.value["content_regex"]
      id            = filter.value["id"]
      name          = filter.value["name"]
      record_type   = filter.value["record_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.exoscale_domain_record.this.id
}

output "records" {
  description = "returns a list of object"
  value       = data.exoscale_domain_record.this.records
}

output "this" {
  value = exoscale_domain_record.this
}
```

[top](#index)