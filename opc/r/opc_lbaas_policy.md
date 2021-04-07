# opc_lbaas_policy

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_lbaas_policy" {
  source = "./modules/opc/r/opc_lbaas_policy"

  # load_balancer - (required) is a type of string
  load_balancer = null
  # name - (required) is a type of string
  name = null

  application_cookie_stickiness_policy = [{
    cookie_name = null
  }]

  cloudgate_policy = [{
    cloudgate_application                   = null
    cloudgate_policy_name                   = null
    identity_service_instance_guid          = null
    virtual_hostname_for_policy_attribution = null
  }]

  load_balancer_cookie_stickiness_policy = [{
    cookie_expiration_period = null
  }]

  load_balancing_mechanism_policy = [{
    load_balancing_mechanism = null
  }]

  rate_limiting_request_policy = [{
    burst_size               = null
    delay_excessive_requests = null
    http_error_code          = null
    logging_level            = null
    rate_limiting_criteria   = null
    requests_per_second      = null
    zone                     = null
    zone_memory_size         = null
  }]

  redirect_policy = [{
    redirect_uri  = null
    response_code = null
  }]

  resource_access_control_policy = [{
    denied_clients    = []
    disposition       = null
    permitted_clients = []
  }]

  set_request_header_policy = [{
    action_when_header_exists       = null
    action_when_header_value_is     = []
    action_when_header_value_is_not = []
    header_name                     = null
    value                           = null
  }]

  ssl_negotiation_policy = [{
    port                    = null
    server_order_preference = null
    ssl_ciphers             = []
    ssl_protocol            = []
  }]

  trusted_certificate_policy = [{
    trusted_certificate = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "load_balancer" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "application_cookie_stickiness_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cookie_name = string
    }
  ))
  default = []
}

variable "cloudgate_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloudgate_application                   = string
      cloudgate_policy_name                   = string
      identity_service_instance_guid          = string
      virtual_hostname_for_policy_attribution = string
    }
  ))
  default = []
}

variable "load_balancer_cookie_stickiness_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cookie_expiration_period = number
    }
  ))
  default = []
}

variable "load_balancing_mechanism_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      load_balancing_mechanism = string
    }
  ))
  default = []
}

variable "rate_limiting_request_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      burst_size               = number
      delay_excessive_requests = bool
      http_error_code          = number
      logging_level            = string
      rate_limiting_criteria   = string
      requests_per_second      = number
      zone                     = string
      zone_memory_size         = number
    }
  ))
  default = []
}

variable "redirect_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      redirect_uri  = string
      response_code = number
    }
  ))
  default = []
}

variable "resource_access_control_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      denied_clients    = set(string)
      disposition       = string
      permitted_clients = set(string)
    }
  ))
  default = []
}

variable "set_request_header_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      action_when_header_exists       = string
      action_when_header_value_is     = set(string)
      action_when_header_value_is_not = set(string)
      header_name                     = string
      value                           = string
    }
  ))
  default = []
}

variable "ssl_negotiation_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      port                    = number
      server_order_preference = string
      ssl_ciphers             = set(string)
      ssl_protocol            = set(string)
    }
  ))
  default = []
}

