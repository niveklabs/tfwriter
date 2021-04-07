# fortios_extendercontroller_extender1

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_extendercontroller_extender1" {
  source = "./modules/fortios/r/fortios_extendercontroller_extender1"

  # authorized - (required) is a type of string
  authorized = null
  # description - (optional) is a type of string
  description = null
  # ext_name - (optional) is a type of string
  ext_name = null
  # fosid - (optional) is a type of string
  fosid = null
  # login_password - (optional) is a type of string
  login_password = null
  # name - (required) is a type of string
  name = null
  # vdom - (optional) is a type of number
  vdom = null

  controller_report = [{
    interval         = null
    signal_threshold = null
    status           = null
  }]

  modem1 = [{
    auto_switch = [{
      dataplan             = null
      disconnect           = null
      disconnect_period    = null
      disconnect_threshold = null
      signal               = null
      switch_back          = null
      switch_back_time     = null
      switch_back_timer    = null
    }]
    conn_status       = null
    default_sim       = null
    gps               = null
    ifname            = null
    preferred_carrier = null
    redundant_intf    = null
    redundant_mode    = null
    sim1_pin          = null
    sim1_pin_code     = null
    sim2_pin          = null
    sim2_pin_code     = null
  }]

  modem2 = [{
    auto_switch = [{
      dataplan             = null
      disconnect           = null
      disconnect_period    = null
      disconnect_threshold = null
      signal               = null
      switch_back          = null
      switch_back_time     = null
      switch_back_timer    = null
    }]
    conn_status       = null
    default_sim       = null
    gps               = null
    ifname            = null
    preferred_carrier = null
    redundant_intf    = null
    redundant_mode    = null
    sim1_pin          = null
    sim1_pin_code     = null
    sim2_pin          = null
    sim2_pin_code     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authorized" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ext_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "login_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "vdom" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "controller_report" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      interval         = number
      signal_threshold = number
      status           = string
    }
  ))
  default = []
}

variable "modem1" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_switch = list(object(
        {
          dataplan             = string
          disconnect           = string
          disconnect_period    = number
          disconnect_threshold = number
          signal               = string
          switch_back          = string
          switch_back_time     = string
          switch_back_timer    = number
        }
      ))
      conn_status       = number
      default_sim       = string
      gps               = string
      ifname            = string
      preferred_carrier = string
      redundant_intf    = string
      redundant_mode    = string
      sim1_pin          = string
      sim1_pin_code     = string
      sim2_pin          = string
      sim2_pin_code     = string
    }
  ))
  default = []
}

