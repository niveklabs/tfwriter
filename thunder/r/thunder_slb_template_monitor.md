# thunder_slb_template_monitor

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
module "thunder_slb_template_monitor" {
  source = "./modules/thunder/r/thunder_slb_template_monitor"

  # id2 - (optional) is a type of number
  id2 = null
  # monitor_relation - (optional) is a type of string
  monitor_relation = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  clear_cfg = [{
    clear_all_sequence = null
    clear_sequence     = null
    sessions           = null
  }]

  link_disable_cfg = [{
    dis_sequence = null
    diseth       = null
  }]

  link_down_cfg = [{
    link_down_sequence1 = null
    link_down_sequence2 = null
    link_down_sequence3 = null
    linkdown_ethernet1  = null
    linkdown_ethernet2  = null
    linkdown_ethernet3  = null
  }]

  link_enable_cfg = [{
    ena_sequence = null
    enaeth       = null
  }]

  link_up_cfg = [{
    link_up_sequence1 = null
    link_up_sequence2 = null
    link_up_sequence3 = null
    linkup_ethernet1  = null
    linkup_ethernet2  = null
    linkup_ethernet3  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "id2" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "monitor_relation" {
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

variable "clear_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      clear_all_sequence = number
      clear_sequence     = number
      sessions           = string
    }
  ))
  default = []
}

variable "link_disable_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      dis_sequence = number
      diseth       = number
    }
  ))
  default = []
}

variable "link_down_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      link_down_sequence1 = number
      link_down_sequence2 = number
      link_down_sequence3 = number
      linkdown_ethernet1  = number
      linkdown_ethernet2  = number
      linkdown_ethernet3  = number
    }
  ))
  default = []
}

variable "link_enable_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ena_sequence = number
      enaeth       = number
    }
  ))
  default = []
}

variable "link_up_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      link_up_sequence1 = number
      link_up_sequence2 = number
      link_up_sequence3 = number
      linkup_ethernet1  = number
      linkup_ethernet2  = number
      linkup_ethernet3  = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_monitor" "this" {
  # id2 - (optional) is a type of number
  id2 = var.id2
  # monitor_relation - (optional) is a type of string
  monitor_relation = var.monitor_relation
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "clear_cfg" {
    for_each = var.clear_cfg
    content {
      # clear_all_sequence - (optional) is a type of number
      clear_all_sequence = clear_cfg.value["clear_all_sequence"]
      # clear_sequence - (optional) is a type of number
      clear_sequence = clear_cfg.value["clear_sequence"]
      # sessions - (optional) is a type of string
      sessions = clear_cfg.value["sessions"]
    }
  }

  dynamic "link_disable_cfg" {
    for_each = var.link_disable_cfg
    content {
      # dis_sequence - (optional) is a type of number
      dis_sequence = link_disable_cfg.value["dis_sequence"]
      # diseth - (optional) is a type of number
      diseth = link_disable_cfg.value["diseth"]
    }
  }

  dynamic "link_down_cfg" {
    for_each = var.link_down_cfg
    content {
      # link_down_sequence1 - (optional) is a type of number
      link_down_sequence1 = link_down_cfg.value["link_down_sequence1"]
      # link_down_sequence2 - (optional) is a type of number
      link_down_sequence2 = link_down_cfg.value["link_down_sequence2"]
      # link_down_sequence3 - (optional) is a type of number
      link_down_sequence3 = link_down_cfg.value["link_down_sequence3"]
      # linkdown_ethernet1 - (optional) is a type of number
      linkdown_ethernet1 = link_down_cfg.value["linkdown_ethernet1"]
      # linkdown_ethernet2 - (optional) is a type of number
      linkdown_ethernet2 = link_down_cfg.value["linkdown_ethernet2"]
      # linkdown_ethernet3 - (optional) is a type of number
      linkdown_ethernet3 = link_down_cfg.value["linkdown_ethernet3"]
    }
  }

  dynamic "link_enable_cfg" {
    for_each = var.link_enable_cfg
    content {
      # ena_sequence - (optional) is a type of number
      ena_sequence = link_enable_cfg.value["ena_sequence"]
      # enaeth - (optional) is a type of number
      enaeth = link_enable_cfg.value["enaeth"]
    }
  }

  dynamic "link_up_cfg" {
    for_each = var.link_up_cfg
    content {
      # link_up_sequence1 - (optional) is a type of number
      link_up_sequence1 = link_up_cfg.value["link_up_sequence1"]
      # link_up_sequence2 - (optional) is a type of number
      link_up_sequence2 = link_up_cfg.value["link_up_sequence2"]
      # link_up_sequence3 - (optional) is a type of number
      link_up_sequence3 = link_up_cfg.value["link_up_sequence3"]
      # linkup_ethernet1 - (optional) is a type of number
      linkup_ethernet1 = link_up_cfg.value["linkup_ethernet1"]
      # linkup_ethernet2 - (optional) is a type of number
      linkup_ethernet2 = link_up_cfg.value["linkup_ethernet2"]
      # linkup_ethernet3 - (optional) is a type of number
      linkup_ethernet3 = link_up_cfg.value["linkup_ethernet3"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_monitor.this.id
}

output "this" {
  value = thunder_slb_template_monitor.this
}
```

[top](#index)