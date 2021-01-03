# opsgenie_maintenance

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opsgenie = ">= 0.5.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_maintenance" {
  source = "./modules/opsgenie/r/opsgenie_maintenance"

  # description - (required) is a type of string
  description = null

  rules = [{
    entity = [{
      id   = null
      type = null
    }]
    state = null
  }]

  time = [{
    end_date   = null
    start_date = null
    type       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "rules" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      entity = list(object(
        {
          id   = string
          type = string
        }
      ))
      state = string
    }
  ))
}

variable "time" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      end_date   = string
      start_date = string
      type       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opsgenie_maintenance" "this" {
  description = var.description

  dynamic "rules" {
    for_each = var.rules
    content {
      state = rules.value["state"]

      dynamic "entity" {
        for_each = rules.value.entity
        content {
          id   = entity.value["id"]
          type = entity.value["type"]
        }
      }

    }
  }

  dynamic "time" {
    for_each = var.time
    content {
      end_date   = time.value["end_date"]
      start_date = time.value["start_date"]
      type       = time.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opsgenie_maintenance.this.id
}

output "this" {
  value = opsgenie_maintenance.this
}
```

[top](#index)