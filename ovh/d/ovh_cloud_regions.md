# ovh_cloud_regions

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_cloud_regions" {
  source = "./modules/ovh/d/ovh_cloud_regions"

  # has_services_up - (optional) is a type of list of string
  has_services_up = []
  # project_id - (optional) is a type of string
  project_id = null
  # service_name - (optional) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "has_services_up" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "project_id" {
  description = "(optional) - Id of the cloud project. DEPRECATED, use `service_name` instead"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(optional) - Service name of the resource representing the id of the cloud project."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ovh_cloud_regions" "this" {
  has_services_up = var.has_services_up
  project_id      = var.project_id
  service_name    = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.ovh_cloud_regions.this.id
}

output "names" {
  description = "returns a set of string"
  value       = data.ovh_cloud_regions.this.names
}

output "project_id" {
  description = "returns a string"
  value       = data.ovh_cloud_regions.this.project_id
}

output "service_name" {
  description = "returns a string"
  value       = data.ovh_cloud_regions.this.service_name
}

output "this" {
  value = ovh_cloud_regions.this
}
```

[top](#index)