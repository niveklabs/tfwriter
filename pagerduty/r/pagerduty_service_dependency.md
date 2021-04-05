# pagerduty_service_dependency

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.9.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_service_dependency" {
  source = "./modules/pagerduty/r/pagerduty_service_dependency"


  dependency = [{
    dependent_service = [{
      id   = null
      type = null
    }]
    supporting_service = [{
      id   = null
      type = null
    }]
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dependency" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      dependent_service = list(object(
        {
          id   = string
          type = string
        }
      ))
      supporting_service = list(object(
        {
          id   = string
          type = string
        }
      ))
      type = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_service_dependency" "this" {

  dynamic "dependency" {
    for_each = var.dependency
    content {
      type = dependency.value["type"]

      dynamic "dependent_service" {
        for_each = dependency.value.dependent_service
        content {
          id   = dependent_service.value["id"]
          type = dependent_service.value["type"]
        }
      }

      dynamic "supporting_service" {
        for_each = dependency.value.supporting_service
        content {
          id   = supporting_service.value["id"]
          type = supporting_service.value["type"]
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
  value       = pagerduty_service_dependency.this.id
}

output "this" {
  value = pagerduty_service_dependency.this
}
```

[top](#index)