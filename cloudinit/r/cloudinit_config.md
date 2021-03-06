# cloudinit_config

[back](../cloudinit.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudinit = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudinit_config" {
  source = "./modules/cloudinit/r/cloudinit_config"

  # base64_encode - (optional) is a type of bool
  base64_encode = null
  # boundary - (optional) is a type of string
  boundary = null
  # gzip - (optional) is a type of bool
  gzip = null

  part = [{
    content      = null
    content_type = null
    filename     = null
    merge_type   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "base64_encode" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "boundary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gzip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "part" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      content      = string
      content_type = string
      filename     = string
      merge_type   = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "cloudinit_config" "this" {
  # base64_encode - (optional) is a type of bool
  base64_encode = var.base64_encode
  # boundary - (optional) is a type of string
  boundary = var.boundary
  # gzip - (optional) is a type of bool
  gzip = var.gzip

  dynamic "part" {
    for_each = var.part
    content {
      # content - (required) is a type of string
      content = part.value["content"]
      # content_type - (optional) is a type of string
      content_type = part.value["content_type"]
      # filename - (optional) is a type of string
      filename = part.value["filename"]
      # merge_type - (optional) is a type of string
      merge_type = part.value["merge_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudinit_config.this.id
}

output "rendered" {
  description = "returns a string"
  value       = cloudinit_config.this.rendered
}

output "this" {
  value = cloudinit_config.this
}
```

[top](#index)