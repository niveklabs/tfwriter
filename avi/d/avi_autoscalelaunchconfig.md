# avi_autoscalelaunchconfig

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_autoscalelaunchconfig" {
  source = "./modules/avi/d/avi_autoscalelaunchconfig"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_autoscalelaunchconfig" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.avi_autoscalelaunchconfig.this.description
}

output "id" {
  description = "returns a string"
  value       = data.avi_autoscalelaunchconfig.this.id
}

output "image_id" {
  description = "returns a string"
  value       = data.avi_autoscalelaunchconfig.this.image_id
}

output "mesos" {
  description = "returns a set of object"
  value       = data.avi_autoscalelaunchconfig.this.mesos
}

output "name" {
  description = "returns a string"
  value       = data.avi_autoscalelaunchconfig.this.name
}

output "openstack" {
  description = "returns a set of object"
  value       = data.avi_autoscalelaunchconfig.this.openstack
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_autoscalelaunchconfig.this.tenant_ref
}

output "use_external_asg" {
  description = "returns a bool"
  value       = data.avi_autoscalelaunchconfig.this.use_external_asg
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_autoscalelaunchconfig.this.uuid
}

output "this" {
  value = avi_autoscalelaunchconfig.this
}
```

[top](#index)