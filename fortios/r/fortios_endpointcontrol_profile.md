# fortios_endpointcontrol_profile

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_endpointcontrol_profile" {
  source = "./modules/fortios/r/fortios_endpointcontrol_profile"

  # description - (optional) is a type of string
  description = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # profile_name - (optional) is a type of string
  profile_name = null
  # replacemsg_override_group - (optional) is a type of string
  replacemsg_override_group = null

  device_groups = [{
    name = null
  }]

  forticlient_android_settings = [{
    disable_wf_when_protected       = null
    forticlient_advanced_vpn        = null
    forticlient_advanced_vpn_buffer = null
    forticlient_vpn_provisioning    = null
    forticlient_vpn_settings = [{
      auth_method                = null
      name                       = null
      preshared_key              = null
      remote_gw                  = null
      sslvpn_access_port         = null
      sslvpn_require_certificate = null
      type                       = null
    }]
    forticlient_wf         = null
    forticlient_wf_profile = null
  }]

  forticlient_ios_settings = [{
    client_vpn_provisioning = null
    client_vpn_settings = [{
      auth_method                = null
      name                       = null
      preshared_key              = null
      remote_gw                  = null
      sslvpn_access_port         = null
      sslvpn_require_certificate = null
      type                       = null
      vpn_configuration_content  = null
      vpn_configuration_name     = null
    }]
    configuration_content            = null
    configuration_name               = null
    disable_wf_when_protected        = null
    distribute_configuration_profile = null
    forticlient_wf                   = null
    forticlient_wf_profile           = null
  }]

  forticlient_winmac_settings = [{
    av_realtime_protection                = null
    av_signature_up_to_date               = null
    forticlient_application_firewall      = null
    forticlient_application_firewall_list = null
    forticlient_av                        = null
    forticlient_ems_compliance            = null
    forticlient_ems_compliance_action     = null
    forticlient_ems_entries = [{
      name = null
    }]
    forticlient_linux_ver                = null
    forticlient_log_upload               = null
    forticlient_log_upload_level         = null
    forticlient_log_upload_server        = null
    forticlient_mac_ver                  = null
    forticlient_minimum_software_version = null
    forticlient_operating_system = [{
      id      = null
      os_name = null
      os_type = null
    }]
    forticlient_own_file = [{
      file = null
      id   = null
    }]
    forticlient_registration_compliance_action = null
    forticlient_registry_entry = [{
      id             = null
      registry_entry = null
    }]
    forticlient_running_app = [{
      app_name               = null
      app_sha256_signature   = null
      app_sha256_signature2  = null
      app_sha256_signature3  = null
      app_sha256_signature4  = null
      application_check_rule = null
      id                     = null
      process_name           = null
      process_name2          = null
      process_name3          = null
      process_name4          = null
    }]
    forticlient_security_posture                   = null
    forticlient_security_posture_compliance_action = null
    forticlient_system_compliance                  = null
    forticlient_system_compliance_action           = null
    forticlient_vuln_scan                          = null
    forticlient_vuln_scan_compliance_action        = null
    forticlient_vuln_scan_enforce                  = null
    forticlient_vuln_scan_enforce_grace            = null
    forticlient_vuln_scan_exempt                   = null
    forticlient_wf                                 = null
    forticlient_wf_profile                         = null
    forticlient_win_ver                            = null
    os_av_software_installed                       = null
    sandbox_address                                = null
    sandbox_analysis                               = null
  }]

  on_net_addr = [{
    name = null
  }]

  src_addr = [{
    name = null
  }]

  user_groups = [{
    name = null
  }]

  users = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "replacemsg_override_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_groups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "forticlient_android_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disable_wf_when_protected       = string
      forticlient_advanced_vpn        = string
      forticlient_advanced_vpn_buffer = string
      forticlient_vpn_provisioning    = string
      forticlient_vpn_settings = list(object(
        {
          auth_method                = string
          name                       = string
          preshared_key              = string
          remote_gw                  = string
          sslvpn_access_port         = number
          sslvpn_require_certificate = string
          type                       = string
        }
      ))
      forticlient_wf         = string
      forticlient_wf_profile = string
    }
  ))
  default = []
}

