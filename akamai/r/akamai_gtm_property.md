# akamai_gtm_property

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_gtm_property" {
  source = "./modules/akamai/r/akamai_gtm_property"

  # backup_cname - (optional) is a type of string
  backup_cname = null
  # backup_ip - (optional) is a type of string
  backup_ip = null
  # balance_by_download_score - (optional) is a type of bool
  balance_by_download_score = null
  # cname - (optional) is a type of string
  cname = null
  # comments - (optional) is a type of string
  comments = null
  # domain - (required) is a type of string
  domain = null
  # dynamic_ttl - (optional) is a type of number
  dynamic_ttl = null
  # failback_delay - (optional) is a type of number
  failback_delay = null
  # failover_delay - (optional) is a type of number
  failover_delay = null
  # ghost_demand_reporting - (optional) is a type of bool
  ghost_demand_reporting = null
  # handout_limit - (required) is a type of number
  handout_limit = null
  # handout_mode - (required) is a type of string
  handout_mode = null
  # health_max - (optional) is a type of number
  health_max = null
  # health_multiplier - (optional) is a type of number
  health_multiplier = null
  # health_threshold - (optional) is a type of number
  health_threshold = null
  # ipv6 - (optional) is a type of bool
  ipv6 = null
  # load_imbalance_percentage - (optional) is a type of number
  load_imbalance_percentage = null
  # map_name - (optional) is a type of string
  map_name = null
  # max_unreachable_penalty - (optional) is a type of number
  max_unreachable_penalty = null
  # min_live_fraction - (optional) is a type of number
  min_live_fraction = null
  # name - (required) is a type of string
  name = null
  # score_aggregation_type - (required) is a type of string
  score_aggregation_type = null
  # static_ttl - (optional) is a type of number
  static_ttl = null
  # stickiness_bonus_constant - (optional) is a type of number
  stickiness_bonus_constant = null
  # stickiness_bonus_percentage - (optional) is a type of number
  stickiness_bonus_percentage = null
  # type - (required) is a type of string
  type = null
  # unreachable_threshold - (optional) is a type of number
  unreachable_threshold = null
  # use_computed_targets - (optional) is a type of bool
  use_computed_targets = null
  # wait_on_complete - (optional) is a type of bool
  wait_on_complete = null

  liveness_test = [{
    answers_required                 = null
    disable_nonstandard_port_warning = null
    disabled                         = null
    error_penalty                    = null
    http_error3xx                    = null
    http_error4xx                    = null
    http_error5xx                    = null
    http_header = [{
      name  = null
      value = null
    }]
    name                          = null
    peer_certificate_verification = null
    recursion_requested           = null
    request_string                = null
    resource_type                 = null
    response_string               = null
    ssl_client_certificate        = null
    ssl_client_private_key        = null
    test_interval                 = null
    test_object                   = null
    test_object_password          = null
    test_object_port              = null
    test_object_protocol          = null
    test_object_username          = null
    test_timeout                  = null
    timeout_penalty               = null
  }]

  static_rr_set = [{
    rdata = []
    ttl   = null
    type  = null
  }]

  traffic_target = [{
    datacenter_id = null
    enabled       = null
    handout_cname = null
    name          = null
    servers       = []
    weight        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "backup_cname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "balance_by_download_score" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}

variable "dynamic_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "failback_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "failover_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ghost_demand_reporting" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "handout_limit" {
  description = "(required)"
  type        = number
}

variable "handout_mode" {
  description = "(required)"
  type        = string
}

variable "health_max" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_multiplier" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ipv6" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "load_imbalance_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "map_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_unreachable_penalty" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_live_fraction" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "score_aggregation_type" {
  description = "(required)"
  type        = string
}

variable "static_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stickiness_bonus_constant" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stickiness_bonus_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "unreachable_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_computed_targets" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "wait_on_complete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "liveness_test" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      answers_required                 = bool
      disable_nonstandard_port_warning = bool
      disabled                         = bool
      error_penalty                    = number
      http_error3xx                    = bool
      http_error4xx                    = bool
      http_error5xx                    = bool
      http_header = list(object(
        {
          name  = string
          value = string
        }
      ))
      name                          = string
      peer_certificate_verification = bool
      recursion_requested           = bool
      request_string                = string
      resource_type                 = string
      response_string               = string
      ssl_client_certificate        = string
      ssl_client_private_key        = string
      test_interval                 = number
      test_object                   = string
      test_object_password          = string
      test_object_port              = number
      test_object_protocol          = string
      test_object_username          = string
      test_timeout                  = number
      timeout_penalty               = number
    }
  ))
  default = []
}

