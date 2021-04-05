# thunder_slb_template_dblb

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
module "thunder_slb_template_dblb" {
  source = "./modules/thunder/r/thunder_slb_template_dblb"

  # class_list - (optional) is a type of string
  class_list = null
  # name - (optional) is a type of string
  name = null
  # server_version - (optional) is a type of string
  server_version = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  calc_sha1 = [{
    sha1_value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "class_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_version" {
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

variable "calc_sha1" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      sha1_value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_dblb" "this" {
  class_list     = var.class_list
  name           = var.name
  server_version = var.server_version
  user_tag       = var.user_tag
  uuid           = var.uuid

  dynamic "calc_sha1" {
    for_each = var.calc_sha1
    content {
      sha1_value = calc_sha1.value["sha1_value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_dblb.this.id
}

output "this" {
  value = thunder_slb_template_dblb.this
}
```

[top](#index)