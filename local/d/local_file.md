# local_file

[back](../local.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/local/d/local_file"

  # filename - (required) is a type of string
  filename = null
}
```

[top](#index)

### Variables

```terraform
variable "filename" {
  description = "(required) - Path to the output file"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "local_file" "this" {
  filename = var.filename
}
```

[top](#index)

### Outputs

```terraform
output "content" {
  description = "returns a string"
  value       = data.local_file.this.content
}

output "content_base64" {
  description = "returns a string"
  value       = data.local_file.this.content_base64
}

output "id" {
  description = "returns a string"
  value       = data.local_file.this.id
}

output "this" {
  value = local_file.this
}
```

[top](#index)