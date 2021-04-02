# oci_optimizer_enrollment_status

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_optimizer_enrollment_status" {
  source = "./modules/oci/d/oci_optimizer_enrollment_status"

  # enrollment_status_id - (required) is a type of string
  enrollment_status_id = null
}
```

[top](#index)

### Variables

```terraform
variable "enrollment_status_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_optimizer_enrollment_status" "this" {
  enrollment_status_id = var.enrollment_status_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_optimizer_enrollment_status.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = data.oci_optimizer_enrollment_status.this.id
}

output "state" {
  description = "returns a string"
  value       = data.oci_optimizer_enrollment_status.this.state
}

output "status" {
  description = "returns a string"
  value       = data.oci_optimizer_enrollment_status.this.status
}

output "status_reason" {
  description = "returns a string"
  value       = data.oci_optimizer_enrollment_status.this.status_reason
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_optimizer_enrollment_status.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_optimizer_enrollment_status.this.time_updated
}

output "this" {
  value = oci_optimizer_enrollment_status.this
}
```

[top](#index)