variable "modem2" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_switch = list(object(
        {
          dataplan             = string
          disconnect           = string
          disconnect_period    = number
          disconnect_threshold = number
          signal               = string
          switch_back          = string
          switch_back_time     = string
          switch_back_timer    = number
        }
      ))
      conn_status       = number
      default_sim       = string
      gps               = string
      ifname            = string
      preferred_carrier = string
      redundant_intf    = string
      redundant_mode    = string
      sim1_pin          = string
      sim1_pin_code     = string
      sim2_pin          = string
      sim2_pin_code     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_extendercontroller_extender1" "this" {
  # authorized - (required) is a type of string
  authorized = var.authorized
  # description - (optional) is a type of string
  description = var.description
  # ext_name - (optional) is a type of string
  ext_name = var.ext_name
  # fosid - (optional) is a type of string
  fosid = var.fosid
  # login_password - (optional) is a type of string
  login_password = var.login_password
  # name - (required) is a type of string
  name = var.name
  # vdom - (optional) is a type of number
  vdom = var.vdom

  dynamic "controller_report" {
    for_each = var.controller_report
    content {
      # interval - (optional) is a type of number
      interval = controller_report.value["interval"]
      # signal_threshold - (optional) is a type of number
      signal_threshold = controller_report.value["signal_threshold"]
      # status - (optional) is a type of string
      status = controller_report.value["status"]
    }
  }

  dynamic "modem1" {
    for_each = var.modem1
    content {
      # conn_status - (optional) is a type of number
      conn_status = modem1.value["conn_status"]
      # default_sim - (optional) is a type of string
      default_sim = modem1.value["default_sim"]
      # gps - (optional) is a type of string
      gps = modem1.value["gps"]
      # ifname - (optional) is a type of string
      ifname = modem1.value["ifname"]
      # preferred_carrier - (optional) is a type of string
      preferred_carrier = modem1.value["preferred_carrier"]
      # redundant_intf - (optional) is a type of string
      redundant_intf = modem1.value["redundant_intf"]
      # redundant_mode - (optional) is a type of string
      redundant_mode = modem1.value["redundant_mode"]
      # sim1_pin - (optional) is a type of string
      sim1_pin = modem1.value["sim1_pin"]
      # sim1_pin_code - (optional) is a type of string
      sim1_pin_code = modem1.value["sim1_pin_code"]
      # sim2_pin - (optional) is a type of string
      sim2_pin = modem1.value["sim2_pin"]
      # sim2_pin_code - (optional) is a type of string
      sim2_pin_code = modem1.value["sim2_pin_code"]

      dynamic "auto_switch" {
        for_each = modem1.value.auto_switch
        content {
          # dataplan - (optional) is a type of string
          dataplan = auto_switch.value["dataplan"]
          # disconnect - (optional) is a type of string
          disconnect = auto_switch.value["disconnect"]
          # disconnect_period - (optional) is a type of number
          disconnect_period = auto_switch.value["disconnect_period"]
          # disconnect_threshold - (optional) is a type of number
          disconnect_threshold = auto_switch.value["disconnect_threshold"]
          # signal - (optional) is a type of string
          signal = auto_switch.value["signal"]
          # switch_back - (optional) is a type of string
          switch_back = auto_switch.value["switch_back"]
          # switch_back_time - (optional) is a type of string
          switch_back_time = auto_switch.value["switch_back_time"]
          # switch_back_timer - (optional) is a type of number
          switch_back_timer = auto_switch.value["switch_back_timer"]
        }
      }

    }
  }

  dynamic "modem2" {
    for_each = var.modem2
    content {
      # conn_status - (optional) is a type of number
      conn_status = modem2.value["conn_status"]
      # default_sim - (optional) is a type of string
      default_sim = modem2.value["default_sim"]
      # gps - (optional) is a type of string
      gps = modem2.value["gps"]
      # ifname - (optional) is a type of string
      ifname = modem2.value["ifname"]
      # preferred_carrier - (optional) is a type of string
      preferred_carrier = modem2.value["preferred_carrier"]
      # redundant_intf - (optional) is a type of string
      redundant_intf = modem2.value["redundant_intf"]
      # redundant_mode - (optional) is a type of string
      redundant_mode = modem2.value["redundant_mode"]
      # sim1_pin - (optional) is a type of string
      sim1_pin = modem2.value["sim1_pin"]
      # sim1_pin_code - (optional) is a type of string
      sim1_pin_code = modem2.value["sim1_pin_code"]
      # sim2_pin - (optional) is a type of string
      sim2_pin = modem2.value["sim2_pin"]
      # sim2_pin_code - (optional) is a type of string
      sim2_pin_code = modem2.value["sim2_pin_code"]

      dynamic "auto_switch" {
        for_each = modem2.value.auto_switch
        content {
          # dataplan - (optional) is a type of string
          dataplan = auto_switch.value["dataplan"]
          # disconnect - (optional) is a type of string
          disconnect = auto_switch.value["disconnect"]
          # disconnect_period - (optional) is a type of number
          disconnect_period = auto_switch.value["disconnect_period"]
          # disconnect_threshold - (optional) is a type of number
          disconnect_threshold = auto_switch.value["disconnect_threshold"]
          # signal - (optional) is a type of string
          signal = auto_switch.value["signal"]
          # switch_back - (optional) is a type of string
          switch_back = auto_switch.value["switch_back"]
          # switch_back_time - (optional) is a type of string
          switch_back_time = auto_switch.value["switch_back_time"]
          # switch_back_timer - (optional) is a type of number
          switch_back_timer = auto_switch.value["switch_back_timer"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender1.this.description
}

output "ext_name" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender1.this.ext_name
}

output "fosid" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender1.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender1.this.id
}

output "vdom" {
  description = "returns a number"
  value       = fortios_extendercontroller_extender1.this.vdom
}

output "this" {
  value = fortios_extendercontroller_extender1.this
}
```

[top](#index)