# bigip_ltm_policy

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_policy" {
  source = "./modules/bigip/r/bigip_ltm_policy"

  # controls - (optional) is a type of set of string
  controls = []
  # name - (required) is a type of string
  name = null
  # published_copy - (optional) is a type of string
  published_copy = null
  # requires - (optional) is a type of set of string
  requires = []
  # strategy - (optional) is a type of string
  strategy = null

  rule = [{
    action = [{
      app_service          = null
      application          = null
      asm                  = null
      avr                  = null
      cache                = null
      carp                 = null
      category             = null
      classify             = null
      clone_pool           = null
      code                 = null
      compress             = null
      content              = null
      cookie_hash          = null
      cookie_insert        = null
      cookie_passive       = null
      cookie_rewrite       = null
      decompress           = null
      defer                = null
      destination_address  = null
      disable              = null
      domain               = null
      enable               = null
      expiry               = null
      expiry_secs          = null
      expression           = null
      extension            = null
      facility             = null
      forward              = null
      from_profile         = null
      hash                 = null
      host                 = null
      http                 = null
      http_basic_auth      = null
      http_cookie          = null
      http_header          = null
      http_host            = null
      http_referer         = null
      http_reply           = null
      http_set_cookie      = null
      http_uri             = null
      ifile                = null
      insert               = null
      internal_virtual     = null
      ip_address           = null
      key                  = null
      l7dos                = null
      length               = null
      location             = null
      log                  = null
      ltm_policy           = null
      member               = null
      message              = null
      netmask              = null
      nexthop              = null
      node                 = null
      offset               = null
      path                 = null
      pem                  = null
      persist              = null
      pin                  = null
      policy               = null
      pool                 = null
      port                 = null
      priority             = null
      profile              = null
      protocol             = null
      query_string         = null
      rateclass            = null
      redirect             = null
      remove               = null
      replace              = null
      request              = null
      request_adapt        = null
      reset                = null
      response             = null
      response_adapt       = null
      scheme               = null
      script               = null
      select               = null
      server_ssl           = null
      set_variable         = null
      snat                 = null
      snatpool             = null
      source_address       = null
      ssl_client_hello     = null
      ssl_server_handshake = null
      ssl_server_hello     = null
      ssl_session_id       = null
      status               = null
      tcl                  = null
      tcp_nagle            = null
      text                 = null
      timeout              = null
      tm_name              = null
      uie                  = null
      universal            = null
      value                = null
      virtual              = null
      vlan                 = null
      vlan_id              = null
      wam                  = null
      write                = null
    }]
    condition = [{
      address                 = null
      all                     = null
      app_service             = null
      browser_type            = null
      browser_version         = null
      case_insensitive        = null
      case_sensitive          = null
      cipher                  = null
      cipher_bits             = null
      client_ssl              = null
      code                    = null
      common_name             = null
      contains                = null
      continent               = null
      country_code            = null
      country_name            = null
      cpu_usage               = null
      device_make             = null
      device_model            = null
      domain                  = null
      ends_with               = null
      equals                  = null
      expiry                  = null
      extension               = null
      external                = null
      geoip                   = null
      greater                 = null
      greater_or_equal        = null
      host                    = null
      http_basic_auth         = null
      http_cookie             = null
      http_header             = null
      http_host               = null
      http_method             = null
      http_referer            = null
      http_set_cookie         = null
      http_status             = null
      http_uri                = null
      http_user_agent         = null
      http_version            = null
      index                   = null
      internal                = null
      isp                     = null
      last_15secs             = null
      last_1min               = null
      last_5mins              = null
      less                    = null
      less_or_equal           = null
      local                   = null
      major                   = null
      matches                 = null
      minor                   = null
      missing                 = null
      mss                     = null
      not                     = null
      org                     = null
      password                = null
      path                    = null
      path_segment            = null
      port                    = null
      present                 = null
      protocol                = null
      query_parameter         = null
      query_string            = null
      region_code             = null
      region_name             = null
      remote                  = null
      request                 = null
      response                = null
      route_domain            = null
      rtt                     = null
      scheme                  = null
      server_name             = null
      ssl_cert                = null
      ssl_client_hello        = null
      ssl_extension           = null
      ssl_server_handshake    = null
      ssl_server_hello        = null
      starts_with             = null
      tcp                     = null
      text                    = null
      tm_name                 = null
      unnamed_query_parameter = null
      user_agent_token        = null
      username                = null
      value                   = null
      values                  = []
      version                 = null
      vlan                    = null
      vlan_id                 = null
    }]
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "controls" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the Policy"
  type        = string
}

variable "published_copy" {
  description = "(optional) - Publish the Policy"
  type        = string
  default     = null
}

variable "requires" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "strategy" {
  description = "(optional) - Policy Strategy (i.e. /Common/first-match)"
  type        = string
  default     = null
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = list(object(
        {
          app_service          = string
          application          = string
          asm                  = bool
          avr                  = bool
          cache                = bool
          carp                 = bool
          category             = string
          classify             = bool
          clone_pool           = string
          code                 = number
          compress             = bool
          content              = string
          cookie_hash          = bool
          cookie_insert        = bool
          cookie_passive       = bool
          cookie_rewrite       = bool
          decompress           = bool
          defer                = bool
          destination_address  = bool
          disable              = bool
          domain               = string
          enable               = bool
          expiry               = string
          expiry_secs          = number
          expression           = string
          extension            = string
          facility             = string
          forward              = bool
          from_profile         = string
          hash                 = bool
          host                 = string
          http                 = bool
          http_basic_auth      = bool
          http_cookie          = bool
          http_header          = bool
          http_host            = bool
          http_referer         = bool
          http_reply           = bool
          http_set_cookie      = bool
          http_uri             = bool
          ifile                = string
          insert               = bool
          internal_virtual     = string
          ip_address           = string
          key                  = string
          l7dos                = bool
          length               = number
          location             = string
          log                  = bool
          ltm_policy           = bool
          member               = string
          message              = string
          netmask              = string
          nexthop              = string
          node                 = string
          offset               = number
          path                 = string
          pem                  = bool
          persist              = bool
          pin                  = bool
          policy               = string
          pool                 = string
          port                 = number
          priority             = string
          profile              = string
          protocol             = string
          query_string         = string
          rateclass            = string
          redirect             = bool
          remove               = bool
          replace              = bool
          request              = bool
          request_adapt        = bool
          reset                = bool
          response             = bool
          response_adapt       = bool
          scheme               = string
          script               = string
          select               = bool
          server_ssl           = bool
          set_variable         = bool
          snat                 = string
          snatpool             = string
          source_address       = bool
          ssl_client_hello     = bool
          ssl_server_handshake = bool
          ssl_server_hello     = bool
          ssl_session_id       = bool
          status               = number
          tcl                  = bool
          tcp_nagle            = bool
          text                 = string
          timeout              = number
          tm_name              = string
          uie                  = bool
          universal            = bool
          value                = string
          virtual              = string
          vlan                 = string
          vlan_id              = number
          wam                  = bool
          write                = bool
        }
      ))
      condition = list(object(
        {
          address                 = bool
          all                     = bool
          app_service             = string
          browser_type            = bool
          browser_version         = bool
          case_insensitive        = bool
          case_sensitive          = bool
          cipher                  = bool
          cipher_bits             = bool
          client_ssl              = bool
          code                    = bool
          common_name             = bool
          contains                = bool
          continent               = bool
          country_code            = bool
          country_name            = bool
          cpu_usage               = bool
          device_make             = bool
          device_model            = bool
          domain                  = bool
          ends_with               = bool
          equals                  = bool
          expiry                  = bool
          extension               = bool
          external                = bool
          geoip                   = bool
          greater                 = bool
          greater_or_equal        = bool
          host                    = bool
          http_basic_auth         = bool
          http_cookie             = bool
          http_header             = bool
          http_host               = bool
          http_method             = bool
          http_referer            = bool
          http_set_cookie         = bool
          http_status             = bool
          http_uri                = bool
          http_user_agent         = bool
          http_version            = bool
          index                   = number
          internal                = bool
          isp                     = bool
          last_15secs             = bool
          last_1min               = bool
          last_5mins              = bool
          less                    = bool
          less_or_equal           = bool
          local                   = bool
          major                   = bool
          matches                 = bool
          minor                   = bool
          missing                 = bool
          mss                     = bool
          not                     = bool
          org                     = bool
          password                = bool
          path                    = bool
          path_segment            = bool
          port                    = bool
          present                 = bool
          protocol                = bool
          query_parameter         = bool
          query_string            = bool
          region_code             = bool
          region_name             = bool
          remote                  = bool
          request                 = bool
          response                = bool
          route_domain            = bool
          rtt                     = bool
          scheme                  = bool
          server_name             = bool
          ssl_cert                = bool
          ssl_client_hello        = bool
          ssl_extension           = bool
          ssl_server_handshake    = bool
          ssl_server_hello        = bool
          starts_with             = bool
          tcp                     = bool
          text                    = bool
          tm_name                 = string
          unnamed_query_parameter = bool
          user_agent_token        = bool
          username                = bool
          value                   = bool
          values                  = list(string)
          version                 = bool
          vlan                    = bool
          vlan_id                 = bool
        }
      ))
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_policy" "this" {
  controls       = var.controls
  name           = var.name
  published_copy = var.published_copy
  requires       = var.requires
  strategy       = var.strategy

  dynamic "rule" {
    for_each = var.rule
    content {
      name = rule.value["name"]

      dynamic "action" {
        for_each = rule.value.action
        content {
          app_service          = action.value["app_service"]
          application          = action.value["application"]
          asm                  = action.value["asm"]
          avr                  = action.value["avr"]
          cache                = action.value["cache"]
          carp                 = action.value["carp"]
          category             = action.value["category"]
          classify             = action.value["classify"]
          clone_pool           = action.value["clone_pool"]
          code                 = action.value["code"]
          compress             = action.value["compress"]
          content              = action.value["content"]
          cookie_hash          = action.value["cookie_hash"]
          cookie_insert        = action.value["cookie_insert"]
          cookie_passive       = action.value["cookie_passive"]
          cookie_rewrite       = action.value["cookie_rewrite"]
          decompress           = action.value["decompress"]
          defer                = action.value["defer"]
          destination_address  = action.value["destination_address"]
          disable              = action.value["disable"]
          domain               = action.value["domain"]
          enable               = action.value["enable"]
          expiry               = action.value["expiry"]
          expiry_secs          = action.value["expiry_secs"]
          expression           = action.value["expression"]
          extension            = action.value["extension"]
          facility             = action.value["facility"]
          forward              = action.value["forward"]
          from_profile         = action.value["from_profile"]
          hash                 = action.value["hash"]
          host                 = action.value["host"]
          http                 = action.value["http"]
          http_basic_auth      = action.value["http_basic_auth"]
          http_cookie          = action.value["http_cookie"]
          http_header          = action.value["http_header"]
          http_host            = action.value["http_host"]
          http_referer         = action.value["http_referer"]
          http_reply           = action.value["http_reply"]
          http_set_cookie      = action.value["http_set_cookie"]
          http_uri             = action.value["http_uri"]
          ifile                = action.value["ifile"]
          insert               = action.value["insert"]
          internal_virtual     = action.value["internal_virtual"]
          ip_address           = action.value["ip_address"]
          key                  = action.value["key"]
          l7dos                = action.value["l7dos"]
          length               = action.value["length"]
          location             = action.value["location"]
          log                  = action.value["log"]
          ltm_policy           = action.value["ltm_policy"]
          member               = action.value["member"]
          message              = action.value["message"]
          netmask              = action.value["netmask"]
          nexthop              = action.value["nexthop"]
          node                 = action.value["node"]
          offset               = action.value["offset"]
          path                 = action.value["path"]
          pem                  = action.value["pem"]
          persist              = action.value["persist"]
          pin                  = action.value["pin"]
          policy               = action.value["policy"]
          pool                 = action.value["pool"]
          port                 = action.value["port"]
          priority             = action.value["priority"]
          profile              = action.value["profile"]
          protocol             = action.value["protocol"]
          query_string         = action.value["query_string"]
          rateclass            = action.value["rateclass"]
          redirect             = action.value["redirect"]
          remove               = action.value["remove"]
          replace              = action.value["replace"]
          request              = action.value["request"]
          request_adapt        = action.value["request_adapt"]
          reset                = action.value["reset"]
          response             = action.value["response"]
          response_adapt       = action.value["response_adapt"]
          scheme               = action.value["scheme"]
          script               = action.value["script"]
          select               = action.value["select"]
          server_ssl           = action.value["server_ssl"]
          set_variable         = action.value["set_variable"]
          snat                 = action.value["snat"]
          snatpool             = action.value["snatpool"]
          source_address       = action.value["source_address"]
          ssl_client_hello     = action.value["ssl_client_hello"]
          ssl_server_handshake = action.value["ssl_server_handshake"]
          ssl_server_hello     = action.value["ssl_server_hello"]
          ssl_session_id       = action.value["ssl_session_id"]
          status               = action.value["status"]
          tcl                  = action.value["tcl"]
          tcp_nagle            = action.value["tcp_nagle"]
          text                 = action.value["text"]
          timeout              = action.value["timeout"]
          tm_name              = action.value["tm_name"]
          uie                  = action.value["uie"]
          universal            = action.value["universal"]
          value                = action.value["value"]
          virtual              = action.value["virtual"]
          vlan                 = action.value["vlan"]
          vlan_id              = action.value["vlan_id"]
          wam                  = action.value["wam"]
          write                = action.value["write"]
        }
      }

      dynamic "condition" {
        for_each = rule.value.condition
        content {
          address                 = condition.value["address"]
          all                     = condition.value["all"]
          app_service             = condition.value["app_service"]
          browser_type            = condition.value["browser_type"]
          browser_version         = condition.value["browser_version"]
          case_insensitive        = condition.value["case_insensitive"]
          case_sensitive          = condition.value["case_sensitive"]
          cipher                  = condition.value["cipher"]
          cipher_bits             = condition.value["cipher_bits"]
          client_ssl              = condition.value["client_ssl"]
          code                    = condition.value["code"]
          common_name             = condition.value["common_name"]
          contains                = condition.value["contains"]
          continent               = condition.value["continent"]
          country_code            = condition.value["country_code"]
          country_name            = condition.value["country_name"]
          cpu_usage               = condition.value["cpu_usage"]
          device_make             = condition.value["device_make"]
          device_model            = condition.value["device_model"]
          domain                  = condition.value["domain"]
          ends_with               = condition.value["ends_with"]
          equals                  = condition.value["equals"]
          expiry                  = condition.value["expiry"]
          extension               = condition.value["extension"]
          external                = condition.value["external"]
          geoip                   = condition.value["geoip"]
          greater                 = condition.value["greater"]
          greater_or_equal        = condition.value["greater_or_equal"]
          host                    = condition.value["host"]
          http_basic_auth         = condition.value["http_basic_auth"]
          http_cookie             = condition.value["http_cookie"]
          http_header             = condition.value["http_header"]
          http_host               = condition.value["http_host"]
          http_method             = condition.value["http_method"]
          http_referer            = condition.value["http_referer"]
          http_set_cookie         = condition.value["http_set_cookie"]
          http_status             = condition.value["http_status"]
          http_uri                = condition.value["http_uri"]
          http_user_agent         = condition.value["http_user_agent"]
          http_version            = condition.value["http_version"]
          index                   = condition.value["index"]
          internal                = condition.value["internal"]
          isp                     = condition.value["isp"]
          last_15secs             = condition.value["last_15secs"]
          last_1min               = condition.value["last_1min"]
          last_5mins              = condition.value["last_5mins"]
          less                    = condition.value["less"]
          less_or_equal           = condition.value["less_or_equal"]
          local                   = condition.value["local"]
          major                   = condition.value["major"]
          matches                 = condition.value["matches"]
          minor                   = condition.value["minor"]
          missing                 = condition.value["missing"]
          mss                     = condition.value["mss"]
          not                     = condition.value["not"]
          org                     = condition.value["org"]
          password                = condition.value["password"]
          path                    = condition.value["path"]
          path_segment            = condition.value["path_segment"]
          port                    = condition.value["port"]
          present                 = condition.value["present"]
          protocol                = condition.value["protocol"]
          query_parameter         = condition.value["query_parameter"]
          query_string            = condition.value["query_string"]
          region_code             = condition.value["region_code"]
          region_name             = condition.value["region_name"]
          remote                  = condition.value["remote"]
          request                 = condition.value["request"]
          response                = condition.value["response"]
          route_domain            = condition.value["route_domain"]
          rtt                     = condition.value["rtt"]
          scheme                  = condition.value["scheme"]
          server_name             = condition.value["server_name"]
          ssl_cert                = condition.value["ssl_cert"]
          ssl_client_hello        = condition.value["ssl_client_hello"]
          ssl_extension           = condition.value["ssl_extension"]
          ssl_server_handshake    = condition.value["ssl_server_handshake"]
          ssl_server_hello        = condition.value["ssl_server_hello"]
          starts_with             = condition.value["starts_with"]
          tcp                     = condition.value["tcp"]
          text                    = condition.value["text"]
          tm_name                 = condition.value["tm_name"]
          unnamed_query_parameter = condition.value["unnamed_query_parameter"]
          user_agent_token        = condition.value["user_agent_token"]
          username                = condition.value["username"]
          value                   = condition.value["value"]
          values                  = condition.value["values"]
          version                 = condition.value["version"]
          vlan                    = condition.value["vlan"]
          vlan_id                 = condition.value["vlan_id"]
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
  value       = bigip_ltm_policy.this.id
}

output "this" {
  value = bigip_ltm_policy.this
}
```

[top](#index)