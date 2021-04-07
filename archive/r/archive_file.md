# archive_file

[back](../archive.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    archive = ">= 2.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "archive_file" {
  source = [{
    content  = null
    filename = null
  }]

  # excludes - (optional) is a type of set of string
  excludes = []
  # output_path - (required) is a type of string
  output_path = null
  # source_content - (optional) is a type of string
  source_content = null
  # source_content_filename - (optional) is a type of string
  source_content_filename = null
  # source_dir - (optional) is a type of string
  source_dir = null
  # source_file - (optional) is a type of string
  source_file = null
  # type - (required) is a type of string
  type = null

}
```

[top](#index)

### Variables

```terraform
variable "excludes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "output_path" {
  description = "(required)"
  type        = string
}

variable "source_content" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_content_filename" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_dir" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "source" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      content  = string
      filename = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "archive_file" "this" {
  # excludes - (optional) is a type of set of string
  excludes = var.excludes
  # output_path - (required) is a type of string
  output_path = var.output_path
  # source_content - (optional) is a type of string
  source_content = var.source_content
  # source_content_filename - (optional) is a type of string
  source_content_filename = var.source_content_filename
  # source_dir - (optional) is a type of string
  source_dir = var.source_dir
  # source_file - (optional) is a type of string
  source_file = var.source_file
  # type - (required) is a type of string
  type = var.type

  dynamic "source" {
    for_each = var.source
    content {
      # content - (required) is a type of string
      content = source.value["content"]
      # filename - (required) is a type of string
      filename = source.value["filename"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = archive_file.this.id
}

output "output_base64sha256" {
  description = "returns a string"
  value       = archive_file.this.output_base64sha256
}

output "output_md5" {
  description = "returns a string"
  value       = archive_file.this.output_md5
}

output "output_sha" {
  description = "returns a string"
  value       = archive_file.this.output_sha
}

output "output_size" {
  description = "returns a number"
  value       = archive_file.this.output_size
}

output "this" {
  value = archive_file.this
}
```

[top](#index)