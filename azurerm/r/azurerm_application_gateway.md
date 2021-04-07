# azurerm_application_gateway

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_application_gateway" {
  source = "./modules/azurerm/r/azurerm_application_gateway"

  # enable_http2 - (optional) is a type of bool
  enable_http2 = null
  # firewall_policy_id - (optional) is a type of string
  firewall_policy_id = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zones - (optional) is a type of list of string
  zones = []

  authentication_certificate = [{
    data = null
    id   = null
    name = null
  }]

  autoscale_configuration = [{
    max_capacity = null
    min_capacity = null
  }]

  backend_address_pool = [{
    fqdns        = []
    id           = null
    ip_addresses = []
    name         = null
  }]

  backend_http_settings = [{
    affinity_cookie_name = null
    authentication_certificate = [{
      id   = null
      name = null
    }]
    connection_draining = [{
      drain_timeout_sec = null
      enabled           = null
    }]
    cookie_based_affinity               = null
    host_name                           = null
    id                                  = null
    name                                = null
    path                                = null
    pick_host_name_from_backend_address = null
    port                                = null
    probe_id                            = null
    probe_name                          = null
    protocol                            = null
    request_timeout                     = null
    trusted_root_certificate_names      = []
  }]

  custom_error_configuration = [{
    custom_error_page_url = null
    id                    = null
    status_code           = null
  }]

  frontend_ip_configuration = [{
    id                            = null
    name                          = null
    private_ip_address            = null
    private_ip_address_allocation = null
    public_ip_address_id          = null
    subnet_id                     = null
  }]

  frontend_port = [{
    id   = null
    name = null
    port = null
  }]

  gateway_ip_configuration = [{
    id        = null
    name      = null
    subnet_id = null
  }]

  http_listener = [{
    custom_error_configuration = [{
      custom_error_page_url = null
      id                    = null
      status_code           = null
    }]
    firewall_policy_id             = null
    frontend_ip_configuration_id   = null
    frontend_ip_configuration_name = null
    frontend_port_id               = null
    frontend_port_name             = null
    host_name                      = null
    host_names                     = []
    id                             = null
    name                           = null
    protocol                       = null
    require_sni                    = null
    ssl_certificate_id             = null
    ssl_certificate_name           = null
  }]

  identity = [{
    identity_ids = []
    type         = null
  }]

  probe = [{
    host     = null
    id       = null
    interval = null
    match = [{
      body        = null
      status_code = []
    }]
    minimum_servers                           = null
    name                                      = null
    path                                      = null
    pick_host_name_from_backend_http_settings = null
    port                                      = null
    protocol                                  = null
    timeout                                   = null
    unhealthy_threshold                       = null
  }]

  redirect_configuration = [{
    id                   = null
    include_path         = null
    include_query_string = null
    name                 = null
    redirect_type        = null
    target_listener_id   = null
    target_listener_name = null
    target_url           = null
  }]

  request_routing_rule = [{
    backend_address_pool_id     = null
    backend_address_pool_name   = null
    backend_http_settings_id    = null
    backend_http_settings_name  = null
    http_listener_id            = null
    http_listener_name          = null
    id                          = null
    name                        = null
    redirect_configuration_id   = null
    redirect_configuration_name = null
    rewrite_rule_set_id         = null
    rewrite_rule_set_name       = null
    rule_type                   = null
    url_path_map_id             = null
    url_path_map_name           = null
  }]

  rewrite_rule_set = [{
    id   = null
    name = null
    rewrite_rule = [{
      condition = [{
        ignore_case = null
        negate      = null
        pattern     = null
        variable    = null
      }]
      name = null
      request_header_configuration = [{
        header_name  = null
        header_value = null
      }]
      response_header_configuration = [{
        header_name  = null
        header_value = null
      }]
      rule_sequence = null
      url = [{
        path         = null
        query_string = null
        reroute      = null
      }]
    }]
  }]

  sku = [{
    capacity = null
    name     = null
    tier     = null
  }]

  ssl_certificate = [{
    data                = null
    id                  = null
    key_vault_secret_id = null
    name                = null
    password            = null
    public_cert_data    = null
  }]

  ssl_policy = [{
    cipher_suites        = []
    disabled_protocols   = []
    min_protocol_version = null
    policy_name          = null
    policy_type          = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  trusted_root_certificate = [{
    data = null
    id   = null
    name = null
  }]

  url_path_map = [{
    default_backend_address_pool_id     = null
    default_backend_address_pool_name   = null
    default_backend_http_settings_id    = null
    default_backend_http_settings_name  = null
    default_redirect_configuration_id   = null
    default_redirect_configuration_name = null
    default_rewrite_rule_set_id         = null
    default_rewrite_rule_set_name       = null
    id                                  = null
    name                                = null
    path_rule = [{
      backend_address_pool_id     = null
      backend_address_pool_name   = null
      backend_http_settings_id    = null
      backend_http_settings_name  = null
      id                          = null
      name                        = null
      paths                       = []
      redirect_configuration_id   = null
      redirect_configuration_name = null
      rewrite_rule_set_id         = null
      rewrite_rule_set_name       = null
    }]
  }]

  waf_configuration = [{
    disabled_rule_group = [{
      rule_group_name = null
      rules           = []
    }]
    enabled = null
    exclusion = [{
      match_variable          = null
      selector                = null
      selector_match_operator = null
    }]
    file_upload_limit_mb     = null
    firewall_mode            = null
    max_request_body_size_kb = null
    request_body_check       = null
    rule_set_type            = null
    rule_set_version         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enable_http2" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "firewall_policy_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "authentication_certificate" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      data = string
      id   = string
      name = string
    }
  ))
  default = []
}

