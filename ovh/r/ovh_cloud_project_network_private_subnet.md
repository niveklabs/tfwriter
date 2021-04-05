# ovh_cloud_project_network_private_subnet

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
module "ovh_cloud_project_network_private_subnet" {
  source = "./modules/ovh/r/ovh_cloud_project_network_private_subnet"

  # dhcp - (optional) is a type of bool
  dhcp = null
  # end - (required) is a type of string
  end = null
  # network - (required) is a type of string
  network = null
  # network_id - (required) is a type of string
  network_id = null
  # no_gateway - (optional) is a type of bool
  no_gateway = null
  # project_id - (optional) is a type of string
  project_id = null
  # region - (required) is a type of string
  region = null
  # service_name - (optional) is a type of string
  service_name = null
  # start - (required) is a type of string
  start = null
}
```

[top](#index)

### Variables

```terraform
variable "dhcp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "end" {
  description = "(required)"
  type        = string
}

variable "network" {
  description = "(required)"
  type        = string
}

variable "network_id" {
  description = "(required)"
  type        = string
}

variable "no_gateway" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "project_id" {
  description = "(optional) - Id of the cloud project. DEPRECATED, use `service_name` instead"
  type        = string
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "service_name" {
  description = "(optional) - Service name of the resource representing the id of the cloud project."
  type        = string
  default     = null
}

variable "start" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_cloud_project_network_private_subnet" "this" {
  dhcp         = var.dhcp
  end          = var.end
  network      = var.network
  network_id   = var.network_id
  no_gateway   = var.no_gateway
  project_id   = var.project_id
  region       = var.region
  service_name = var.service_name
  start        = var.start
}
```

[top](#index)

### Outputs

```terraform
output "cidr" {
  description = "returns a string"
  value       = ovh_cloud_project_network_private_subnet.this.cidr
}

output "gateway_ip" {
  description = "returns a string"
  value       = ovh_cloud_project_network_private_subnet.this.gateway_ip
}

output "id" {
  description = "returns a string"
  value       = ovh_cloud_project_network_private_subnet.this.id
}

output "ip_pools" {
  description = "returns a set of object"
  value       = ovh_cloud_project_network_private_subnet.this.ip_pools
}

output "project_id" {
  description = "returns a string"
  value       = ovh_cloud_project_network_private_subnet.this.project_id
}

output "service_name" {
  description = "returns a string"
  value       = ovh_cloud_project_network_private_subnet.this.service_name
}

output "this" {
  value = ovh_cloud_project_network_private_subnet.this
}
```

[top](#index)