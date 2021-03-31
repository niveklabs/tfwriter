# avi_systemconfiguration

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_systemconfiguration" {
  source = "./modules/avi/r/avi_systemconfiguration"

  # default_license_tier - (optional) is a type of string
  default_license_tier = null
  # dns_virtualservice_refs - (optional) is a type of list of string
  dns_virtualservice_refs = []
  # docker_mode - (optional) is a type of bool
  docker_mode = null
  # ssh_ciphers - (optional) is a type of list of string
  ssh_ciphers = []
  # ssh_hmacs - (optional) is a type of list of string
  ssh_hmacs = []
  # uuid - (optional) is a type of string
  uuid = null
  # welcome_workflow_complete - (optional) is a type of bool
  welcome_workflow_complete = null

  admin_auth_configuration = [{
    allow_local_user_login = null
    auth_profile_ref       = null
    mapping_rules = [{
      assign_policy = null
      assign_role   = null
      assign_tenant = null
      attribute_match = [{
        criteria = null
        name     = null
        values   = []
      }]
      group_match = [{
        criteria = null
        groups   = []
      }]
      index                     = null
      is_superuser              = null
      object_access_policy_refs = []
      policy_attribute_name     = null
      role_attribute_name       = null
      role_refs                 = []
      tenant_attribute_name     = null
      tenant_refs               = []
    }]
  }]

  dns_configuration = [{
    search_domain = null
    server_list = [{
      addr = null
      type = null
    }]
  }]

  email_configuration = [{
    auth_password    = null
    auth_username    = null
    disable_tls      = null
    from_email       = null
    mail_server_name = null
    mail_server_port = null
    smtp_type        = null
  }]

  global_tenant_config = [{
    se_in_provider_context       = null
    tenant_access_to_provider_se = null
    tenant_vrf                   = null
  }]

  linux_configuration = [{
    banner   = null
    cis_mode = null
    motd     = null
  }]

  mgmt_ip_access_control = [{
    api_access = [{
      addrs = [{
        addr = null
        type = null
      }]
      group_refs     = []
      match_criteria = null
      prefixes = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      ranges = [{
        begin = [{
          addr = null
          type = null
        }]
        end = [{
          addr = null
          type = null
        }]
      }]
    }]
    shell_server_access = [{
      addrs = [{
        addr = null
        type = null
      }]
      group_refs     = []
      match_criteria = null
      prefixes = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      ranges = [{
        begin = [{
          addr = null
          type = null
        }]
        end = [{
          addr = null
          type = null
        }]
      }]
    }]
    snmp_access = [{
      addrs = [{
        addr = null
        type = null
      }]
      group_refs     = []
      match_criteria = null
      prefixes = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      ranges = [{
        begin = [{
          addr = null
          type = null
        }]
        end = [{
          addr = null
          type = null
        }]
      }]
    }]
    ssh_access = [{
      addrs = [{
        addr = null
        type = null
      }]
      group_refs     = []
      match_criteria = null
      prefixes = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      ranges = [{
        begin = [{
          addr = null
          type = null
        }]
        end = [{
          addr = null
          type = null
        }]
      }]
    }]
    sysint_access = [{
      addrs = [{
        addr = null
        type = null
      }]
      group_refs     = []
      match_criteria = null
      prefixes = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      ranges = [{
        begin = [{
          addr = null
          type = null
        }]
        end = [{
          addr = null
          type = null
        }]
      }]
    }]
  }]

  ntp_configuration = [{
    ntp_authentication_keys = [{
      algorithm  = null
      key        = null
      key_number = null
    }]
    ntp_server_list = [{
      addr = null
      type = null
    }]
    ntp_servers = [{
      key_number = null
      server = [{
        addr = null
        type = null
      }]
    }]
  }]

  portal_configuration = [{
    allow_basic_authentication     = null
    api_force_timeout              = null
    disable_remote_cli_shell       = null
    disable_swagger                = null
    enable_clickjacking_protection = null
    enable_http                    = null
    enable_https                   = null
    http_port                      = null
    https_port                     = null
    password_strength_check        = null
    redirect_to_https              = null
    sslkeyandcertificate_refs      = []
    sslprofile_ref                 = null
    use_uuid_from_input            = null
  }]

  proxy_configuration = [{
    host     = null
    password = null
    port     = null
    username = null
  }]

  secure_channel_configuration = [{
    sslkeyandcertificate_refs = []
  }]

  snmp_configuration = [{
    community          = null
    large_trap_payload = null
    snmp_v3_config = [{
      engine_id = null
      user = [{
        auth_passphrase = null
        auth_type       = null
        priv_passphrase = null
        priv_type       = null
        username        = null
      }]
    }]
    sys_contact  = null
    sys_location = null
    version      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_license_tier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_virtualservice_refs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "docker_mode" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ssh_ciphers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ssh_hmacs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "welcome_workflow_complete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "admin_auth_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      allow_local_user_login = bool
      auth_profile_ref       = string
      mapping_rules = list(object(
        {
          assign_policy = string
          assign_role   = string
          assign_tenant = string
          attribute_match = set(object(
            {
              criteria = string
              name     = string
              values   = list(string)
            }
          ))
          group_match = set(object(
            {
              criteria = string
              groups   = list(string)
            }
          ))
          index                     = number
          is_superuser              = bool
          object_access_policy_refs = list(string)
          policy_attribute_name     = string
          role_attribute_name       = string
          role_refs                 = list(string)
          tenant_attribute_name     = string
          tenant_refs               = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "dns_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      search_domain = string
      server_list = list(object(
        {
          addr = string
          type = string
        }
      ))
    }
  ))
  default = []
}

variable "email_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      auth_password    = string
      auth_username    = string
      disable_tls      = bool
      from_email       = string
      mail_server_name = string
      mail_server_port = number
      smtp_type        = string
    }
  ))
  default = []
}

