# avi_fileservice

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
module "avi_fileservice" {
  source = "./modules/avi/d/avi_fileservice"

  # local_file - (required) is a type of string
  local_file = null
  # upload - (optional) is a type of bool
  upload = null
  # uri - (required) is a type of string
  uri = null
}
```

[top](#index)

### Variables

```terraform
variable "local_file" {
  description = "(required)"
  type        = string
}

variable "upload" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "uri" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "avi_fileservice" "this" {
  # local_file - (required) is a type of string
  local_file = var.local_file
  # upload - (optional) is a type of bool
  upload = var.upload
  # uri - (required) is a type of string
  uri = var.uri
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.avi_fileservice.this.id
}

output "this" {
  value = avi_fileservice.this
}
```

[top](#index)