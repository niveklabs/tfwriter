# thunder_slb_template_sip

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
module "thunder_slb_template_sip" {
  source = "./modules/thunder/r/thunder_slb_template_sip"

  # acl_id - (optional) is a type of number
  acl_id = null
  # acl_name_value - (optional) is a type of string
  acl_name_value = null
  # alg_dest_nat - (optional) is a type of number
  alg_dest_nat = null
  # alg_source_nat - (optional) is a type of number
  alg_source_nat = null
  # call_id_persist_disable - (optional) is a type of number
  call_id_persist_disable = null
  # client_keep_alive - (optional) is a type of number
  client_keep_alive = null
  # dialog_aware - (optional) is a type of number
  dialog_aware = null
  # drop_when_client_fail - (optional) is a type of number
  drop_when_client_fail = null
  # drop_when_server_fail - (optional) is a type of number
  drop_when_server_fail = null
  # failed_client_selection - (optional) is a type of number
  failed_client_selection = null
  # failed_client_selection_message - (optional) is a type of string
  failed_client_selection_message = null
  # failed_server_selection - (optional) is a type of number
  failed_server_selection = null
  # failed_server_selection_message - (optional) is a type of string
  failed_server_selection_message = null
  # insert_client_ip - (optional) is a type of number
  insert_client_ip = null
  # interval - (optional) is a type of number
  interval = null
  # keep_server_ip_if_match_acl - (optional) is a type of number
  keep_server_ip_if_match_acl = null
  # name - (optional) is a type of string
  name = null
  # pstn_gw - (optional) is a type of string
  pstn_gw = null
  # server_keep_alive - (optional) is a type of number
  server_keep_alive = null
  # server_selection_per_request - (optional) is a type of number
  server_selection_per_request = null
  # service_group - (optional) is a type of string
  service_group = null
  # smp_call_id_rtp_session - (optional) is a type of number
  smp_call_id_rtp_session = null
  # timeout - (optional) is a type of number
  timeout = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  client_request_header = [{
    client_request_erase_all        = null
    client_request_header_erase     = null
    client_request_header_insert    = null
    insert_condition_client_request = null
  }]

  client_response_header = [{
    client_response_erase_all        = null
    client_response_header_erase     = null
    client_response_header_insert    = null
    insert_condition_client_response = null
  }]

  exclude_translation = [{
    header_string     = null
    translation_value = null
  }]

  server_request_header = [{
    insert_condition_server_request = null
    server_request_erase_all        = null
    server_request_header_erase     = null
    server_request_header_insert    = null
  }]

  server_response_header = [{
    insert_condition_server_response = null
    server_response_erase_all        = null
    server_response_header_erase     = null
    server_response_header_insert    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acl_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "acl_name_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alg_dest_nat" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "alg_source_nat" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "call_id_persist_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "client_keep_alive" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dialog_aware" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "drop_when_client_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "drop_when_server_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "failed_client_selection" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "failed_client_selection_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "failed_server_selection" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "failed_server_selection_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "insert_client_ip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "keep_server_ip_if_match_acl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pstn_gw" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_keep_alive" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_selection_per_request" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "smp_call_id_rtp_session" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout" {
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

variable "client_request_header" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      client_request_erase_all        = number
      client_request_header_erase     = string
      client_request_header_insert    = string
      insert_condition_client_request = string
    }
  ))
  default = []
}

variable "client_response_header" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      client_response_erase_all        = number
      client_response_header_erase     = string
      client_response_header_insert    = string
      insert_condition_client_response = string
    }
  ))
  default = []
}

variable "exclude_translation" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      header_string     = string
      translation_value = string
    }
  ))
  default = []
}

variable "server_request_header" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      insert_condition_server_request = string
      server_request_erase_all        = number
      server_request_header_erase     = string
      server_request_header_insert    = string
    }
  ))
  default = []
}