variable "trusted_certificate_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      trusted_certificate = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opc_lbaas_policy" "this" {
  # load_balancer - (required) is a type of string
  load_balancer = var.load_balancer
  # name - (required) is a type of string
  name = var.name

  dynamic "application_cookie_stickiness_policy" {
    for_each = var.application_cookie_stickiness_policy
    content {
      # cookie_name - (required) is a type of string
      cookie_name = application_cookie_stickiness_policy.value["cookie_name"]
    }
  }

  dynamic "cloudgate_policy" {
    for_each = var.cloudgate_policy
    content {
      # cloudgate_application - (optional) is a type of string
      cloudgate_application = cloudgate_policy.value["cloudgate_application"]
      # cloudgate_policy_name - (optional) is a type of string
      cloudgate_policy_name = cloudgate_policy.value["cloudgate_policy_name"]
      # identity_service_instance_guid - (optional) is a type of string
      identity_service_instance_guid = cloudgate_policy.value["identity_service_instance_guid"]
      # virtual_hostname_for_policy_attribution - (required) is a type of string
      virtual_hostname_for_policy_attribution = cloudgate_policy.value["virtual_hostname_for_policy_attribution"]
    }
  }

  dynamic "load_balancer_cookie_stickiness_policy" {
    for_each = var.load_balancer_cookie_stickiness_policy
    content {
      # cookie_expiration_period - (required) is a type of number
      cookie_expiration_period = load_balancer_cookie_stickiness_policy.value["cookie_expiration_period"]
    }
  }

  dynamic "load_balancing_mechanism_policy" {
    for_each = var.load_balancing_mechanism_policy
    content {
      # load_balancing_mechanism - (required) is a type of string
      load_balancing_mechanism = load_balancing_mechanism_policy.value["load_balancing_mechanism"]
    }
  }

  dynamic "rate_limiting_request_policy" {
    for_each = var.rate_limiting_request_policy
    content {
      # burst_size - (required) is a type of number
      burst_size = rate_limiting_request_policy.value["burst_size"]
      # delay_excessive_requests - (required) is a type of bool
      delay_excessive_requests = rate_limiting_request_policy.value["delay_excessive_requests"]
      # http_error_code - (optional) is a type of number
      http_error_code = rate_limiting_request_policy.value["http_error_code"]
      # logging_level - (optional) is a type of string
      logging_level = rate_limiting_request_policy.value["logging_level"]
      # rate_limiting_criteria - (optional) is a type of string
      rate_limiting_criteria = rate_limiting_request_policy.value["rate_limiting_criteria"]
      # requests_per_second - (required) is a type of number
      requests_per_second = rate_limiting_request_policy.value["requests_per_second"]
      # zone - (required) is a type of string
      zone = rate_limiting_request_policy.value["zone"]
      # zone_memory_size - (optional) is a type of number
      zone_memory_size = rate_limiting_request_policy.value["zone_memory_size"]
    }
  }

  dynamic "redirect_policy" {
    for_each = var.redirect_policy
    content {
      # redirect_uri - (required) is a type of string
      redirect_uri = redirect_policy.value["redirect_uri"]
      # response_code - (required) is a type of number
      response_code = redirect_policy.value["response_code"]
    }
  }

  dynamic "resource_access_control_policy" {
    for_each = var.resource_access_control_policy
    content {
      # denied_clients - (optional) is a type of set of string
      denied_clients = resource_access_control_policy.value["denied_clients"]
      # disposition - (required) is a type of string
      disposition = resource_access_control_policy.value["disposition"]
      # permitted_clients - (optional) is a type of set of string
      permitted_clients = resource_access_control_policy.value["permitted_clients"]
    }
  }

  dynamic "set_request_header_policy" {
    for_each = var.set_request_header_policy
    content {
      # action_when_header_exists - (optional) is a type of string
      action_when_header_exists = set_request_header_policy.value["action_when_header_exists"]
      # action_when_header_value_is - (optional) is a type of set of string
      action_when_header_value_is = set_request_header_policy.value["action_when_header_value_is"]
      # action_when_header_value_is_not - (optional) is a type of set of string
      action_when_header_value_is_not = set_request_header_policy.value["action_when_header_value_is_not"]
      # header_name - (required) is a type of string
      header_name = set_request_header_policy.value["header_name"]
      # value - (optional) is a type of string
      value = set_request_header_policy.value["value"]
    }
  }

  dynamic "ssl_negotiation_policy" {
    for_each = var.ssl_negotiation_policy
    content {
      # port - (required) is a type of number
      port = ssl_negotiation_policy.value["port"]
      # server_order_preference - (optional) is a type of string
      server_order_preference = ssl_negotiation_policy.value["server_order_preference"]
      # ssl_ciphers - (optional) is a type of set of string
      ssl_ciphers = ssl_negotiation_policy.value["ssl_ciphers"]
      # ssl_protocol - (required) is a type of set of string
      ssl_protocol = ssl_negotiation_policy.value["ssl_protocol"]
    }
  }

  dynamic "trusted_certificate_policy" {
    for_each = var.trusted_certificate_policy
    content {
      # trusted_certificate - (required) is a type of string
      trusted_certificate = trusted_certificate_policy.value["trusted_certificate"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_lbaas_policy.this.id
}

output "state" {
  description = "returns a bool"
  value       = opc_lbaas_policy.this.state
}

output "type" {
  description = "returns a string"
  value       = opc_lbaas_policy.this.type
}

output "uri" {
  description = "returns a string"
  value       = opc_lbaas_policy.this.uri
}

output "this" {
  value = opc_lbaas_policy.this
}
```

[top](#index)