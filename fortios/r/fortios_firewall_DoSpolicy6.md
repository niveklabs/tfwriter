# fortios_firewall_DoSpolicy6

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
module "fortios_firewall_DoSpolicy6" {
  source = "./modules/fortios/r/fortios_firewall_DoSpolicy6"

  # comments - (optional) is a type of string
  comments = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # interface - (required) is a type of string
  interface = null
  # name - (optional) is a type of string
  name = null
  # policyid - (optional) is a type of number
  policyid = null
  # status - (optional) is a type of string
  status = null

  anomaly = [{
    action            = null
    log               = null
    name              = null
    quarantine        = null
    quarantine_expiry = null
    quarantine_log    = null
    status            = null
    threshold         = null
    thresholddefault  = null
  }]

  dstaddr = [{
    name = null
  }]

  service = [{
    name = null
  }]

  srcaddr = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policyid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "anomaly" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action            = string
      log               = string
      name              = string
      quarantine        = string
      quarantine_expiry = string
      quarantine_log    = string
      status            = string
      threshold         = number
      thresholddefault  = number
    }
  ))
  default = []
}

variable "dstaddr" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "service" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "srcaddr" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_DoSpolicy6" "this" {
  # comments - (optional) is a type of string
  comments = var.comments
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # interface - (required) is a type of string
  interface = var.interface
  # name - (optional) is a type of string
  name = var.name
  # policyid - (optional) is a type of number
  policyid = var.policyid
  # status - (optional) is a type of string
  status = var.status

  dynamic "anomaly" {
    for_each = var.anomaly
    content {
      # action - (optional) is a type of string
      action = anomaly.value["action"]
      # log - (optional) is a type of string
      log = anomaly.value["log"]
      # name - (optional) is a type of string
      name = anomaly.value["name"]
      # quarantine - (optional) is a type of string
      quarantine = anomaly.value["quarantine"]
      # quarantine_expiry - (optional) is a type of string
      quarantine_expiry = anomaly.value["quarantine_expiry"]
      # quarantine_log - (optional) is a type of string
      quarantine_log = anomaly.value["quarantine_log"]
      # status - (optional) is a type of string
      status = anomaly.value["status"]
      # threshold - (optional) is a type of number
      threshold = anomaly.value["threshold"]
      # thresholddefault - (optional) is a type of number
      thresholddefault = anomaly.value["thresholddefault"]
    }
  }

  dynamic "dstaddr" {
    for_each = var.dstaddr
    content {
      # name - (optional) is a type of string
      name = dstaddr.value["name"]
    }
  }

  dynamic "service" {
    for_each = var.service
    content {
      # name - (optional) is a type of string
      name = service.value["name"]
    }
  }

  dynamic "srcaddr" {
    for_each = var.srcaddr
    content {
      # name - (optional) is a type of string
      name = srcaddr.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_DoSpolicy6.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_DoSpolicy6.this.name
}

output "policyid" {
  description = "returns a number"
  value       = fortios_firewall_DoSpolicy6.this.policyid
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_DoSpolicy6.this.status
}

output "this" {
  value = fortios_firewall_DoSpolicy6.this
}
```

[top](#index)