variable "autoscale_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_capacity = number
      min_capacity = number
    }
  ))
  default = []
}

variable "backend_address_pool" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      fqdns        = list(string)
      id           = string
      ip_addresses = list(string)
      name         = string
    }
  ))
}

variable "backend_http_settings" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      affinity_cookie_name = string
      authentication_certificate = list(object(
        {
          id   = string
          name = string
        }
      ))
      connection_draining = list(object(
        {
          drain_timeout_sec = number
          enabled           = bool
        }
      ))
      cookie_based_affinity               = string
      host_name                           = string
      id                                  = string
      name                                = string
      path                                = string
      pick_host_name_from_backend_address = bool
      port                                = number
      probe_id                            = string
      probe_name                          = string
      protocol                            = string
      request_timeout                     = number
      trusted_root_certificate_names      = list(string)
    }
  ))
}

variable "custom_error_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      custom_error_page_url = string
      id                    = string
      status_code           = string
    }
  ))
  default = []
}

variable "frontend_ip_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      id                            = string
      name                          = string
      private_ip_address            = string
      private_ip_address_allocation = string
      public_ip_address_id          = string
      subnet_id                     = string
    }
  ))
}

variable "frontend_port" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      id   = string
      name = string
      port = number
    }
  ))
}

variable "gateway_ip_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 2"
  type = set(object(
    {
      id        = string
      name      = string
      subnet_id = string
    }
  ))
}

variable "http_listener" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      custom_error_configuration = list(object(
        {
          custom_error_page_url = string
          id                    = string
          status_code           = string
        }
      ))
      firewall_policy_id             = string
      frontend_ip_configuration_id   = string
      frontend_ip_configuration_name = string
      frontend_port_id               = string
      frontend_port_name             = string
      host_name                      = string
      host_names                     = set(string)
      id                             = string
      name                           = string
      protocol                       = string
      require_sni                    = bool
      ssl_certificate_id             = string
      ssl_certificate_name           = string
    }
  ))
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      identity_ids = list(string)
      type         = string
    }
  ))
  default = []
}

