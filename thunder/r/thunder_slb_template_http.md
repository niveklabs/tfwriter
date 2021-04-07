# thunder_slb_template_http

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
module "thunder_slb_template_http" {
  source = "./modules/thunder/r/thunder_slb_template_http"

  # 100_cont_wait_for_req_complete - (optional) is a type of number
  100 _cont_wait_for_req_complete = null
  # bypass_sg - (optional) is a type of string
  bypass_sg = null
  # client_ip_hdr_replace - (optional) is a type of number
  client_ip_hdr_replace = null
  # client_port_hdr_replace - (optional) is a type of number
  client_port_hdr_replace = null
  # compression_auto_disable_on_high_cpu - (optional) is a type of number
  compression_auto_disable_on_high_cpu = null
  # compression_enable - (optional) is a type of number
  compression_enable = null
  # compression_keep_accept_encoding - (optional) is a type of number
  compression_keep_accept_encoding = null
  # compression_keep_accept_encoding_enable - (optional) is a type of number
  compression_keep_accept_encoding_enable = null
  # compression_level - (optional) is a type of number
  compression_level = null
  # compression_minimum_content_length - (optional) is a type of number
  compression_minimum_content_length = null
  # cookie_format - (optional) is a type of string
  cookie_format = null
  # failover_url - (optional) is a type of string
  failover_url = null
  # insert_client_ip - (optional) is a type of number
  insert_client_ip = null
  # insert_client_ip_header_name - (optional) is a type of string
  insert_client_ip_header_name = null
  # insert_client_port - (optional) is a type of number
  insert_client_port = null
  # insert_client_port_header_name - (optional) is a type of string
  insert_client_port_header_name = null
  # keep_client_alive - (optional) is a type of number
  keep_client_alive = null
  # log_retry - (optional) is a type of number
  log_retry = null
  # max_concurrent_streams - (optional) is a type of number
  max_concurrent_streams = null
  # name - (optional) is a type of string
  name = null
  # non_http_bypass - (optional) is a type of number
  non_http_bypass = null
  # persist_on_401 - (optional) is a type of number
  persist_on_401 = null
  # rd_port - (optional) is a type of number
  rd_port = null
  # rd_resp_code - (optional) is a type of string
  rd_resp_code = null
  # rd_secure - (optional) is a type of number
  rd_secure = null
  # rd_simple_loc - (optional) is a type of string
  rd_simple_loc = null
  # redirect - (optional) is a type of number
  redirect = null
  # req_hdr_wait_time - (optional) is a type of number
  req_hdr_wait_time = null
  # req_hdr_wait_time_val - (optional) is a type of number
  req_hdr_wait_time_val = null
  # request_line_case_insensitive - (optional) is a type of number
  request_line_case_insensitive = null
  # request_timeout - (optional) is a type of number
  request_timeout = null
  # retry_on_5xx - (optional) is a type of number
  retry_on_5xx = null
  # retry_on_5xx_per_req - (optional) is a type of number
  retry_on_5xx_per_req = null
  # retry_on_5xx_per_req_val - (optional) is a type of number
  retry_on_5xx_per_req_val = null
  # retry_on_5xx_val - (optional) is a type of number
  retry_on_5xx_val = null
  # strict_transaction_switch - (optional) is a type of number
  strict_transaction_switch = null
  # term_11client_hdr_conn_close - (optional) is a type of number
  term_11client_hdr_conn_close = null
  # url_hash_first - (optional) is a type of number
  url_hash_first = null
  # url_hash_last - (optional) is a type of number
  url_hash_last = null
  # url_hash_offset - (optional) is a type of number
  url_hash_offset = null
  # url_hash_persist - (optional) is a type of number
  url_hash_persist = null
  # use_server_status - (optional) is a type of number
  use_server_status = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  compression_content_type = [{
    content_type = null
  }]

  compression_exclude_content_type = [{
    exclude_content_type = null
  }]

