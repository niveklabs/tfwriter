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
    fortios = ">= 1.6.18"
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
  # interface - (required) is a type of string
  interface = null
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

variable "interface" {
  description = "(required)"
  type        = string
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
  comments  = var.comments
  interface = var.interface
  policyid  = var.policyid
  status    = var.status

  dynamic "anomaly" {
    for_each = var.anomaly
    content {
      action            = anomaly.value["action"]
      log               = anomaly.value["log"]
      name              = anomaly.value["name"]
      quarantine        = anomaly.value["quarantine"]
      quarantine_expiry = anomaly.value["quarantine_expiry"]
      quarantine_log    = anomaly.value["quarantine_log"]
      status            = anomaly.value["status"]
      threshold         = anomaly.value["threshold"]
      thresholddefault  = anomaly.value["thresholddefault"]
    }
  }

  dynamic "dstaddr" {
    for_each = var.dstaddr
    content {
      name = dstaddr.value["name"]
    }
  }

  dynamic "service" {
    for_each = var.service
    content {
      name = service.value["name"]
    }
  }

  dynamic "srcaddr" {
    for_each = var.srcaddr
    content {
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