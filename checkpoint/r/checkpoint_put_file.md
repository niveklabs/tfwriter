# checkpoint_put_file

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_put_file" {
  source = "./modules/checkpoint/r/checkpoint_put_file"

  # file_name - (required) is a type of string
  file_name = null
  # override - (optional) is a type of bool
  override = null
  # text_content - (required) is a type of string
  text_content = null
}
```

[top](#index)

### Variables

```terraform
variable "file_name" {
  description = "(required) - Filename include the desired path. The file will be created in the user home directory if the full path wasn't provided"
  type        = string
}

variable "override" {
  description = "(optional) - comments"
  type        = bool
  default     = null
}

variable "text_content" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_put_file" "this" {
  # file_name - (required) is a type of string
  file_name = var.file_name
  # override - (optional) is a type of bool
  override = var.override
  # text_content - (required) is a type of string
  text_content = var.text_content
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_put_file.this.id
}

output "this" {
  value = checkpoint_put_file.this
}
```

[top](#index)