# oci_optimizer_enrollment_status

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_optimizer_enrollment_status" {
  source = "./modules/oci/r/oci_optimizer_enrollment_status"

  # enrollment_status_id - (required) is a type of string
  enrollment_status_id = null
  # status - (required) is a type of string
  status = null

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
variable "enrollment_status_id" {
  description = "(required)"
  type        = string
}

variable "status" {
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
resource "oci_optimizer_enrollment_status" "this" {
  enrollment_status_id = var.enrollment_status_id
  status               = var.status

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
output "compartment_id" {
  description = "returns a string"
  value       = oci_optimizer_enrollment_status.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = oci_optimizer_enrollment_status.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_optimizer_enrollment_status.this.state
}

output "status_reason" {
  description = "returns a string"
  value       = oci_optimizer_enrollment_status.this.status_reason
}

output "time_created" {
  description = "returns a string"
  value       = oci_optimizer_enrollment_status.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_optimizer_enrollment_status.this.time_updated
}

output "this" {
  value = oci_optimizer_enrollment_status.this
}
```

[top](#index)