  compression_exclude_uri = [{
    exclude_uri = null
  }]

  host_switching = [{
    host_match_string   = null
    host_service_group  = null
    host_switching_type = null
  }]

  redirect_rewrite = [{
    match_list = [{
      redirect_match = null
      rewrite_to     = null
    }]
    redirect_secure      = null
    redirect_secure_port = null
  }]

  request_header_erase_list = [{
    request_header_erase = null
  }]

  request_header_insert_list = [{
    request_header_insert      = null
    request_header_insert_type = null
  }]

  response_content_replace_list = [{
    response_content_replace = null
    response_new_string      = null
  }]

  response_header_erase_list = [{
    response_header_erase = null
  }]

  response_header_insert_list = [{
    response_header_insert      = null
    response_header_insert_type = null
  }]

  template = [{
    logging = null
  }]

  url_switching = [{
    url_match_string   = null
    url_service_group  = null
    url_switching_type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "100_cont_wait_for_req_complete" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bypass_sg" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_ip_hdr_replace" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "client_port_hdr_replace" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "compression_auto_disable_on_high_cpu" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "compression_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "compression_keep_accept_encoding" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "compression_keep_accept_encoding_enable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "compression_level" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "compression_minimum_content_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cookie_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "failover_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "insert_client_ip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "insert_client_ip_header_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "insert_client_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "insert_client_port_header_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keep_client_alive" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "log_retry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_concurrent_streams" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "non_http_bypass" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "persist_on_401" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rd_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rd_resp_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rd_secure" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rd_simple_loc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redirect" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "req_hdr_wait_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "req_hdr_wait_time_val" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "request_line_case_insensitive" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "request_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "retry_on_5xx" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "retry_on_5xx_per_req" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "retry_on_5xx_per_req_val" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "retry_on_5xx_val" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "strict_transaction_switch" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "term_11client_hdr_conn_close" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "url_hash_first" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "url_hash_last" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "url_hash_offset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "url_hash_persist" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_server_status" {
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

variable "compression_content_type" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      content_type = string
    }
  ))
  default = []
}

variable "compression_exclude_content_type" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      exclude_content_type = string
    }
  ))
  default = []
}

variable "compression_exclude_uri" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      exclude_uri = string
    }
  ))
  default = []
}

variable "host_switching" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      host_match_string   = string
      host_service_group  = string
      host_switching_type = string
    }
  ))
  default = []
}

variable "redirect_rewrite" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      match_list = list(object(
        {
          redirect_match = string
          rewrite_to     = string
        }
      ))
      redirect_secure      = number
      redirect_secure_port = number
    }
  ))
  default = []
}

variable "request_header_erase_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      request_header_erase = string
    }
  ))
  default = []
}

variable "request_header_insert_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      request_header_insert      = string
      request_header_insert_type = string
    }
  ))
  default = []
}

variable "response_content_replace_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      response_content_replace = string
      response_new_string      = string
    }
  ))
  default = []
}

variable "response_header_erase_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      response_header_erase = string
    }
  ))
  default = []
}

variable "response_header_insert_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      response_header_insert      = string
      response_header_insert_type = string
    }
  ))
  default = []
}

variable "template" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      logging = string
    }
  ))
  default = []
}

