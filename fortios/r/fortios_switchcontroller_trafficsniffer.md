# fortios_switchcontroller_trafficsniffer

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
module "fortios_switchcontroller_trafficsniffer" {
  source = "./modules/fortios/r/fortios_switchcontroller_trafficsniffer"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # erspan_ip - (optional) is a type of string
  erspan_ip = null
  # mode - (optional) is a type of string
  mode = null

  target_ip = [{
    description = null
    ip          = null
  }]

  target_mac = [{
    description = null
    mac         = null
  }]

  target_port = [{
    description = null
    in_ports = [{
      name = null
    }]
    out_ports = [{
      name = null
    }]
    switch_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "erspan_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_ip" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      ip          = string
    }
  ))
  default = []
}

variable "target_mac" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      mac         = string
    }
  ))
  default = []
}

variable "target_port" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      in_ports = list(object(
        {
          name = string
        }
      ))
      out_ports = list(object(
        {
          name = string
        }
      ))
      switch_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_trafficsniffer" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # erspan_ip - (optional) is a type of string
  erspan_ip = var.erspan_ip
  # mode - (optional) is a type of string
  mode = var.mode

  dynamic "target_ip" {
    for_each = var.target_ip
    content {
      # description - (optional) is a type of string
      description = target_ip.value["description"]
      # ip - (optional) is a type of string
      ip = target_ip.value["ip"]
    }
  }

  dynamic "target_mac" {
    for_each = var.target_mac
    content {
      # description - (optional) is a type of string
      description = target_mac.value["description"]
      # mac - (optional) is a type of string
      mac = target_mac.value["mac"]
    }
  }

  dynamic "target_port" {
    for_each = var.target_port
    content {
      # description - (optional) is a type of string
      description = target_port.value["description"]
      # switch_id - (optional) is a type of string
      switch_id = target_port.value["switch_id"]

      dynamic "in_ports" {
        for_each = target_port.value.in_ports
        content {
          # name - (optional) is a type of string
          name = in_ports.value["name"]
        }
      }

      dynamic "out_ports" {
        for_each = target_port.value.out_ports
        content {
          # name - (optional) is a type of string
          name = out_ports.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "erspan_ip" {
  description = "returns a string"
  value       = fortios_switchcontroller_trafficsniffer.this.erspan_ip
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_trafficsniffer.this.id
}

output "mode" {
  description = "returns a string"
  value       = fortios_switchcontroller_trafficsniffer.this.mode
}

output "this" {
  value = fortios_switchcontroller_trafficsniffer.this
}
```

[top](#index)