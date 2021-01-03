# newrelic_entity_tags

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_entity_tags" {
  source = "./modules/newrelic/r/newrelic_entity_tags"

  # guid - (required) is a type of string
  guid = null

  tag = [{
    key    = null
    values = []
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "guid" {
  description = "(required) - The guid of the entity to tag."
  type        = string
}

variable "tag" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      key    = string
      values = set(string)
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_entity_tags" "this" {
  guid = var.guid

  dynamic "tag" {
    for_each = var.tag
    content {
      key    = tag.value["key"]
      values = tag.value["values"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = newrelic_entity_tags.this.id
}

output "this" {
  value = newrelic_entity_tags.this
}
```

[top](#index)