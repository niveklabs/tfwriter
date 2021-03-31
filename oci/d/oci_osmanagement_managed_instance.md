# oci_osmanagement_managed_instance

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_osmanagement_managed_instance" {
  source = "./modules/oci/d/oci_osmanagement_managed_instance"

  # managed_instance_id - (required) is a type of string
  managed_instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "managed_instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_osmanagement_managed_instance" "this" {
  managed_instance_id = var.managed_instance_id
}
```

[top](#index)

### Outputs

```terraform
output "bug_updates_available" {
  description = "returns a number"
  value       = data.oci_osmanagement_managed_instance.this.bug_updates_available
}

output "child_software_sources" {
  description = "returns a list of object"
  value       = data.oci_osmanagement_managed_instance.this.child_software_sources
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance.this.compartment_id
}

output "description" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance.this.display_name
}

output "enhancement_updates_available" {
  description = "returns a number"
  value       = data.oci_osmanagement_managed_instance.this.enhancement_updates_available
}

output "id" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance.this.id
}

output "is_reboot_required" {
  description = "returns a bool"
  value       = data.oci_osmanagement_managed_instance.this.is_reboot_required
}

output "last_boot" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance.this.last_boot
}

output "last_checkin" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance.this.last_checkin
}

output "managed_instance_groups" {
  description = "returns a list of object"
  value       = data.oci_osmanagement_managed_instance.this.managed_instance_groups
}

output "os_family" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance.this.os_family
}

output "os_kernel_version" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance.this.os_kernel_version
}

output "os_name" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance.this.os_name
}

output "os_version" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance.this.os_version
}

output "other_updates_available" {
  description = "returns a number"
  value       = data.oci_osmanagement_managed_instance.this.other_updates_available
}

output "parent_software_source" {
  description = "returns a list of object"
  value       = data.oci_osmanagement_managed_instance.this.parent_software_source
}

output "scheduled_job_count" {
  description = "returns a number"
  value       = data.oci_osmanagement_managed_instance.this.scheduled_job_count
}

output "security_updates_available" {
  description = "returns a number"
  value       = data.oci_osmanagement_managed_instance.this.security_updates_available
}

output "status" {
  description = "returns a string"
  value       = data.oci_osmanagement_managed_instance.this.status
}

output "updates_available" {
  description = "returns a number"
  value       = data.oci_osmanagement_managed_instance.this.updates_available
}

output "work_request_count" {
  description = "returns a number"
  value       = data.oci_osmanagement_managed_instance.this.work_request_count
}

output "this" {
  value = oci_osmanagement_managed_instance.this
}
```

[top](#index)