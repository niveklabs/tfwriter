# avi_portalfileupload

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
module "avi_portalfileupload" {
  source = "./modules/avi/r/avi_portalfileupload"

  # case_id - (optional) is a type of string
  case_id = null
  # error - (optional) is a type of string
  error = null
  # file_path - (optional) is a type of string
  file_path = null
  # name - (optional) is a type of string
  name = null
  # s3_directory - (optional) is a type of string
  s3_directory = null
  # status - (optional) is a type of string
  status = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "case_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "error" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "s3_directory" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
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

### Resource

```terraform
resource "avi_portalfileupload" "this" {
  case_id      = var.case_id
  error        = var.error
  file_path    = var.file_path
  name         = var.name
  s3_directory = var.s3_directory
  status       = var.status
  tenant_ref   = var.tenant_ref
  uuid         = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "case_id" {
  description = "returns a string"
  value       = avi_portalfileupload.this.case_id
}

output "error" {
  description = "returns a string"
  value       = avi_portalfileupload.this.error
}

output "file_path" {
  description = "returns a string"
  value       = avi_portalfileupload.this.file_path
}

output "id" {
  description = "returns a string"
  value       = avi_portalfileupload.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_portalfileupload.this.name
}

output "s3_directory" {
  description = "returns a string"
  value       = avi_portalfileupload.this.s3_directory
}

output "status" {
  description = "returns a string"
  value       = avi_portalfileupload.this.status
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_portalfileupload.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_portalfileupload.this.uuid
}

output "this" {
  value = avi_portalfileupload.this
}
```

[top](#index)