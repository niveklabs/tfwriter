# ovh_vrack_cloudproject

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_vrack_cloudproject" {
  source = "./modules/ovh/r/ovh_vrack_cloudproject"

  # project_id - (optional) is a type of string
  project_id = null
  # service_name - (optional) is a type of string
  service_name = null
  # vrack_id - (optional) is a type of string
  vrack_id = null
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(optional) - Service name of the resource representing the id of the cloud project."
  type        = string
  default     = null
}

variable "vrack_id" {
  description = "(optional) - Id of the vrack. DEPRECATED, use `service_name` instead"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ovh_vrack_cloudproject" "this" {
  # project_id - (optional) is a type of string
  project_id = var.project_id
  # service_name - (optional) is a type of string
  service_name = var.service_name
  # vrack_id - (optional) is a type of string
  vrack_id = var.vrack_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_vrack_cloudproject.this.id
}

output "service_name" {
  description = "returns a string"
  value       = ovh_vrack_cloudproject.this.service_name
}

output "vrack_id" {
  description = "returns a string"
  value       = ovh_vrack_cloudproject.this.vrack_id
}

output "this" {
  value = ovh_vrack_cloudproject.this
}
```

[top](#index)