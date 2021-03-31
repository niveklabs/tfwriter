# alicloud_alidns_record

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_alidns_record" {
  source = "./modules/alicloud/r/alicloud_alidns_record"

  # domain_name - (required) is a type of string
  domain_name = null
  # lang - (optional) is a type of string
  lang = null
  # line - (optional) is a type of string
  line = null
  # priority - (optional) is a type of number
  priority = null
  # remark - (optional) is a type of string
  remark = null
  # rr - (required) is a type of string
  rr = null
  # status - (optional) is a type of string
  status = null
  # ttl - (optional) is a type of number
  ttl = null
  # type - (required) is a type of string
  type = null
  # user_client_ip - (optional) is a type of string
  user_client_ip = null
  # value - (required) is a type of string
  value = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "line" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "remark" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rr" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "user_client_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_alidns_record" "this" {
  domain_name    = var.domain_name
  lang           = var.lang
  line           = var.line
  priority       = var.priority
  remark         = var.remark
  rr             = var.rr
  status         = var.status
  ttl            = var.ttl
  type           = var.type
  user_client_ip = var.user_client_ip
  value          = var.value

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_alidns_record.this.id
}

output "this" {
  value = alicloud_alidns_record.this
}
```

[top](#index)