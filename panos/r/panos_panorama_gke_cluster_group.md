# panos_panorama_gke_cluster_group

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_gke_cluster_group" {
  source = "./modules/panos/r/panos_panorama_gke_cluster_group"

  # description - (optional) is a type of string
  description = null
  # device_group - (required) is a type of string
  device_group = null
  # gcp_project_credential - (required) is a type of string
  gcp_project_credential = null
  # name - (required) is a type of string
  name = null
  # template_stack - (required) is a type of string
  template_stack = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_group" {
  description = "(required)"
  type        = string
}

variable "gcp_project_credential" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "template_stack" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_gke_cluster_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # device_group - (required) is a type of string
  device_group = var.device_group
  # gcp_project_credential - (required) is a type of string
  gcp_project_credential = var.gcp_project_credential
  # name - (required) is a type of string
  name = var.name
  # template_stack - (required) is a type of string
  template_stack = var.template_stack
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_gke_cluster_group.this.id
}

output "this" {
  value = panos_panorama_gke_cluster_group.this
}
```

[top](#index)