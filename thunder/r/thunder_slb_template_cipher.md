# thunder_slb_template_cipher

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_template_cipher" {
  source = "./modules/thunder/r/thunder_slb_template_cipher"

  # name - (optional) is a type of string
  name = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  cipher_cfg = [{
    cipher_suite = null
    priority     = null
  }]
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

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cipher_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cipher_suite = string
      priority     = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_cipher" "this" {
  name     = var.name
  user_tag = var.user_tag
  uuid     = var.uuid

  dynamic "cipher_cfg" {
    for_each = var.cipher_cfg
    content {
      cipher_suite = cipher_cfg.value["cipher_suite"]
      priority     = cipher_cfg.value["priority"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_cipher.this.id
}

output "this" {
  value = thunder_slb_template_cipher.this
}
```

[top](#index)