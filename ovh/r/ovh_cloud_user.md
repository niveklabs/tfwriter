# ovh_cloud_user

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
module "ovh_cloud_user" {
  source = "./modules/ovh/r/ovh_cloud_user"

  # description - (optional) is a type of string
  description = null
  # openstack_rc - (optional) is a type of map of string
  openstack_rc = {}
  # project_id - (optional) is a type of string
  project_id = null
  # role_name - (optional) is a type of string
  role_name = null
  # role_names - (optional) is a type of list of string
  role_names = []
  # service_name - (optional) is a type of string
  service_name = null
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

variable "openstack_rc" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "project_id" {
  description = "(optional) - Id of the cloud project. DEPRECATED, use `service_name` instead"
  type        = string
  default     = null
}

variable "role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_names" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "service_name" {
  description = "(optional) - Service name of the resource representing the id of the cloud project."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ovh_cloud_user" "this" {
  description  = var.description
  openstack_rc = var.openstack_rc
  project_id   = var.project_id
  role_name    = var.role_name
  role_names   = var.role_names
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "creation_date" {
  description = "returns a string"
  value       = ovh_cloud_user.this.creation_date
}

output "id" {
  description = "returns a string"
  value       = ovh_cloud_user.this.id
}

output "openstack_rc" {
  description = "returns a map of string"
  value       = ovh_cloud_user.this.openstack_rc
}

output "password" {
  description = "returns a string"
  value       = ovh_cloud_user.this.password
  sensitive   = true
}

output "project_id" {
  description = "returns a string"
  value       = ovh_cloud_user.this.project_id
}

output "roles" {
  description = "returns a list of object"
  value       = ovh_cloud_user.this.roles
}

output "service_name" {
  description = "returns a string"
  value       = ovh_cloud_user.this.service_name
}

output "status" {
  description = "returns a string"
  value       = ovh_cloud_user.this.status
}

output "username" {
  description = "returns a string"
  value       = ovh_cloud_user.this.username
}

output "this" {
  value = ovh_cloud_user.this
}
```

[top](#index)