variable "forticlient_ios_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_vpn_provisioning = string
      client_vpn_settings = list(object(
        {
          auth_method                = string
          name                       = string
          preshared_key              = string
          remote_gw                  = string
          sslvpn_access_port         = number
          sslvpn_require_certificate = string
          type                       = string
          vpn_configuration_content  = string
          vpn_configuration_name     = string
        }
      ))
      configuration_content            = string
      configuration_name               = string
      disable_wf_when_protected        = string
      distribute_configuration_profile = string
      forticlient_wf                   = string
      forticlient_wf_profile           = string
    }
  ))
  default = []
}

variable "forticlient_winmac_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      av_realtime_protection                = string
      av_signature_up_to_date               = string
      forticlient_application_firewall      = string
      forticlient_application_firewall_list = string
      forticlient_av                        = string
      forticlient_ems_compliance            = string
      forticlient_ems_compliance_action     = string
      forticlient_ems_entries = list(object(
        {
          name = string
        }
      ))
      forticlient_linux_ver                = string
      forticlient_log_upload               = string
      forticlient_log_upload_level         = string
      forticlient_log_upload_server        = string
      forticlient_mac_ver                  = string
      forticlient_minimum_software_version = string
      forticlient_operating_system = list(object(
        {
          id      = number
          os_name = string
          os_type = string
        }
      ))
      forticlient_own_file = list(object(
        {
          file = string
          id   = number
        }
      ))
      forticlient_registration_compliance_action = string
      forticlient_registry_entry = list(object(
        {
          id             = number
          registry_entry = string
        }
      ))
      forticlient_running_app = list(object(
        {
          app_name               = string
          app_sha256_signature   = string
          app_sha256_signature2  = string
          app_sha256_signature3  = string
          app_sha256_signature4  = string
          application_check_rule = string
          id                     = number
          process_name           = string
          process_name2          = string
          process_name3          = string
          process_name4          = string
        }
      ))
      forticlient_security_posture                   = string
      forticlient_security_posture_compliance_action = string
      forticlient_system_compliance                  = string
      forticlient_system_compliance_action           = string
      forticlient_vuln_scan                          = string
      forticlient_vuln_scan_compliance_action        = string
      forticlient_vuln_scan_enforce                  = string
      forticlient_vuln_scan_enforce_grace            = number
      forticlient_vuln_scan_exempt                   = string
      forticlient_wf                                 = string
      forticlient_wf_profile                         = string
      forticlient_win_ver                            = string
      os_av_software_installed                       = string
      sandbox_address                                = string
      sandbox_analysis                               = string
    }
  ))
  default = []
}

