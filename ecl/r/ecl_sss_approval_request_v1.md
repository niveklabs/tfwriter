# ecl_sss_approval_request_v1

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_sss_approval_request_v1" {
  source = "./modules/ecl/r/ecl_sss_approval_request_v1"

  # request_id - (required) is a type of string
  request_id = null
  # status - (required) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "request_id" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ecl_sss_approval_request_v1" "this" {
  request_id = var.request_id
  status     = var.status
}
```

[top](#index)

### Outputs

```terraform
output "actions" {
  description = "returns a list of object"
  value       = ecl_sss_approval_request_v1.this.actions
}

output "approval_deadline" {
  description = "returns a string"
  value       = ecl_sss_approval_request_v1.this.approval_deadline
}

output "approval_expire" {
  description = "returns a string"
  value       = ecl_sss_approval_request_v1.this.approval_expire
}

output "approver" {
  description = "returns a bool"
  value       = ecl_sss_approval_request_v1.this.approver
}

output "approver_id" {
  description = "returns a string"
  value       = ecl_sss_approval_request_v1.this.approver_id
}

output "approver_type" {
  description = "returns a string"
  value       = ecl_sss_approval_request_v1.this.approver_type
}

output "descriptions" {
  description = "returns a list of object"
  value       = ecl_sss_approval_request_v1.this.descriptions
}

output "external_request_id" {
  description = "returns a string"
  value       = ecl_sss_approval_request_v1.this.external_request_id
}

output "id" {
  description = "returns a string"
  value       = ecl_sss_approval_request_v1.this.id
}

output "registered_time" {
  description = "returns a string"
  value       = ecl_sss_approval_request_v1.this.registered_time
}

output "request_user" {
  description = "returns a bool"
  value       = ecl_sss_approval_request_v1.this.request_user
}

output "request_user_id" {
  description = "returns a string"
  value       = ecl_sss_approval_request_v1.this.request_user_id
}

output "service" {
  description = "returns a string"
  value       = ecl_sss_approval_request_v1.this.service
}

output "updated_time" {
  description = "returns a string"
  value       = ecl_sss_approval_request_v1.this.updated_time
}

output "this" {
  value = ecl_sss_approval_request_v1.this
}
```

[top](#index)