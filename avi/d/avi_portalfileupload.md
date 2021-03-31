# avi_portalfileupload

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
module "avi_portalfileupload" {
  source = "./modules/avi/d/avi_portalfileupload"

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
data "avi_portalfileupload" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "case_id" {
  description = "returns a string"
  value       = data.avi_portalfileupload.this.case_id
}

output "error" {
  description = "returns a string"
  value       = data.avi_portalfileupload.this.error
}

output "file_path" {
  description = "returns a string"
  value       = data.avi_portalfileupload.this.file_path
}

output "id" {
  description = "returns a string"
  value       = data.avi_portalfileupload.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_portalfileupload.this.name
}

output "s3_directory" {
  description = "returns a string"
  value       = data.avi_portalfileupload.this.s3_directory
}

output "status" {
  description = "returns a string"
  value       = data.avi_portalfileupload.this.status
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_portalfileupload.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_portalfileupload.this.uuid
}

output "this" {
  value = avi_portalfileupload.this
}
```

[top](#index)