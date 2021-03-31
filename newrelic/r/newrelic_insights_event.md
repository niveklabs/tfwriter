# newrelic_insights_event

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
    newrelic = ">= 2.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_insights_event" {
  source = "./modules/newrelic/r/newrelic_insights_event"


  event = [{
    attribute = [{
      key   = null
      type  = null
      value = null
    }]
    timestamp = null
    type      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "event" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      attribute = set(object(
        {
          key   = string
          type  = string
          value = string
        }
      ))
      timestamp = number
      type      = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_insights_event" "this" {

  dynamic "event" {
    for_each = var.event
    content {
      timestamp = event.value["timestamp"]
      type      = event.value["type"]

      dynamic "attribute" {
        for_each = event.value.attribute
        content {
          key   = attribute.value["key"]
          type  = attribute.value["type"]
          value = attribute.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = newrelic_insights_event.this.id
}

output "this" {
  value = newrelic_insights_event.this
}
```

[top](#index)