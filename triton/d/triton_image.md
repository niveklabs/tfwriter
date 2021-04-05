# triton_image

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    triton = ">= 0.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "triton_image" {
  source = "./modules/triton/d/triton_image"

  # most_recent - (optional) is a type of bool
  most_recent = null
  # name - (optional) is a type of string
  name = null
  # os - (optional) is a type of string
  os = null
  # owner - (optional) is a type of string
  owner = null
  # public - (optional) is a type of bool
  public = null
  # state - (optional) is a type of string
  state = null
  # type - (optional) is a type of string
  type = null
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "most_recent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "triton_image" "this" {
  most_recent = var.most_recent
  name        = var.name
  os          = var.os
  owner       = var.owner
  public      = var.public
  state       = var.state
  type        = var.type
  version     = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.triton_image.this.id
}

output "this" {
  value = triton_image.this
}
```

[top](#index)