variable "static_rr_set" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      rdata = list(string)
      ttl   = number
      type  = string
    }
  ))
  default = []
}

variable "traffic_target" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      datacenter_id = number
      enabled       = bool
      handout_cname = string
      name          = string
      servers       = list(string)
      weight        = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "akamai_gtm_property" "this" {
  backup_cname                = var.backup_cname
  backup_ip                   = var.backup_ip
  balance_by_download_score   = var.balance_by_download_score
  cname                       = var.cname
  comments                    = var.comments
  domain                      = var.domain
  dynamic_ttl                 = var.dynamic_ttl
  failback_delay              = var.failback_delay
  failover_delay              = var.failover_delay
  ghost_demand_reporting      = var.ghost_demand_reporting
  handout_limit               = var.handout_limit
  handout_mode                = var.handout_mode
  health_max                  = var.health_max
  health_multiplier           = var.health_multiplier
  health_threshold            = var.health_threshold
  ipv6                        = var.ipv6
  load_imbalance_percentage   = var.load_imbalance_percentage
  map_name                    = var.map_name
  max_unreachable_penalty     = var.max_unreachable_penalty
  min_live_fraction           = var.min_live_fraction
  name                        = var.name
  score_aggregation_type      = var.score_aggregation_type
  static_ttl                  = var.static_ttl
  stickiness_bonus_constant   = var.stickiness_bonus_constant
  stickiness_bonus_percentage = var.stickiness_bonus_percentage
  type                        = var.type
  unreachable_threshold       = var.unreachable_threshold
  use_computed_targets        = var.use_computed_targets
  wait_on_complete            = var.wait_on_complete

  dynamic "liveness_test" {
    for_each = var.liveness_test
    content {
      answers_required                 = liveness_test.value["answers_required"]
      disable_nonstandard_port_warning = liveness_test.value["disable_nonstandard_port_warning"]
      disabled                         = liveness_test.value["disabled"]
      error_penalty                    = liveness_test.value["error_penalty"]
      http_error3xx                    = liveness_test.value["http_error3xx"]
      http_error4xx                    = liveness_test.value["http_error4xx"]
      http_error5xx                    = liveness_test.value["http_error5xx"]
      name                             = liveness_test.value["name"]
      peer_certificate_verification    = liveness_test.value["peer_certificate_verification"]
      recursion_requested              = liveness_test.value["recursion_requested"]
      request_string                   = liveness_test.value["request_string"]
      resource_type                    = liveness_test.value["resource_type"]
      response_string                  = liveness_test.value["response_string"]
      ssl_client_certificate           = liveness_test.value["ssl_client_certificate"]
      ssl_client_private_key           = liveness_test.value["ssl_client_private_key"]
      test_interval                    = liveness_test.value["test_interval"]
      test_object                      = liveness_test.value["test_object"]
      test_object_password             = liveness_test.value["test_object_password"]
      test_object_port                 = liveness_test.value["test_object_port"]
      test_object_protocol             = liveness_test.value["test_object_protocol"]
      test_object_username             = liveness_test.value["test_object_username"]
      test_timeout                     = liveness_test.value["test_timeout"]
      timeout_penalty                  = liveness_test.value["timeout_penalty"]

      dynamic "http_header" {
        for_each = liveness_test.value.http_header
        content {
          name  = http_header.value["name"]
          value = http_header.value["value"]
        }
      }

    }
  }

  dynamic "static_rr_set" {
    for_each = var.static_rr_set
    content {
      rdata = static_rr_set.value["rdata"]
      ttl   = static_rr_set.value["ttl"]
      type  = static_rr_set.value["type"]
    }
  }

  dynamic "traffic_target" {
    for_each = var.traffic_target
    content {
      datacenter_id = traffic_target.value["datacenter_id"]
      enabled       = traffic_target.value["enabled"]
      handout_cname = traffic_target.value["handout_cname"]
      name          = traffic_target.value["name"]
      servers       = traffic_target.value["servers"]
      weight        = traffic_target.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_gtm_property.this.id
}

output "weighted_hash_bits_for_ipv4" {
  description = "returns a number"
  value       = akamai_gtm_property.this.weighted_hash_bits_for_ipv4
}

output "weighted_hash_bits_for_ipv6" {
  description = "returns a number"
  value       = akamai_gtm_property.this.weighted_hash_bits_for_ipv6
}

output "this" {
  value = akamai_gtm_property.this
}
```

[top](#index)