# oci_core_instance_pool_instance

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_instance_pool_instance" {
  source = "./modules/oci/r/oci_core_instance_pool_instance"

  # auto_terminate_instance_on_delete - (optional) is a type of bool
  auto_terminate_instance_on_delete = null
  # decrement_size_on_delete - (optional) is a type of bool
  decrement_size_on_delete = null
  # instance_id - (required) is a type of string
  instance_id = null
  # instance_pool_id - (required) is a type of string
  instance_pool_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_terminate_instance_on_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "decrement_size_on_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "instance_pool_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_core_instance_pool_instance" "this" {
  auto_terminate_instance_on_delete = var.auto_terminate_instance_on_delete
  decrement_size_on_delete          = var.decrement_size_on_delete
  instance_id                       = var.instance_id
  instance_pool_id                  = var.instance_pool_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "availability_domain" {
  description = "returns a string"
  value       = oci_core_instance_pool_instance.this.availability_domain
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_core_instance_pool_instance.this.compartment_id
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_instance_pool_instance.this.display_name
}

output "fault_domain" {
  description = "returns a string"
  value       = oci_core_instance_pool_instance.this.fault_domain
}

output "id" {
  description = "returns a string"
  value       = oci_core_instance_pool_instance.this.id
}

output "instance_configuration_id" {
  description = "returns a string"
  value       = oci_core_instance_pool_instance.this.instance_configuration_id
}

output "load_balancer_backends" {
  description = "returns a list of object"
  value       = oci_core_instance_pool_instance.this.load_balancer_backends
}

output "region" {
  description = "returns a string"
  value       = oci_core_instance_pool_instance.this.region
}

output "shape" {
  description = "returns a string"
  value       = oci_core_instance_pool_instance.this.shape
}

output "state" {
  description = "returns a string"
  value       = oci_core_instance_pool_instance.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_instance_pool_instance.this.time_created
}

output "this" {
  value = oci_core_instance_pool_instance.this
}
```

[top](#index)