variable "url_switching" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      url_match_string   = string
      url_service_group  = string
      url_switching_type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_http" "this" {
  # 100_cont_wait_for_req_complete - (optional) is a type of number
  100 _cont_wait_for_req_complete = var.100 _cont_wait_for_req_complete
  # bypass_sg - (optional) is a type of string
  bypass_sg = var.bypass_sg
  # client_ip_hdr_replace - (optional) is a type of number
  client_ip_hdr_replace = var.client_ip_hdr_replace
  # client_port_hdr_replace - (optional) is a type of number
  client_port_hdr_replace = var.client_port_hdr_replace
  # compression_auto_disable_on_high_cpu - (optional) is a type of number
  compression_auto_disable_on_high_cpu = var.compression_auto_disable_on_high_cpu
  # compression_enable - (optional) is a type of number
  compression_enable = var.compression_enable
  # compression_keep_accept_encoding - (optional) is a type of number
  compression_keep_accept_encoding = var.compression_keep_accept_encoding
  # compression_keep_accept_encoding_enable - (optional) is a type of number
  compression_keep_accept_encoding_enable = var.compression_keep_accept_encoding_enable
  # compression_level - (optional) is a type of number
  compression_level = var.compression_level
  # compression_minimum_content_length - (optional) is a type of number
  compression_minimum_content_length = var.compression_minimum_content_length
  # cookie_format - (optional) is a type of string
  cookie_format = var.cookie_format
  # failover_url - (optional) is a type of string
  failover_url = var.failover_url
  # insert_client_ip - (optional) is a type of number
  insert_client_ip = var.insert_client_ip
  # insert_client_ip_header_name - (optional) is a type of string
  insert_client_ip_header_name = var.insert_client_ip_header_name
  # insert_client_port - (optional) is a type of number
  insert_client_port = var.insert_client_port
  # insert_client_port_header_name - (optional) is a type of string
  insert_client_port_header_name = var.insert_client_port_header_name
  # keep_client_alive - (optional) is a type of number
  keep_client_alive = var.keep_client_alive
  # log_retry - (optional) is a type of number
  log_retry = var.log_retry
  # max_concurrent_streams - (optional) is a type of number
  max_concurrent_streams = var.max_concurrent_streams
  # name - (optional) is a type of string
  name = var.name
  # non_http_bypass - (optional) is a type of number
  non_http_bypass = var.non_http_bypass
  # persist_on_401 - (optional) is a type of number
  persist_on_401 = var.persist_on_401
  # rd_port - (optional) is a type of number
  rd_port = var.rd_port
  # rd_resp_code - (optional) is a type of string
  rd_resp_code = var.rd_resp_code
  # rd_secure - (optional) is a type of number
  rd_secure = var.rd_secure
  # rd_simple_loc - (optional) is a type of string
  rd_simple_loc = var.rd_simple_loc
  # redirect - (optional) is a type of number
  redirect = var.redirect
  # req_hdr_wait_time - (optional) is a type of number
  req_hdr_wait_time = var.req_hdr_wait_time
  # req_hdr_wait_time_val - (optional) is a type of number
  req_hdr_wait_time_val = var.req_hdr_wait_time_val
  # request_line_case_insensitive - (optional) is a type of number
  request_line_case_insensitive = var.request_line_case_insensitive
  # request_timeout - (optional) is a type of number
  request_timeout = var.request_timeout
  # retry_on_5xx - (optional) is a type of number
  retry_on_5xx = var.retry_on_5xx
  # retry_on_5xx_per_req - (optional) is a type of number
  retry_on_5xx_per_req = var.retry_on_5xx_per_req
  # retry_on_5xx_per_req_val - (optional) is a type of number
  retry_on_5xx_per_req_val = var.retry_on_5xx_per_req_val
  # retry_on_5xx_val - (optional) is a type of number
  retry_on_5xx_val = var.retry_on_5xx_val
  # strict_transaction_switch - (optional) is a type of number
  strict_transaction_switch = var.strict_transaction_switch
  # term_11client_hdr_conn_close - (optional) is a type of number
  term_11client_hdr_conn_close = var.term_11client_hdr_conn_close
  # url_hash_first - (optional) is a type of number
  url_hash_first = var.url_hash_first
  # url_hash_last - (optional) is a type of number
  url_hash_last = var.url_hash_last
  # url_hash_offset - (optional) is a type of number
  url_hash_offset = var.url_hash_offset
  # url_hash_persist - (optional) is a type of number
  url_hash_persist = var.url_hash_persist
  # use_server_status - (optional) is a type of number
  use_server_status = var.use_server_status
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "compression_content_type" {
    for_each = var.compression_content_type
    content {
      # content_type - (optional) is a type of string
      content_type = compression_content_type.value["content_type"]
    }
  }

  dynamic "compression_exclude_content_type" {
    for_each = var.compression_exclude_content_type
    content {
      # exclude_content_type - (optional) is a type of string
      exclude_content_type = compression_exclude_content_type.value["exclude_content_type"]
    }
  }

  dynamic "compression_exclude_uri" {
    for_each = var.compression_exclude_uri
    content {
      # exclude_uri - (optional) is a type of string
      exclude_uri = compression_exclude_uri.value["exclude_uri"]
    }
  }

  dynamic "host_switching" {
    for_each = var.host_switching
    content {
      # host_match_string - (optional) is a type of string
      host_match_string = host_switching.value["host_match_string"]
      # host_service_group - (optional) is a type of string
      host_service_group = host_switching.value["host_service_group"]
      # host_switching_type - (optional) is a type of string
      host_switching_type = host_switching.value["host_switching_type"]
    }
  }

  dynamic "redirect_rewrite" {
    for_each = var.redirect_rewrite
    content {
      # redirect_secure - (optional) is a type of number
      redirect_secure = redirect_rewrite.value["redirect_secure"]
      # redirect_secure_port - (optional) is a type of number
      redirect_secure_port = redirect_rewrite.value["redirect_secure_port"]

      dynamic "match_list" {
        for_each = redirect_rewrite.value.match_list
        content {
          # redirect_match - (optional) is a type of string
          redirect_match = match_list.value["redirect_match"]
          # rewrite_to - (optional) is a type of string
          rewrite_to = match_list.value["rewrite_to"]
        }
      }

    }
  }

  dynamic "request_header_erase_list" {
    for_each = var.request_header_erase_list
    content {
      # request_header_erase - (optional) is a type of string
      request_header_erase = request_header_erase_list.value["request_header_erase"]
    }
  }

  dynamic "request_header_insert_list" {
    for_each = var.request_header_insert_list
    content {
      # request_header_insert - (optional) is a type of string
      request_header_insert = request_header_insert_list.value["request_header_insert"]
      # request_header_insert_type - (optional) is a type of string
      request_header_insert_type = request_header_insert_list.value["request_header_insert_type"]
    }
  }

  dynamic "response_content_replace_list" {
    for_each = var.response_content_replace_list
    content {
      # response_content_replace - (optional) is a type of string
      response_content_replace = response_content_replace_list.value["response_content_replace"]
      # response_new_string - (optional) is a type of string
      response_new_string = response_content_replace_list.value["response_new_string"]
    }
  }

  dynamic "response_header_erase_list" {
    for_each = var.response_header_erase_list
    content {
      # response_header_erase - (optional) is a type of string
      response_header_erase = response_header_erase_list.value["response_header_erase"]
    }
  }

  dynamic "response_header_insert_list" {
    for_each = var.response_header_insert_list
    content {
      # response_header_insert - (optional) is a type of string
      response_header_insert = response_header_insert_list.value["response_header_insert"]
      # response_header_insert_type - (optional) is a type of string
      response_header_insert_type = response_header_insert_list.value["response_header_insert_type"]
    }
  }

  dynamic "template" {
    for_each = var.template
    content {
      # logging - (optional) is a type of string
      logging = template.value["logging"]
    }
  }

  dynamic "url_switching" {
    for_each = var.url_switching
    content {
      # url_match_string - (optional) is a type of string
      url_match_string = url_switching.value["url_match_string"]
      # url_service_group - (optional) is a type of string
      url_service_group = url_switching.value["url_service_group"]
      # url_switching_type - (optional) is a type of string
      url_switching_type = url_switching.value["url_switching_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_http.this.id
}

output "this" {
  value = thunder_slb_template_http.this
}
```

[top](#index)