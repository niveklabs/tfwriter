# thunder_slb_template_fix

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
module "thunder_slb_template_fix" {
  source = "./modules/thunder/r/thunder_slb_template_fix"

  # insert_client_ip - (optional) is a type of number
  insert_client_ip = null
  # logging - (optional) is a type of string
  logging = null
  # name - (optional) is a type of string
  name = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  tag_switching = [{
    equals         = null
    service_group  = null
    switching_type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "insert_client_ip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "logging" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "tag_switching" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      equals         = string
      service_group  = string
      switching_type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_fix" "this" {
  # insert_client_ip - (optional) is a type of number
  insert_client_ip = var.insert_client_ip
  # logging - (optional) is a type of string
  logging = var.logging
  # name - (optional) is a type of string
  name = var.name
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "tag_switching" {
    for_each = var.tag_switching
    content {
      # equals - (optional) is a type of string
      equals = tag_switching.value["equals"]
      # service_group - (optional) is a type of string
      service_group = tag_switching.value["service_group"]
      # switching_type - (optional) is a type of string
      switching_type = tag_switching.value["switching_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_fix.this.id
}

output "this" {
  value = thunder_slb_template_fix.this
}
```

[top](#index)