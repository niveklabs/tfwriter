# fastly_service_dynamic_snippet_content_v1

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.21.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_service_dynamic_snippet_content_v1" {
  source = "./modules/fastly/r/fastly_service_dynamic_snippet_content_v1"

  # content - (required) is a type of string
  content = null
  # service_id - (required) is a type of string
  service_id = null
  # snippet_id - (required) is a type of string
  snippet_id = null
}
```

[top](#index)

### Variables

```terraform
variable "content" {
  description = "(required) - The contents of the VCL dynamic snippet"
  type        = string
}

variable "service_id" {
  description = "(required) - Service Id"
  type        = string
}

variable "snippet_id" {
  description = "(required) - Snippet Id"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fastly_service_dynamic_snippet_content_v1" "this" {
  content    = var.content
  service_id = var.service_id
  snippet_id = var.snippet_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fastly_service_dynamic_snippet_content_v1.this.id
}

output "this" {
  value = fastly_service_dynamic_snippet_content_v1.this
}
```

[top](#index)