variable "global_tenant_config" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      se_in_provider_context       = bool
      tenant_access_to_provider_se = bool
      tenant_vrf                   = bool
    }
  ))
  default = []
}

variable "linux_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      banner   = string
      cis_mode = bool
      motd     = string
    }
  ))
  default = []
}

variable "mgmt_ip_access_control" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      api_access = set(object(
        {
          addrs = list(object(
            {
              addr = string
              type = string
            }
          ))
          group_refs     = list(string)
          match_criteria = string
          prefixes = list(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          ranges = list(object(
            {
              begin = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              end = set(object(
                {
                  addr = string
                  type = string
                }
              ))
            }
          ))
        }
      ))
      shell_server_access = set(object(
        {
          addrs = list(object(
            {
              addr = string
              type = string
            }
          ))
          group_refs     = list(string)
          match_criteria = string
          prefixes = list(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          ranges = list(object(
            {
              begin = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              end = set(object(
                {
                  addr = string
                  type = string
                }
              ))
            }
          ))
        }
      ))
      snmp_access = set(object(
        {
          addrs = list(object(
            {
              addr = string
              type = string
            }
          ))
          group_refs     = list(string)
          match_criteria = string
          prefixes = list(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          ranges = list(object(
            {
              begin = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              end = set(object(
                {
                  addr = string
                  type = string
                }
              ))
            }
          ))
        }
      ))
      ssh_access = set(object(
        {
          addrs = list(object(
            {
              addr = string
              type = string
            }
          ))
          group_refs     = list(string)
          match_criteria = string
          prefixes = list(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          ranges = list(object(
            {
              begin = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              end = set(object(
                {
                  addr = string
                  type = string
                }
              ))
            }
          ))
        }
      ))
      sysint_access = set(object(
        {
          addrs = list(object(
            {
              addr = string
              type = string
            }
          ))
          group_refs     = list(string)
          match_criteria = string
          prefixes = list(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          ranges = list(object(
            {
              begin = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              end = set(object(
                {
                  addr = string
                  type = string
                }
              ))
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "ntp_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ntp_authentication_keys = list(object(
        {
          algorithm  = string
          key        = string
          key_number = number
        }
      ))
      ntp_server_list = list(object(
        {
          addr = string
          type = string
        }
      ))
      ntp_servers = list(object(
        {
          key_number = number
          server = set(object(
            {
              addr = string
              type = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "portal_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      allow_basic_authentication     = bool
      api_force_timeout              = number
      disable_remote_cli_shell       = bool
      disable_swagger                = bool
      enable_clickjacking_protection = bool
      enable_http                    = bool
      enable_https                   = bool
      http_port                      = number
      https_port                     = number
      password_strength_check        = bool
      redirect_to_https              = bool
      sslkeyandcertificate_refs      = list(string)
      sslprofile_ref                 = string
      use_uuid_from_input            = bool
    }
  ))
  default = []
}

variable "proxy_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      host     = string
      password = string
      port     = number
      username = string
    }
  ))
  default = []
}

variable "secure_channel_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      sslkeyandcertificate_refs = list(string)
    }
  ))
  default = []
}

variable "snmp_configuration" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      community          = string
      large_trap_payload = bool
      snmp_v3_config = set(object(
        {
          engine_id = string
          user = set(object(
            {
              auth_passphrase = string
              auth_type       = string
              priv_passphrase = string
              priv_type       = string
              username        = string
            }
          ))
        }
      ))
      sys_contact  = string
      sys_location = string
      version      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_systemconfiguration" "this" {
  default_license_tier      = var.default_license_tier
  dns_virtualservice_refs   = var.dns_virtualservice_refs
  docker_mode               = var.docker_mode
  ssh_ciphers               = var.ssh_ciphers
  ssh_hmacs                 = var.ssh_hmacs
  uuid                      = var.uuid
  welcome_workflow_complete = var.welcome_workflow_complete

  dynamic "admin_auth_configuration" {
    for_each = var.admin_auth_configuration
    content {
      allow_local_user_login = admin_auth_configuration.value["allow_local_user_login"]
      auth_profile_ref       = admin_auth_configuration.value["auth_profile_ref"]

      dynamic "mapping_rules" {
        for_each = admin_auth_configuration.value.mapping_rules
        content {
          assign_policy             = mapping_rules.value["assign_policy"]
          assign_role               = mapping_rules.value["assign_role"]
          assign_tenant             = mapping_rules.value["assign_tenant"]
          index                     = mapping_rules.value["index"]
          is_superuser              = mapping_rules.value["is_superuser"]
          object_access_policy_refs = mapping_rules.value["object_access_policy_refs"]
          policy_attribute_name     = mapping_rules.value["policy_attribute_name"]
          role_attribute_name       = mapping_rules.value["role_attribute_name"]
          role_refs                 = mapping_rules.value["role_refs"]
          tenant_attribute_name     = mapping_rules.value["tenant_attribute_name"]
          tenant_refs               = mapping_rules.value["tenant_refs"]

          dynamic "attribute_match" {
            for_each = mapping_rules.value.attribute_match
            content {
              criteria = attribute_match.value["criteria"]
              name     = attribute_match.value["name"]
              values   = attribute_match.value["values"]
            }
          }

          dynamic "group_match" {
            for_each = mapping_rules.value.group_match
            content {
              criteria = group_match.value["criteria"]
              groups   = group_match.value["groups"]
            }
          }

        }
      }

    }
  }

  dynamic "dns_configuration" {
    for_each = var.dns_configuration
    content {
      search_domain = dns_configuration.value["search_domain"]

      dynamic "server_list" {
        for_each = dns_configuration.value.server_list
        content {
          addr = server_list.value["addr"]
          type = server_list.value["type"]
        }
      }

    }
  }

  dynamic "email_configuration" {
    for_each = var.email_configuration
    content {
      auth_password    = email_configuration.value["auth_password"]
      auth_username    = email_configuration.value["auth_username"]
      disable_tls      = email_configuration.value["disable_tls"]
      from_email       = email_configuration.value["from_email"]
      mail_server_name = email_configuration.value["mail_server_name"]
      mail_server_port = email_configuration.value["mail_server_port"]
      smtp_type        = email_configuration.value["smtp_type"]
    }
  }

  dynamic "global_tenant_config" {
    for_each = var.global_tenant_config
    content {
      se_in_provider_context       = global_tenant_config.value["se_in_provider_context"]
      tenant_access_to_provider_se = global_tenant_config.value["tenant_access_to_provider_se"]
      tenant_vrf                   = global_tenant_config.value["tenant_vrf"]
    }
  }

  dynamic "linux_configuration" {
    for_each = var.linux_configuration
    content {
      banner   = linux_configuration.value["banner"]
      cis_mode = linux_configuration.value["cis_mode"]
      motd     = linux_configuration.value["motd"]
    }
  }

  dynamic "mgmt_ip_access_control" {
    for_each = var.mgmt_ip_access_control
    content {

      dynamic "api_access" {
        for_each = mgmt_ip_access_control.value.api_access
        content {
          group_refs     = api_access.value["group_refs"]
          match_criteria = api_access.value["match_criteria"]

          dynamic "addrs" {
            for_each = api_access.value.addrs
            content {
              addr = addrs.value["addr"]
              type = addrs.value["type"]
            }
          }

          dynamic "prefixes" {
            for_each = api_access.value.prefixes
            content {
              mask = prefixes.value["mask"]

              dynamic "ip_addr" {
                for_each = prefixes.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "ranges" {
            for_each = api_access.value.ranges
            content {

              dynamic "begin" {
                for_each = ranges.value.begin
                content {
                  addr = begin.value["addr"]
                  type = begin.value["type"]
                }
              }

              dynamic "end" {
                for_each = ranges.value.end
                content {
                  addr = end.value["addr"]
                  type = end.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "shell_server_access" {
        for_each = mgmt_ip_access_control.value.shell_server_access
        content {
          group_refs     = shell_server_access.value["group_refs"]
          match_criteria = shell_server_access.value["match_criteria"]

          dynamic "addrs" {
            for_each = shell_server_access.value.addrs
            content {
              addr = addrs.value["addr"]
              type = addrs.value["type"]
            }
          }

          dynamic "prefixes" {
            for_each = shell_server_access.value.prefixes
            content {
              mask = prefixes.value["mask"]

              dynamic "ip_addr" {
                for_each = prefixes.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "ranges" {
            for_each = shell_server_access.value.ranges
            content {

              dynamic "begin" {
                for_each = ranges.value.begin
                content {
                  addr = begin.value["addr"]
                  type = begin.value["type"]
                }
              }

              dynamic "end" {
                for_each = ranges.value.end
                content {
                  addr = end.value["addr"]
                  type = end.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "snmp_access" {
        for_each = mgmt_ip_access_control.value.snmp_access
        content {
          group_refs     = snmp_access.value["group_refs"]
          match_criteria = snmp_access.value["match_criteria"]

          dynamic "addrs" {
            for_each = snmp_access.value.addrs
            content {
              addr = addrs.value["addr"]
              type = addrs.value["type"]
            }
          }

          dynamic "prefixes" {
            for_each = snmp_access.value.prefixes
            content {
              mask = prefixes.value["mask"]

              dynamic "ip_addr" {
                for_each = prefixes.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "ranges" {
            for_each = snmp_access.value.ranges
            content {

              dynamic "begin" {
                for_each = ranges.value.begin
                content {
                  addr = begin.value["addr"]
                  type = begin.value["type"]
                }
              }

              dynamic "end" {
                for_each = ranges.value.end
                content {
                  addr = end.value["addr"]
                  type = end.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "ssh_access" {
        for_each = mgmt_ip_access_control.value.ssh_access
        content {
          group_refs     = ssh_access.value["group_refs"]
          match_criteria = ssh_access.value["match_criteria"]

          dynamic "addrs" {
            for_each = ssh_access.value.addrs
            content {
              addr = addrs.value["addr"]
              type = addrs.value["type"]
            }
          }

          dynamic "prefixes" {
            for_each = ssh_access.value.prefixes
            content {
              mask = prefixes.value["mask"]

              dynamic "ip_addr" {
                for_each = prefixes.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "ranges" {
            for_each = ssh_access.value.ranges
            content {

              dynamic "begin" {
                for_each = ranges.value.begin
                content {
                  addr = begin.value["addr"]
                  type = begin.value["type"]
                }
              }

              dynamic "end" {
                for_each = ranges.value.end
                content {
                  addr = end.value["addr"]
                  type = end.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "sysint_access" {
        for_each = mgmt_ip_access_control.value.sysint_access
        content {
          group_refs     = sysint_access.value["group_refs"]
          match_criteria = sysint_access.value["match_criteria"]

          dynamic "addrs" {
            for_each = sysint_access.value.addrs
            content {
              addr = addrs.value["addr"]
              type = addrs.value["type"]
            }
          }

          dynamic "prefixes" {
            for_each = sysint_access.value.prefixes
            content {
              mask = prefixes.value["mask"]

              dynamic "ip_addr" {
                for_each = prefixes.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "ranges" {
            for_each = sysint_access.value.ranges
            content {

              dynamic "begin" {
                for_each = ranges.value.begin
                content {
                  addr = begin.value["addr"]
                  type = begin.value["type"]
                }
              }

              dynamic "end" {
                for_each = ranges.value.end
                content {
                  addr = end.value["addr"]
                  type = end.value["type"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "ntp_configuration" {
    for_each = var.ntp_configuration
    content {

      dynamic "ntp_authentication_keys" {
        for_each = ntp_configuration.value.ntp_authentication_keys
        content {
          algorithm  = ntp_authentication_keys.value["algorithm"]
          key        = ntp_authentication_keys.value["key"]
          key_number = ntp_authentication_keys.value["key_number"]
        }
      }

      dynamic "ntp_server_list" {
        for_each = ntp_configuration.value.ntp_server_list
        content {
          addr = ntp_server_list.value["addr"]
          type = ntp_server_list.value["type"]
        }
      }

      dynamic "ntp_servers" {
        for_each = ntp_configuration.value.ntp_servers
        content {
          key_number = ntp_servers.value["key_number"]

          dynamic "server" {
            for_each = ntp_servers.value.server
            content {
              addr = server.value["addr"]
              type = server.value["type"]
            }
          }

        }
      }

    }
  }

  dynamic "portal_configuration" {
    for_each = var.portal_configuration
    content {
      allow_basic_authentication     = portal_configuration.value["allow_basic_authentication"]
      api_force_timeout              = portal_configuration.value["api_force_timeout"]
      disable_remote_cli_shell       = portal_configuration.value["disable_remote_cli_shell"]
      disable_swagger                = portal_configuration.value["disable_swagger"]
      enable_clickjacking_protection = portal_configuration.value["enable_clickjacking_protection"]
      enable_http                    = portal_configuration.value["enable_http"]
      enable_https                   = portal_configuration.value["enable_https"]
      http_port                      = portal_configuration.value["http_port"]
      https_port                     = portal_configuration.value["https_port"]
      password_strength_check        = portal_configuration.value["password_strength_check"]
      redirect_to_https              = portal_configuration.value["redirect_to_https"]
      sslkeyandcertificate_refs      = portal_configuration.value["sslkeyandcertificate_refs"]
      sslprofile_ref                 = portal_configuration.value["sslprofile_ref"]
      use_uuid_from_input            = portal_configuration.value["use_uuid_from_input"]
    }
  }

  dynamic "proxy_configuration" {
    for_each = var.proxy_configuration
    content {
      host     = proxy_configuration.value["host"]
      password = proxy_configuration.value["password"]
      port     = proxy_configuration.value["port"]
      username = proxy_configuration.value["username"]
    }
  }

  dynamic "secure_channel_configuration" {
    for_each = var.secure_channel_configuration
    content {
      sslkeyandcertificate_refs = secure_channel_configuration.value["sslkeyandcertificate_refs"]
    }
  }

  dynamic "snmp_configuration" {
    for_each = var.snmp_configuration
    content {
      community          = snmp_configuration.value["community"]
      large_trap_payload = snmp_configuration.value["large_trap_payload"]
      sys_contact        = snmp_configuration.value["sys_contact"]
      sys_location       = snmp_configuration.value["sys_location"]
      version            = snmp_configuration.value["version"]

      dynamic "snmp_v3_config" {
        for_each = snmp_configuration.value.snmp_v3_config
        content {
          engine_id = snmp_v3_config.value["engine_id"]

          dynamic "user" {
            for_each = snmp_v3_config.value.user
            content {
              auth_passphrase = user.value["auth_passphrase"]
              auth_type       = user.value["auth_type"]
              priv_passphrase = user.value["priv_passphrase"]
              priv_type       = user.value["priv_type"]
              username        = user.value["username"]
            }
          }

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
  value       = avi_systemconfiguration.this.id
}

output "uuid" {
  description = "returns a string"
  value       = avi_systemconfiguration.this.uuid
}

output "this" {
  value = avi_systemconfiguration.this
}
```

[top](#index)