variable "probe" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      host     = string
      id       = string
      interval = number
      match = list(object(
        {
          body        = string
          status_code = list(string)
        }
      ))
      minimum_servers                           = number
      name                                      = string
      path                                      = string
      pick_host_name_from_backend_http_settings = bool
      port                                      = number
      protocol                                  = string
      timeout                                   = number
      unhealthy_threshold                       = number
    }
  ))
  default = []
}

variable "redirect_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id                   = string
      include_path         = bool
      include_query_string = bool
      name                 = string
      redirect_type        = string
      target_listener_id   = string
      target_listener_name = string
      target_url           = string
    }
  ))
  default = []
}

variable "request_routing_rule" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      backend_address_pool_id     = string
      backend_address_pool_name   = string
      backend_http_settings_id    = string
      backend_http_settings_name  = string
      http_listener_id            = string
      http_listener_name          = string
      id                          = string
      name                        = string
      redirect_configuration_id   = string
      redirect_configuration_name = string
      rewrite_rule_set_id         = string
      rewrite_rule_set_name       = string
      rule_type                   = string
      url_path_map_id             = string
      url_path_map_name           = string
    }
  ))
}

variable "rewrite_rule_set" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id   = string
      name = string
      rewrite_rule = list(object(
        {
          condition = list(object(
            {
              ignore_case = bool
              negate      = bool
              pattern     = string
              variable    = string
            }
          ))
          name = string
          request_header_configuration = list(object(
            {
              header_name  = string
              header_value = string
            }
          ))
          response_header_configuration = list(object(
            {
              header_name  = string
              header_value = string
            }
          ))
          rule_sequence = number
          url = list(object(
            {
              path         = string
              query_string = string
              reroute      = bool
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "sku" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      capacity = number
      name     = string
      tier     = string
    }
  ))
}

variable "ssl_certificate" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      data                = string
      id                  = string
      key_vault_secret_id = string
      name                = string
      password            = string
      public_cert_data    = string
    }
  ))
  default = []
}

variable "ssl_policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cipher_suites        = list(string)
      disabled_protocols   = list(string)
      min_protocol_version = string
      policy_name          = string
      policy_type          = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}

variable "trusted_root_certificate" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      data = string
      id   = string
      name = string
    }
  ))
  default = []
}

variable "url_path_map" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      default_backend_address_pool_id     = string
      default_backend_address_pool_name   = string
      default_backend_http_settings_id    = string
      default_backend_http_settings_name  = string
      default_redirect_configuration_id   = string
      default_redirect_configuration_name = string
      default_rewrite_rule_set_id         = string
      default_rewrite_rule_set_name       = string
      id                                  = string
      name                                = string
      path_rule = list(object(
        {
          backend_address_pool_id     = string
          backend_address_pool_name   = string
          backend_http_settings_id    = string
          backend_http_settings_name  = string
          id                          = string
          name                        = string
          paths                       = list(string)
          redirect_configuration_id   = string
          redirect_configuration_name = string
          rewrite_rule_set_id         = string
          rewrite_rule_set_name       = string
        }
      ))
    }
  ))
  default = []
}

