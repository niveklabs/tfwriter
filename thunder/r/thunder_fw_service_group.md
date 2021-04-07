# thunder_fw_service_group

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
module "thunder_fw_service_group" {
  source = "./modules/thunder/r/thunder_fw_service_group"

  # health_check - (optional) is a type of string
  health_check = null
  # name - (optional) is a type of string
  name = null
  # protocol - (optional) is a type of string
  protocol = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  member_list = [{
    name = null
    port = null
    sampling_enable = [{
      counters1 = null
    }]
    user_tag = null
    uuid     = null
  }]

  sampling_enable = [{
    counters1 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "health_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
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

variable "member_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
      port = number
      sampling_enable = list(object(
        {
          counters1 = string
        }
      ))
      user_tag = string
      uuid     = string
    }
  ))
  default = []
}

variable "sampling_enable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      counters1 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_fw_service_group" "this" {
  # health_check - (optional) is a type of string
  health_check = var.health_check
  # name - (optional) is a type of string
  name = var.name
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "member_list" {
    for_each = var.member_list
    content {
      # name - (optional) is a type of string
      name = member_list.value["name"]
      # port - (optional) is a type of number
      port = member_list.value["port"]
      # user_tag - (optional) is a type of string
      user_tag = member_list.value["user_tag"]
      # uuid - (optional) is a type of string
      uuid = member_list.value["uuid"]

      dynamic "sampling_enable" {
        for_each = member_list.value.sampling_enable
        content {
          # counters1 - (optional) is a type of string
          counters1 = sampling_enable.value["counters1"]
        }
      }

    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      # counters1 - (optional) is a type of string
      counters1 = sampling_enable.value["counters1"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_service_group.this.id
}

output "this" {
  value = thunder_fw_service_group.this
}
```

[top](#index)