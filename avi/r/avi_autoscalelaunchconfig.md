# avi_autoscalelaunchconfig

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/avi/r/avi_autoscalelaunchconfig"

  # description - (optional) is a type of string
  description = null
  # image_id - (optional) is a type of string
  image_id = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # use_external_asg - (optional) is a type of bool
  use_external_asg = null
  # uuid - (optional) is a type of string
  uuid = null

  mesos = [{
    force = null
  }]

  openstack = [{
    heat_scale_down_url = null
    heat_scale_up_url   = null
  }]
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

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_external_asg" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mesos" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      force = bool
    }
  ))
  default = []
}

variable "openstack" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      heat_scale_down_url = string
      heat_scale_up_url   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_autoscalelaunchconfig" "this" {
  # description - (optional) is a type of string
  description = var.description
  # image_id - (optional) is a type of string
  image_id = var.image_id
  # name - (required) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # use_external_asg - (optional) is a type of bool
  use_external_asg = var.use_external_asg
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "mesos" {
    for_each = var.mesos
    content {
      # force - (optional) is a type of bool
      force = mesos.value["force"]
    }
  }

  dynamic "openstack" {
    for_each = var.openstack
    content {
      # heat_scale_down_url - (optional) is a type of string
      heat_scale_down_url = openstack.value["heat_scale_down_url"]
      # heat_scale_up_url - (optional) is a type of string
      heat_scale_up_url = openstack.value["heat_scale_up_url"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_autoscalelaunchconfig.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_autoscalelaunchconfig.this.id
}

output "image_id" {
  description = "returns a string"
  value       = avi_autoscalelaunchconfig.this.image_id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_autoscalelaunchconfig.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_autoscalelaunchconfig.this.uuid
}

output "this" {
  value = avi_autoscalelaunchconfig.this
}
```

[top](#index)