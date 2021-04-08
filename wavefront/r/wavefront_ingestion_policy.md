# wavefront_ingestion_policy

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_ingestion_policy" {
  source = "./modules/wavefront/r/wavefront_ingestion_policy"

  # description - (required) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_ingestion_policy" "this" {
  # description - (required) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_ingestion_policy.this.id
}

output "this" {
  value = wavefront_ingestion_policy.this
}
```

[top](#index)