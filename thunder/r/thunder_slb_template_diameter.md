# thunder_slb_template_diameter

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
module "thunder_slb_template_diameter" {
  source = "./modules/thunder/r/thunder_slb_template_diameter"

  # avp_code - (optional) is a type of number
  avp_code = null
  # avp_string - (optional) is a type of string
  avp_string = null
  # customize_cea - (optional) is a type of number
  customize_cea = null
  # dwr_time - (optional) is a type of number
  dwr_time = null
  # dwr_up_retry - (optional) is a type of number
  dwr_up_retry = null
  # forward_to_latest_server - (optional) is a type of number
  forward_to_latest_server = null
  # forward_unknown_session_id - (optional) is a type of number
  forward_unknown_session_id = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # load_balance_on_session_id - (optional) is a type of number
  load_balance_on_session_id = null
  # multiple_origin_host - (optional) is a type of number
  multiple_origin_host = null
  # name - (optional) is a type of string
  name = null
  # origin_realm - (optional) is a type of string
  origin_realm = null
  # product_name - (optional) is a type of string
  product_name = null
  # service_group_name - (optional) is a type of string
  service_group_name = null
  # session_age - (optional) is a type of number
  session_age = null
  # terminate_on_cca_t - (optional) is a type of number
  terminate_on_cca_t = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
  # vendor_id - (optional) is a type of number
  vendor_id = null

  avp_list = [{
    avp       = null
    int32     = null
    int64     = null
    mandatory = null
    string    = null
  }]

  message_code_list = [{
    message_code = null
  }]

  origin_host = [{
    origin_host_name = null
    uuid             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "avp_code" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "avp_string" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "customize_cea" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dwr_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dwr_up_retry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_to_latest_server" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward_unknown_session_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "load_balance_on_session_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "multiple_origin_host" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "origin_realm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "product_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_age" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "terminate_on_cca_t" {
  description = "(optional)"
  type        = number
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

variable "vendor_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "avp_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      avp       = number
      int32     = number
      int64     = number
      mandatory = number
      string    = string
    }
  ))
  default = []
}

variable "message_code_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      message_code = number
    }
  ))
  default = []
}

variable "origin_host" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      origin_host_name = string
      uuid             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_diameter" "this" {
  avp_code                   = var.avp_code
  avp_string                 = var.avp_string
  customize_cea              = var.customize_cea
  dwr_time                   = var.dwr_time
  dwr_up_retry               = var.dwr_up_retry
  forward_to_latest_server   = var.forward_to_latest_server
  forward_unknown_session_id = var.forward_unknown_session_id
  idle_timeout               = var.idle_timeout
  load_balance_on_session_id = var.load_balance_on_session_id
  multiple_origin_host       = var.multiple_origin_host
  name                       = var.name
  origin_realm               = var.origin_realm
  product_name               = var.product_name
  service_group_name         = var.service_group_name
  session_age                = var.session_age
  terminate_on_cca_t         = var.terminate_on_cca_t
  user_tag                   = var.user_tag
  uuid                       = var.uuid
  vendor_id                  = var.vendor_id

  dynamic "avp_list" {
    for_each = var.avp_list
    content {
      avp       = avp_list.value["avp"]
      int32     = avp_list.value["int32"]
      int64     = avp_list.value["int64"]
      mandatory = avp_list.value["mandatory"]
      string    = avp_list.value["string"]
    }
  }

  dynamic "message_code_list" {
    for_each = var.message_code_list
    content {
      message_code = message_code_list.value["message_code"]
    }
  }

  dynamic "origin_host" {
    for_each = var.origin_host
    content {
      origin_host_name = origin_host.value["origin_host_name"]
      uuid             = origin_host.value["uuid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_diameter.this.id
}

output "this" {
  value = thunder_slb_template_diameter.this
}
```

[top](#index)