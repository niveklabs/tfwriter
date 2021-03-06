# local_file

[back](../local.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    local = ">= 2.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "local_file" {
  source = null

  # content - (optional) is a type of string
  content = null
  # content_base64 - (optional) is a type of string
  content_base64 = null
  # directory_permission - (optional) is a type of string
  directory_permission = null
  # file_permission - (optional) is a type of string
  file_permission = null
  # filename - (required) is a type of string
  filename = null
  # sensitive_content - (optional) is a type of string
  sensitive_content = null
  # source - (optional) is a type of string
}
```

[top](#index)

### Variables

```terraform
variable "content" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "content_base64" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "directory_permission" {
  description = "(optional) - Permissions to set for directories created"
  type        = string
  default     = null
}

variable "file_permission" {
  description = "(optional) - Permissions to set for the output file"
  type        = string
  default     = null
}

variable "filename" {
  description = "(required) - Path to the output file"
  type        = string
}

variable "sensitive_content" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source" {
  description = "(optional) - Path to file to use as source for content of output file"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "local_file" "this" {
  # content - (optional) is a type of string
  content = var.content
  # content_base64 - (optional) is a type of string
  content_base64 = var.content_base64
  # directory_permission - (optional) is a type of string
  directory_permission = var.directory_permission
  # file_permission - (optional) is a type of string
  file_permission = var.file_permission
  # filename - (required) is a type of string
  filename = var.filename
  # sensitive_content - (optional) is a type of string
  sensitive_content = var.sensitive_content
  # source - (optional) is a type of string
  source = var.source
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = local_file.this.id
}

output "this" {
  value = local_file.this
}
```

[top](#index)