variable "on_net_addr" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "src_addr" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "user_groups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "users" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_endpointcontrol_profile" "this" {
  description               = var.description
  dynamic_sort_subtable     = var.dynamic_sort_subtable
  profile_name              = var.profile_name
  replacemsg_override_group = var.replacemsg_override_group

  dynamic "device_groups" {
    for_each = var.device_groups
    content {
      name = device_groups.value["name"]
    }
  }

  dynamic "forticlient_android_settings" {
    for_each = var.forticlient_android_settings
    content {
      disable_wf_when_protected       = forticlient_android_settings.value["disable_wf_when_protected"]
      forticlient_advanced_vpn        = forticlient_android_settings.value["forticlient_advanced_vpn"]
      forticlient_advanced_vpn_buffer = forticlient_android_settings.value["forticlient_advanced_vpn_buffer"]
      forticlient_vpn_provisioning    = forticlient_android_settings.value["forticlient_vpn_provisioning"]
      forticlient_wf                  = forticlient_android_settings.value["forticlient_wf"]
      forticlient_wf_profile          = forticlient_android_settings.value["forticlient_wf_profile"]

      dynamic "forticlient_vpn_settings" {
        for_each = forticlient_android_settings.value.forticlient_vpn_settings
        content {
          auth_method                = forticlient_vpn_settings.value["auth_method"]
          name                       = forticlient_vpn_settings.value["name"]
          preshared_key              = forticlient_vpn_settings.value["preshared_key"]
          remote_gw                  = forticlient_vpn_settings.value["remote_gw"]
          sslvpn_access_port         = forticlient_vpn_settings.value["sslvpn_access_port"]
          sslvpn_require_certificate = forticlient_vpn_settings.value["sslvpn_require_certificate"]
          type                       = forticlient_vpn_settings.value["type"]
        }
      }

    }
  }

  dynamic "forticlient_ios_settings" {
    for_each = var.forticlient_ios_settings
    content {
      client_vpn_provisioning          = forticlient_ios_settings.value["client_vpn_provisioning"]
      configuration_content            = forticlient_ios_settings.value["configuration_content"]
      configuration_name               = forticlient_ios_settings.value["configuration_name"]
      disable_wf_when_protected        = forticlient_ios_settings.value["disable_wf_when_protected"]
      distribute_configuration_profile = forticlient_ios_settings.value["distribute_configuration_profile"]
      forticlient_wf                   = forticlient_ios_settings.value["forticlient_wf"]
      forticlient_wf_profile           = forticlient_ios_settings.value["forticlient_wf_profile"]

      dynamic "client_vpn_settings" {
        for_each = forticlient_ios_settings.value.client_vpn_settings
        content {
          auth_method                = client_vpn_settings.value["auth_method"]
          name                       = client_vpn_settings.value["name"]
          preshared_key              = client_vpn_settings.value["preshared_key"]
          remote_gw                  = client_vpn_settings.value["remote_gw"]
          sslvpn_access_port         = client_vpn_settings.value["sslvpn_access_port"]
          sslvpn_require_certificate = client_vpn_settings.value["sslvpn_require_certificate"]
          type                       = client_vpn_settings.value["type"]
          vpn_configuration_content  = client_vpn_settings.value["vpn_configuration_content"]
          vpn_configuration_name     = client_vpn_settings.value["vpn_configuration_name"]
        }
      }

    }
  }

  dynamic "forticlient_winmac_settings" {
    for_each = var.forticlient_winmac_settings
    content {
      av_realtime_protection                         = forticlient_winmac_settings.value["av_realtime_protection"]
      av_signature_up_to_date                        = forticlient_winmac_settings.value["av_signature_up_to_date"]
      forticlient_application_firewall               = forticlient_winmac_settings.value["forticlient_application_firewall"]
      forticlient_application_firewall_list          = forticlient_winmac_settings.value["forticlient_application_firewall_list"]
      forticlient_av                                 = forticlient_winmac_settings.value["forticlient_av"]
      forticlient_ems_compliance                     = forticlient_winmac_settings.value["forticlient_ems_compliance"]
      forticlient_ems_compliance_action              = forticlient_winmac_settings.value["forticlient_ems_compliance_action"]
      forticlient_linux_ver                          = forticlient_winmac_settings.value["forticlient_linux_ver"]
      forticlient_log_upload                         = forticlient_winmac_settings.value["forticlient_log_upload"]
      forticlient_log_upload_level                   = forticlient_winmac_settings.value["forticlient_log_upload_level"]
      forticlient_log_upload_server                  = forticlient_winmac_settings.value["forticlient_log_upload_server"]
      forticlient_mac_ver                            = forticlient_winmac_settings.value["forticlient_mac_ver"]
      forticlient_minimum_software_version           = forticlient_winmac_settings.value["forticlient_minimum_software_version"]
      forticlient_registration_compliance_action     = forticlient_winmac_settings.value["forticlient_registration_compliance_action"]
      forticlient_security_posture                   = forticlient_winmac_settings.value["forticlient_security_posture"]
      forticlient_security_posture_compliance_action = forticlient_winmac_settings.value["forticlient_security_posture_compliance_action"]
      forticlient_system_compliance                  = forticlient_winmac_settings.value["forticlient_system_compliance"]
      forticlient_system_compliance_action           = forticlient_winmac_settings.value["forticlient_system_compliance_action"]
      forticlient_vuln_scan                          = forticlient_winmac_settings.value["forticlient_vuln_scan"]
      forticlient_vuln_scan_compliance_action        = forticlient_winmac_settings.value["forticlient_vuln_scan_compliance_action"]
      forticlient_vuln_scan_enforce                  = forticlient_winmac_settings.value["forticlient_vuln_scan_enforce"]
      forticlient_vuln_scan_enforce_grace            = forticlient_winmac_settings.value["forticlient_vuln_scan_enforce_grace"]
      forticlient_vuln_scan_exempt                   = forticlient_winmac_settings.value["forticlient_vuln_scan_exempt"]
      forticlient_wf                                 = forticlient_winmac_settings.value["forticlient_wf"]
      forticlient_wf_profile                         = forticlient_winmac_settings.value["forticlient_wf_profile"]
      forticlient_win_ver                            = forticlient_winmac_settings.value["forticlient_win_ver"]
      os_av_software_installed                       = forticlient_winmac_settings.value["os_av_software_installed"]
      sandbox_address                                = forticlient_winmac_settings.value["sandbox_address"]
      sandbox_analysis                               = forticlient_winmac_settings.value["sandbox_analysis"]

      dynamic "forticlient_ems_entries" {
        for_each = forticlient_winmac_settings.value.forticlient_ems_entries
        content {
          name = forticlient_ems_entries.value["name"]
        }
      }

      dynamic "forticlient_operating_system" {
        for_each = forticlient_winmac_settings.value.forticlient_operating_system
        content {
          id      = forticlient_operating_system.value["id"]
          os_name = forticlient_operating_system.value["os_name"]
          os_type = forticlient_operating_system.value["os_type"]
        }
      }

      dynamic "forticlient_own_file" {
        for_each = forticlient_winmac_settings.value.forticlient_own_file
        content {
          file = forticlient_own_file.value["file"]
          id   = forticlient_own_file.value["id"]
        }
      }

      dynamic "forticlient_registry_entry" {
        for_each = forticlient_winmac_settings.value.forticlient_registry_entry
        content {
          id             = forticlient_registry_entry.value["id"]
          registry_entry = forticlient_registry_entry.value["registry_entry"]
        }
      }

      dynamic "forticlient_running_app" {
        for_each = forticlient_winmac_settings.value.forticlient_running_app
        content {
          app_name               = forticlient_running_app.value["app_name"]
          app_sha256_signature   = forticlient_running_app.value["app_sha256_signature"]
          app_sha256_signature2  = forticlient_running_app.value["app_sha256_signature2"]
          app_sha256_signature3  = forticlient_running_app.value["app_sha256_signature3"]
          app_sha256_signature4  = forticlient_running_app.value["app_sha256_signature4"]
          application_check_rule = forticlient_running_app.value["application_check_rule"]
          id                     = forticlient_running_app.value["id"]
          process_name           = forticlient_running_app.value["process_name"]
          process_name2          = forticlient_running_app.value["process_name2"]
          process_name3          = forticlient_running_app.value["process_name3"]
          process_name4          = forticlient_running_app.value["process_name4"]
        }
      }

    }
  }

  dynamic "on_net_addr" {
    for_each = var.on_net_addr
    content {
      name = on_net_addr.value["name"]
    }
  }

  dynamic "src_addr" {
    for_each = var.src_addr
    content {
      name = src_addr.value["name"]
    }
  }

  dynamic "user_groups" {
    for_each = var.user_groups
    content {
      name = user_groups.value["name"]
    }
  }

  dynamic "users" {
    for_each = var.users
    content {
      name = users.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_endpointcontrol_profile.this.id
}

output "profile_name" {
  description = "returns a string"
  value       = fortios_endpointcontrol_profile.this.profile_name
}

output "replacemsg_override_group" {
  description = "returns a string"
  value       = fortios_endpointcontrol_profile.this.replacemsg_override_group
}

output "this" {
  value = fortios_endpointcontrol_profile.this
}
```

[top](#index)