variable "server_response_header" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      insert_condition_server_response = string
      server_response_erase_all        = number
      server_response_header_erase     = string
      server_response_header_insert    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_sip" "this" {
  # acl_id - (optional) is a type of number
  acl_id = var.acl_id
  # acl_name_value - (optional) is a type of string
  acl_name_value = var.acl_name_value
  # alg_dest_nat - (optional) is a type of number
  alg_dest_nat = var.alg_dest_nat
  # alg_source_nat - (optional) is a type of number
  alg_source_nat = var.alg_source_nat
  # call_id_persist_disable - (optional) is a type of number
  call_id_persist_disable = var.call_id_persist_disable
  # client_keep_alive - (optional) is a type of number
  client_keep_alive = var.client_keep_alive
  # dialog_aware - (optional) is a type of number
  dialog_aware = var.dialog_aware
  # drop_when_client_fail - (optional) is a type of number
  drop_when_client_fail = var.drop_when_client_fail
  # drop_when_server_fail - (optional) is a type of number
  drop_when_server_fail = var.drop_when_server_fail
  # failed_client_selection - (optional) is a type of number
  failed_client_selection = var.failed_client_selection
  # failed_client_selection_message - (optional) is a type of string
  failed_client_selection_message = var.failed_client_selection_message
  # failed_server_selection - (optional) is a type of number
  failed_server_selection = var.failed_server_selection
  # failed_server_selection_message - (optional) is a type of string
  failed_server_selection_message = var.failed_server_selection_message
  # insert_client_ip - (optional) is a type of number
  insert_client_ip = var.insert_client_ip
  # interval - (optional) is a type of number
  interval = var.interval
  # keep_server_ip_if_match_acl - (optional) is a type of number
  keep_server_ip_if_match_acl = var.keep_server_ip_if_match_acl
  # name - (optional) is a type of string
  name = var.name
  # pstn_gw - (optional) is a type of string
  pstn_gw = var.pstn_gw
  # server_keep_alive - (optional) is a type of number
  server_keep_alive = var.server_keep_alive
  # server_selection_per_request - (optional) is a type of number
  server_selection_per_request = var.server_selection_per_request
  # service_group - (optional) is a type of string
  service_group = var.service_group
  # smp_call_id_rtp_session - (optional) is a type of number
  smp_call_id_rtp_session = var.smp_call_id_rtp_session
  # timeout - (optional) is a type of number
  timeout = var.timeout
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "client_request_header" {
    for_each = var.client_request_header
    content {
      # client_request_erase_all - (optional) is a type of number
      client_request_erase_all = client_request_header.value["client_request_erase_all"]
      # client_request_header_erase - (optional) is a type of string
      client_request_header_erase = client_request_header.value["client_request_header_erase"]
      # client_request_header_insert - (optional) is a type of string
      client_request_header_insert = client_request_header.value["client_request_header_insert"]
      # insert_condition_client_request - (optional) is a type of string
      insert_condition_client_request = client_request_header.value["insert_condition_client_request"]
    }
  }

  dynamic "client_response_header" {
    for_each = var.client_response_header
    content {
      # client_response_erase_all - (optional) is a type of number
      client_response_erase_all = client_response_header.value["client_response_erase_all"]
      # client_response_header_erase - (optional) is a type of string
      client_response_header_erase = client_response_header.value["client_response_header_erase"]
      # client_response_header_insert - (optional) is a type of string
      client_response_header_insert = client_response_header.value["client_response_header_insert"]
      # insert_condition_client_response - (optional) is a type of string
      insert_condition_client_response = client_response_header.value["insert_condition_client_response"]
    }
  }

  dynamic "exclude_translation" {
    for_each = var.exclude_translation
    content {
      # header_string - (optional) is a type of string
      header_string = exclude_translation.value["header_string"]
      # translation_value - (optional) is a type of string
      translation_value = exclude_translation.value["translation_value"]
    }
  }

  dynamic "server_request_header" {
    for_each = var.server_request_header
    content {
      # insert_condition_server_request - (optional) is a type of string
      insert_condition_server_request = server_request_header.value["insert_condition_server_request"]
      # server_request_erase_all - (optional) is a type of number
      server_request_erase_all = server_request_header.value["server_request_erase_all"]
      # server_request_header_erase - (optional) is a type of string
      server_request_header_erase = server_request_header.value["server_request_header_erase"]
      # server_request_header_insert - (optional) is a type of string
      server_request_header_insert = server_request_header.value["server_request_header_insert"]
    }
  }

  dynamic "server_response_header" {
    for_each = var.server_response_header
    content {
      # insert_condition_server_response - (optional) is a type of string
      insert_condition_server_response = server_response_header.value["insert_condition_server_response"]
      # server_response_erase_all - (optional) is a type of number
      server_response_erase_all = server_response_header.value["server_response_erase_all"]
      # server_response_header_erase - (optional) is a type of string
      server_response_header_erase = server_response_header.value["server_response_header_erase"]
      # server_response_header_insert - (optional) is a type of string
      server_response_header_insert = server_response_header.value["server_response_header_insert"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_sip.this.id
}

output "this" {
  value = thunder_slb_template_sip.this
}
```

[top](#index)