variable "waf_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disabled_rule_group = list(object(
        {
          rule_group_name = string
          rules           = list(number)
        }
      ))
      enabled = bool
      exclusion = list(object(
        {
          match_variable          = string
          selector                = string
          selector_match_operator = string
        }
      ))
      file_upload_limit_mb     = number
      firewall_mode            = string
      max_request_body_size_kb = number
      request_body_check       = bool
      rule_set_type            = string
      rule_set_version         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_application_gateway" "this" {
  # enable_http2 - (optional) is a type of bool
  enable_http2 = var.enable_http2
  # firewall_policy_id - (optional) is a type of string
  firewall_policy_id = var.firewall_policy_id
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # zones - (optional) is a type of list of string
  zones = var.zones

  dynamic "authentication_certificate" {
    for_each = var.authentication_certificate
    content {
      # data - (required) is a type of string
      data = authentication_certificate.value["data"]
      # name - (required) is a type of string
      name = authentication_certificate.value["name"]
    }
  }

  dynamic "autoscale_configuration" {
    for_each = var.autoscale_configuration
    content {
      # max_capacity - (optional) is a type of number
      max_capacity = autoscale_configuration.value["max_capacity"]
      # min_capacity - (required) is a type of number
      min_capacity = autoscale_configuration.value["min_capacity"]
    }
  }

  dynamic "backend_address_pool" {
    for_each = var.backend_address_pool
    content {
      # fqdns - (optional) is a type of list of string
      fqdns = backend_address_pool.value["fqdns"]
      # ip_addresses - (optional) is a type of list of string
      ip_addresses = backend_address_pool.value["ip_addresses"]
      # name - (required) is a type of string
      name = backend_address_pool.value["name"]
    }
  }

  dynamic "backend_http_settings" {
    for_each = var.backend_http_settings
    content {
      # affinity_cookie_name - (optional) is a type of string
      affinity_cookie_name = backend_http_settings.value["affinity_cookie_name"]
      # cookie_based_affinity - (required) is a type of string
      cookie_based_affinity = backend_http_settings.value["cookie_based_affinity"]
      # host_name - (optional) is a type of string
      host_name = backend_http_settings.value["host_name"]
      # name - (required) is a type of string
      name = backend_http_settings.value["name"]
      # path - (optional) is a type of string
      path = backend_http_settings.value["path"]
      # pick_host_name_from_backend_address - (optional) is a type of bool
      pick_host_name_from_backend_address = backend_http_settings.value["pick_host_name_from_backend_address"]
      # port - (required) is a type of number
      port = backend_http_settings.value["port"]
      # probe_name - (optional) is a type of string
      probe_name = backend_http_settings.value["probe_name"]
      # protocol - (required) is a type of string
      protocol = backend_http_settings.value["protocol"]
      # request_timeout - (optional) is a type of number
      request_timeout = backend_http_settings.value["request_timeout"]
      # trusted_root_certificate_names - (optional) is a type of list of string
      trusted_root_certificate_names = backend_http_settings.value["trusted_root_certificate_names"]

      dynamic "authentication_certificate" {
        for_each = backend_http_settings.value.authentication_certificate
        content {
          # name - (required) is a type of string
          name = authentication_certificate.value["name"]
        }
      }

      dynamic "connection_draining" {
        for_each = backend_http_settings.value.connection_draining
        content {
          # drain_timeout_sec - (required) is a type of number
          drain_timeout_sec = connection_draining.value["drain_timeout_sec"]
          # enabled - (required) is a type of bool
          enabled = connection_draining.value["enabled"]
        }
      }

    }
  }

  dynamic "custom_error_configuration" {
    for_each = var.custom_error_configuration
    content {
      # custom_error_page_url - (required) is a type of string
      custom_error_page_url = custom_error_configuration.value["custom_error_page_url"]
      # status_code - (required) is a type of string
      status_code = custom_error_configuration.value["status_code"]
    }
  }

  dynamic "frontend_ip_configuration" {
    for_each = var.frontend_ip_configuration
    content {
      # name - (required) is a type of string
      name = frontend_ip_configuration.value["name"]
      # private_ip_address - (optional) is a type of string
      private_ip_address = frontend_ip_configuration.value["private_ip_address"]
      # private_ip_address_allocation - (optional) is a type of string
      private_ip_address_allocation = frontend_ip_configuration.value["private_ip_address_allocation"]
      # public_ip_address_id - (optional) is a type of string
      public_ip_address_id = frontend_ip_configuration.value["public_ip_address_id"]
      # subnet_id - (optional) is a type of string
      subnet_id = frontend_ip_configuration.value["subnet_id"]
    }
  }

  dynamic "frontend_port" {
    for_each = var.frontend_port
    content {
      # name - (required) is a type of string
      name = frontend_port.value["name"]
      # port - (required) is a type of number
      port = frontend_port.value["port"]
    }
  }

  dynamic "gateway_ip_configuration" {
    for_each = var.gateway_ip_configuration
    content {
      # name - (required) is a type of string
      name = gateway_ip_configuration.value["name"]
      # subnet_id - (required) is a type of string
      subnet_id = gateway_ip_configuration.value["subnet_id"]
    }
  }

  dynamic "http_listener" {
    for_each = var.http_listener
    content {
      # firewall_policy_id - (optional) is a type of string
      firewall_policy_id = http_listener.value["firewall_policy_id"]
      # frontend_ip_configuration_name - (required) is a type of string
      frontend_ip_configuration_name = http_listener.value["frontend_ip_configuration_name"]
      # frontend_port_name - (required) is a type of string
      frontend_port_name = http_listener.value["frontend_port_name"]
      # host_name - (optional) is a type of string
      host_name = http_listener.value["host_name"]
      # host_names - (optional) is a type of set of string
      host_names = http_listener.value["host_names"]
      # name - (required) is a type of string
      name = http_listener.value["name"]
      # protocol - (required) is a type of string
      protocol = http_listener.value["protocol"]
      # require_sni - (optional) is a type of bool
      require_sni = http_listener.value["require_sni"]
      # ssl_certificate_name - (optional) is a type of string
      ssl_certificate_name = http_listener.value["ssl_certificate_name"]

      dynamic "custom_error_configuration" {
        for_each = http_listener.value.custom_error_configuration
        content {
          # custom_error_page_url - (required) is a type of string
          custom_error_page_url = custom_error_configuration.value["custom_error_page_url"]
          # status_code - (required) is a type of string
          status_code = custom_error_configuration.value["status_code"]
        }
      }

    }
  }

  dynamic "identity" {
    for_each = var.identity
    content {
      # identity_ids - (required) is a type of list of string
      identity_ids = identity.value["identity_ids"]
      # type - (optional) is a type of string
      type = identity.value["type"]
    }
  }

  dynamic "probe" {
    for_each = var.probe
    content {
      # host - (optional) is a type of string
      host = probe.value["host"]
      # interval - (required) is a type of number
      interval = probe.value["interval"]
      # minimum_servers - (optional) is a type of number
      minimum_servers = probe.value["minimum_servers"]
      # name - (required) is a type of string
      name = probe.value["name"]
      # path - (required) is a type of string
      path = probe.value["path"]
      # pick_host_name_from_backend_http_settings - (optional) is a type of bool
      pick_host_name_from_backend_http_settings = probe.value["pick_host_name_from_backend_http_settings"]
      # port - (optional) is a type of number
      port = probe.value["port"]
      # protocol - (required) is a type of string
      protocol = probe.value["protocol"]
      # timeout - (required) is a type of number
      timeout = probe.value["timeout"]
      # unhealthy_threshold - (required) is a type of number
      unhealthy_threshold = probe.value["unhealthy_threshold"]

      dynamic "match" {
        for_each = probe.value.match
        content {
          # body - (optional) is a type of string
          body = match.value["body"]
          # status_code - (optional) is a type of list of string
          status_code = match.value["status_code"]
        }
      }

    }
  }

  dynamic "redirect_configuration" {
    for_each = var.redirect_configuration
    content {
      # include_path - (optional) is a type of bool
      include_path = redirect_configuration.value["include_path"]
      # include_query_string - (optional) is a type of bool
      include_query_string = redirect_configuration.value["include_query_string"]
      # name - (required) is a type of string
      name = redirect_configuration.value["name"]
      # redirect_type - (required) is a type of string
      redirect_type = redirect_configuration.value["redirect_type"]
      # target_listener_name - (optional) is a type of string
      target_listener_name = redirect_configuration.value["target_listener_name"]
      # target_url - (optional) is a type of string
      target_url = redirect_configuration.value["target_url"]
    }
  }

  dynamic "request_routing_rule" {
    for_each = var.request_routing_rule
    content {
      # backend_address_pool_name - (optional) is a type of string
      backend_address_pool_name = request_routing_rule.value["backend_address_pool_name"]
      # backend_http_settings_name - (optional) is a type of string
      backend_http_settings_name = request_routing_rule.value["backend_http_settings_name"]
      # http_listener_name - (required) is a type of string
      http_listener_name = request_routing_rule.value["http_listener_name"]
      # name - (required) is a type of string
      name = request_routing_rule.value["name"]
      # redirect_configuration_name - (optional) is a type of string
      redirect_configuration_name = request_routing_rule.value["redirect_configuration_name"]
      # rewrite_rule_set_name - (optional) is a type of string
      rewrite_rule_set_name = request_routing_rule.value["rewrite_rule_set_name"]
      # rule_type - (required) is a type of string
      rule_type = request_routing_rule.value["rule_type"]
      # url_path_map_name - (optional) is a type of string
      url_path_map_name = request_routing_rule.value["url_path_map_name"]
    }
  }

  dynamic "rewrite_rule_set" {
    for_each = var.rewrite_rule_set
    content {
      # name - (required) is a type of string
      name = rewrite_rule_set.value["name"]

      dynamic "rewrite_rule" {
        for_each = rewrite_rule_set.value.rewrite_rule
        content {
          # name - (required) is a type of string
          name = rewrite_rule.value["name"]
          # rule_sequence - (required) is a type of number
          rule_sequence = rewrite_rule.value["rule_sequence"]

          dynamic "condition" {
            for_each = rewrite_rule.value.condition
            content {
              # ignore_case - (optional) is a type of bool
              ignore_case = condition.value["ignore_case"]
              # negate - (optional) is a type of bool
              negate = condition.value["negate"]
              # pattern - (required) is a type of string
              pattern = condition.value["pattern"]
              # variable - (required) is a type of string
              variable = condition.value["variable"]
            }
          }

          dynamic "request_header_configuration" {
            for_each = rewrite_rule.value.request_header_configuration
            content {
              # header_name - (required) is a type of string
              header_name = request_header_configuration.value["header_name"]
              # header_value - (required) is a type of string
              header_value = request_header_configuration.value["header_value"]
            }
          }

          dynamic "response_header_configuration" {
            for_each = rewrite_rule.value.response_header_configuration
            content {
              # header_name - (required) is a type of string
              header_name = response_header_configuration.value["header_name"]
              # header_value - (required) is a type of string
              header_value = response_header_configuration.value["header_value"]
            }
          }

          dynamic "url" {
            for_each = rewrite_rule.value.url
            content {
              # path - (optional) is a type of string
              path = url.value["path"]
              # query_string - (optional) is a type of string
              query_string = url.value["query_string"]
              # reroute - (optional) is a type of bool
              reroute = url.value["reroute"]
            }
          }

        }
      }

    }
  }

  dynamic "sku" {
    for_each = var.sku
    content {
      # capacity - (optional) is a type of number
      capacity = sku.value["capacity"]
      # name - (required) is a type of string
      name = sku.value["name"]
      # tier - (required) is a type of string
      tier = sku.value["tier"]
    }
  }

  dynamic "ssl_certificate" {
    for_each = var.ssl_certificate
    content {
      # data - (optional) is a type of string
      data = ssl_certificate.value["data"]
      # key_vault_secret_id - (optional) is a type of string
      key_vault_secret_id = ssl_certificate.value["key_vault_secret_id"]
      # name - (required) is a type of string
      name = ssl_certificate.value["name"]
      # password - (optional) is a type of string
      password = ssl_certificate.value["password"]
    }
  }

  dynamic "ssl_policy" {
    for_each = var.ssl_policy
    content {
      # cipher_suites - (optional) is a type of list of string
      cipher_suites = ssl_policy.value["cipher_suites"]
      # disabled_protocols - (optional) is a type of list of string
      disabled_protocols = ssl_policy.value["disabled_protocols"]
      # min_protocol_version - (optional) is a type of string
      min_protocol_version = ssl_policy.value["min_protocol_version"]
      # policy_name - (optional) is a type of string
      policy_name = ssl_policy.value["policy_name"]
      # policy_type - (optional) is a type of string
      policy_type = ssl_policy.value["policy_type"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

  dynamic "trusted_root_certificate" {
    for_each = var.trusted_root_certificate
    content {
      # data - (required) is a type of string
      data = trusted_root_certificate.value["data"]
      # name - (required) is a type of string
      name = trusted_root_certificate.value["name"]
    }
  }

  dynamic "url_path_map" {
    for_each = var.url_path_map
    content {
      # default_backend_address_pool_name - (optional) is a type of string
      default_backend_address_pool_name = url_path_map.value["default_backend_address_pool_name"]
      # default_backend_http_settings_name - (optional) is a type of string
      default_backend_http_settings_name = url_path_map.value["default_backend_http_settings_name"]
      # default_redirect_configuration_name - (optional) is a type of string
      default_redirect_configuration_name = url_path_map.value["default_redirect_configuration_name"]
      # default_rewrite_rule_set_name - (optional) is a type of string
      default_rewrite_rule_set_name = url_path_map.value["default_rewrite_rule_set_name"]
      # name - (required) is a type of string
      name = url_path_map.value["name"]

      dynamic "path_rule" {
        for_each = url_path_map.value.path_rule
        content {
          # backend_address_pool_name - (optional) is a type of string
          backend_address_pool_name = path_rule.value["backend_address_pool_name"]
          # backend_http_settings_name - (optional) is a type of string
          backend_http_settings_name = path_rule.value["backend_http_settings_name"]
          # name - (required) is a type of string
          name = path_rule.value["name"]
          # paths - (required) is a type of list of string
          paths = path_rule.value["paths"]
          # redirect_configuration_name - (optional) is a type of string
          redirect_configuration_name = path_rule.value["redirect_configuration_name"]
          # rewrite_rule_set_name - (optional) is a type of string
          rewrite_rule_set_name = path_rule.value["rewrite_rule_set_name"]
        }
      }

    }
  }

  dynamic "waf_configuration" {
    for_each = var.waf_configuration
    content {
      # enabled - (required) is a type of bool
      enabled = waf_configuration.value["enabled"]
      # file_upload_limit_mb - (optional) is a type of number
      file_upload_limit_mb = waf_configuration.value["file_upload_limit_mb"]
      # firewall_mode - (required) is a type of string
      firewall_mode = waf_configuration.value["firewall_mode"]
      # max_request_body_size_kb - (optional) is a type of number
      max_request_body_size_kb = waf_configuration.value["max_request_body_size_kb"]
      # request_body_check - (optional) is a type of bool
      request_body_check = waf_configuration.value["request_body_check"]
      # rule_set_type - (optional) is a type of string
      rule_set_type = waf_configuration.value["rule_set_type"]
      # rule_set_version - (required) is a type of string
      rule_set_version = waf_configuration.value["rule_set_version"]

      dynamic "disabled_rule_group" {
        for_each = waf_configuration.value.disabled_rule_group
        content {
          # rule_group_name - (required) is a type of string
          rule_group_name = disabled_rule_group.value["rule_group_name"]
          # rules - (optional) is a type of list of number
          rules = disabled_rule_group.value["rules"]
        }
      }

      dynamic "exclusion" {
        for_each = waf_configuration.value.exclusion
        content {
          # match_variable - (required) is a type of string
          match_variable = exclusion.value["match_variable"]
          # selector - (optional) is a type of string
          selector = exclusion.value["selector"]
          # selector_match_operator - (optional) is a type of string
          selector_match_operator = exclusion.value["selector_match_operator"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_application_gateway.this.id
}

output "this" {
  value = azurerm_application_gateway.this
}
```

[top](#index)