# ovh_cloud_network_private

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
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_cloud_network_private" {
  source = "./modules/ovh/r/ovh_cloud_network_private"

  # name - (required) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
  # regions - (optional) is a type of set of string
  regions = []
  # service_name - (optional) is a type of string
  service_name = null
  # vlan_id - (optional) is a type of number
  vlan_id = null
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

variable "regions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "service_name" {
  description = "(optional) - Service name of the resource representing the id of the cloud project."
  type        = string
  default     = null
}

variable "vlan_id" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ovh_cloud_network_private" "this" {
  name         = var.name
  project_id   = var.project_id
  regions      = var.regions
  service_name = var.service_name
  vlan_id      = var.vlan_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_cloud_network_private.this.id
}

output "project_id" {
  description = "returns a string"
  value       = ovh_cloud_network_private.this.project_id
}

output "regions" {
  description = "returns a set of string"
  value       = ovh_cloud_network_private.this.regions
}

output "regions_status" {
  description = "returns a set of object"
  value       = ovh_cloud_network_private.this.regions_status
}

output "service_name" {
  description = "returns a string"
  value       = ovh_cloud_network_private.this.service_name
}

output "status" {
  description = "returns a string"
  value       = ovh_cloud_network_private.this.status
}

output "type" {
  description = "returns a string"
  value       = ovh_cloud_network_private.this.type
}

output "this" {
  value = ovh_cloud_network_private.this
}
```

[top](#index)