# ovh_cloud_region

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
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_cloud_region" {
  source = "./modules/ovh/d/ovh_cloud_region"

  # name - (required) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
  # service_name - (optional) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
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
data "ovh_cloud_region" "this" {
  name         = var.name
  project_id   = var.project_id
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "continentCode" {
  description = "returns a string"
  value       = data.ovh_cloud_region.this.continentCode
}

output "continent_code" {
  description = "returns a string"
  value       = data.ovh_cloud_region.this.continent_code
}

output "datacenterLocation" {
  description = "returns a string"
  value       = data.ovh_cloud_region.this.datacenterLocation
}

output "datacenter_location" {
  description = "returns a string"
  value       = data.ovh_cloud_region.this.datacenter_location
}

output "id" {
  description = "returns a string"
  value       = data.ovh_cloud_region.this.id
}

output "project_id" {
  description = "returns a string"
  value       = data.ovh_cloud_region.this.project_id
}

output "service_name" {
  description = "returns a string"
  value       = data.ovh_cloud_region.this.service_name
}

output "services" {
  description = "returns a set of object"
  value       = data.ovh_cloud_region.this.services
}

output "this" {
  value = ovh_cloud_region.this
}
```

[top](#index)