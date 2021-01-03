# nomad_quota_specification

[back](../nomad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nomad = ">= 1.4.11"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_quota_specification" {
  source = "./modules/nomad/r/nomad_quota_specification"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  limits = [{
    region = null
    region_limit = [{
      cpu       = null
      memory_mb = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description for this quota specification."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Unique name for this quota specification."
  type        = string
}

variable "limits" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      region = string
      region_limit = set(object(
        {
          cpu       = number
          memory_mb = number
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "nomad_quota_specification" "this" {
  description = var.description
  name        = var.name

  dynamic "limits" {
    for_each = var.limits
    content {
      region = limits.value["region"]

      dynamic "region_limit" {
        for_each = limits.value.region_limit
        content {
          cpu       = region_limit.value["cpu"]
          memory_mb = region_limit.value["memory_mb"]
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
  value       = nomad_quota_specification.this.id
}

output "this" {
  value = nomad_quota_specification.this
}
```

[top](#index)