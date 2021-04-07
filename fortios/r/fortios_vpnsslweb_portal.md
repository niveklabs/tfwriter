# fortios_vpnsslweb_portal

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
module "fortios_vpnsslweb_portal" {
  source = "./modules/fortios/r/fortios_vpnsslweb_portal"

  # allow_user_access - (optional) is a type of string
  allow_user_access = null
  # auto_connect - (optional) is a type of string
  auto_connect = null
  # custom_lang - (optional) is a type of string
  custom_lang = null
  # customize_forticlient_download_url - (optional) is a type of string
  customize_forticlient_download_url = null
  # display_bookmark - (optional) is a type of string
  display_bookmark = null
  # display_connection_tools - (optional) is a type of string
  display_connection_tools = null
  # display_history - (optional) is a type of string
  display_history = null
  # display_status - (optional) is a type of string
  display_status = null
  # dns_server1 - (optional) is a type of string
  dns_server1 = null
  # dns_server2 - (optional) is a type of string
  dns_server2 = null
  # dns_suffix - (optional) is a type of string
  dns_suffix = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # exclusive_routing - (optional) is a type of string
  exclusive_routing = null
  # forticlient_download - (optional) is a type of string
  forticlient_download = null
  # forticlient_download_method - (optional) is a type of string
  forticlient_download_method = null
  # heading - (optional) is a type of string
  heading = null
  # hide_sso_credential - (optional) is a type of string
  hide_sso_credential = null
  # host_check - (optional) is a type of string
  host_check = null
  # host_check_interval - (optional) is a type of number
  host_check_interval = null
  # ip_mode - (optional) is a type of string
  ip_mode = null
  # ipv6_dns_server1 - (optional) is a type of string
  ipv6_dns_server1 = null
  # ipv6_dns_server2 - (optional) is a type of string
  ipv6_dns_server2 = null
  # ipv6_exclusive_routing - (optional) is a type of string
  ipv6_exclusive_routing = null
  # ipv6_service_restriction - (optional) is a type of string
  ipv6_service_restriction = null
  # ipv6_split_tunneling - (optional) is a type of string
  ipv6_split_tunneling = null
  # ipv6_split_tunneling_routing_negate - (optional) is a type of string
  ipv6_split_tunneling_routing_negate = null
  # ipv6_tunnel_mode - (optional) is a type of string
  ipv6_tunnel_mode = null
  # ipv6_wins_server1 - (optional) is a type of string
  ipv6_wins_server1 = null
  # ipv6_wins_server2 - (optional) is a type of string
  ipv6_wins_server2 = null
  # keep_alive - (optional) is a type of string
  keep_alive = null
  # limit_user_logins - (optional) is a type of string
  limit_user_logins = null
  # mac_addr_action - (optional) is a type of string
  mac_addr_action = null
  # mac_addr_check - (optional) is a type of string
  mac_addr_check = null
  # macos_forticlient_download_url - (optional) is a type of string
  macos_forticlient_download_url = null
  # name - (optional) is a type of string
  name = null
  # os_check - (optional) is a type of string
  os_check = null
  # redir_url - (optional) is a type of string
  redir_url = null
  # save_password - (optional) is a type of string
  save_password = null
  # service_restriction - (optional) is a type of string
  service_restriction = null
  # skip_check_for_browser - (optional) is a type of string
  skip_check_for_browser = null
  # skip_check_for_unsupported_os - (optional) is a type of string
  skip_check_for_unsupported_os = null
  # smb_max_version - (optional) is a type of string
  smb_max_version = null
  # smb_min_version - (optional) is a type of string
  smb_min_version = null
  # smb_ntlmv1_auth - (optional) is a type of string
  smb_ntlmv1_auth = null
  # smbv1 - (optional) is a type of string
  smbv1 = null
  # split_tunneling - (optional) is a type of string
  split_tunneling = null
  # split_tunneling_routing_negate - (optional) is a type of string
  split_tunneling_routing_negate = null
  # theme - (optional) is a type of string
  theme = null
  # transform_backward_slashes - (optional) is a type of string
  transform_backward_slashes = null
  # tunnel_mode - (optional) is a type of string
  tunnel_mode = null
  # use_sdwan - (optional) is a type of string
  use_sdwan = null
  # user_bookmark - (optional) is a type of string
  user_bookmark = null
  # user_group_bookmark - (optional) is a type of string
  user_group_bookmark = null
  # web_mode - (optional) is a type of string
  web_mode = null
  # windows_forticlient_download_url - (optional) is a type of string
  windows_forticlient_download_url = null
  # wins_server1 - (optional) is a type of string
  wins_server1 = null
  # wins_server2 - (optional) is a type of string
  wins_server2 = null

  bookmark_group = [{
    bookmarks = [{
      additional_params = null
      apptype           = null
      description       = null
      domain            = null
      folder            = null
      form_data = [{
        name  = null
        value = null
      }]
      host                     = null
      listening_port           = null
      load_balancing_info      = null
      logon_password           = null
      logon_user               = null
      name                     = null
      port                     = null
      preconnection_blob       = null
      preconnection_id         = null
      remote_port              = null
      security                 = null
      server_layout            = null
      show_status_window       = null
      sso                      = null
      sso_credential           = null
      sso_credential_sent_once = null
      sso_password             = null
      sso_username             = null
      url                      = null
    }]
    name = null
  }]

  host_check_policy = [{
    name = null
  }]

  ip_pools = [{
    name = null
  }]

  ipv6_pools = [{
    name = null
  }]

  ipv6_split_tunneling_routing_address = [{
    name = null
  }]

  mac_addr_check_rule = [{
    mac_addr_list = [{
      addr = null
    }]
    mac_addr_mask = null
    name          = null
  }]

  os_check_list = [{
    action             = null
    latest_patch_level = null
    name               = null
    tolerance          = null
  }]

  split_dns = [{
    dns_server1      = null
    dns_server2      = null
    domains          = null
    id               = null
    ipv6_dns_server1 = null
    ipv6_dns_server2 = null
  }]

  split_tunneling_routing_address = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_user_access" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_connect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "customize_forticlient_download_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_bookmark" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_connection_tools" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_history" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_suffix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exclusive_routing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forticlient_download" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forticlient_download_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "heading" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hide_sso_credential" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_check_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_dns_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_dns_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_exclusive_routing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_service_restriction" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_split_tunneling" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_split_tunneling_routing_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_tunnel_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_wins_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6_wins_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keep_alive" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "limit_user_logins" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac_addr_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac_addr_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "macos_forticlient_download_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redir_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "save_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_restriction" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "skip_check_for_browser" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "skip_check_for_unsupported_os" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "smb_max_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "smb_min_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "smb_ntlmv1_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "smbv1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "split_tunneling" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "split_tunneling_routing_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "theme" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "transform_backward_slashes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_sdwan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_bookmark" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_group_bookmark" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "windows_forticlient_download_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wins_server1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wins_server2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bookmark_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bookmarks = list(object(
        {
          additional_params = string
          apptype           = string
          description       = string
          domain            = string
          folder            = string
          form_data = list(object(
            {
              name  = string
              value = string
            }
          ))
          host                     = string
          listening_port           = number
          load_balancing_info      = string
          logon_password           = string
          logon_user               = string
          name                     = string
          port                     = number
          preconnection_blob       = string
          preconnection_id         = number
          remote_port              = number
          security                 = string
          server_layout            = string
          show_status_window       = string
          sso                      = string
          sso_credential           = string
          sso_credential_sent_once = string
          sso_password             = string
          sso_username             = string
          url                      = string
        }
      ))
      name = string
    }
  ))
  default = []
}

variable "host_check_policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "ip_pools" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "ipv6_pools" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "ipv6_split_tunneling_routing_address" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "mac_addr_check_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      mac_addr_list = list(object(
        {
          addr = string
        }
      ))
      mac_addr_mask = number
      name          = string
    }
  ))
  default = []
}

variable "os_check_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action             = string
      latest_patch_level = string
      name               = string
      tolerance          = number
    }
  ))
  default = []
}

variable "split_dns" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      dns_server1      = string
      dns_server2      = string
      domains          = string
      id               = number
      ipv6_dns_server1 = string
      ipv6_dns_server2 = string
    }
  ))
  default = []
}

variable "split_tunneling_routing_address" {
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
resource "fortios_vpnsslweb_portal" "this" {
  # allow_user_access - (optional) is a type of string
  allow_user_access = var.allow_user_access
  # auto_connect - (optional) is a type of string
  auto_connect = var.auto_connect
  # custom_lang - (optional) is a type of string
  custom_lang = var.custom_lang
  # customize_forticlient_download_url - (optional) is a type of string
  customize_forticlient_download_url = var.customize_forticlient_download_url
  # display_bookmark - (optional) is a type of string
  display_bookmark = var.display_bookmark
  # display_connection_tools - (optional) is a type of string
  display_connection_tools = var.display_connection_tools
  # display_history - (optional) is a type of string
  display_history = var.display_history
  # display_status - (optional) is a type of string
  display_status = var.display_status
  # dns_server1 - (optional) is a type of string
  dns_server1 = var.dns_server1
  # dns_server2 - (optional) is a type of string
  dns_server2 = var.dns_server2
  # dns_suffix - (optional) is a type of string
  dns_suffix = var.dns_suffix
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # exclusive_routing - (optional) is a type of string
  exclusive_routing = var.exclusive_routing
  # forticlient_download - (optional) is a type of string
  forticlient_download = var.forticlient_download
  # forticlient_download_method - (optional) is a type of string
  forticlient_download_method = var.forticlient_download_method
  # heading - (optional) is a type of string
  heading = var.heading
  # hide_sso_credential - (optional) is a type of string
  hide_sso_credential = var.hide_sso_credential
  # host_check - (optional) is a type of string
  host_check = var.host_check
  # host_check_interval - (optional) is a type of number
  host_check_interval = var.host_check_interval
  # ip_mode - (optional) is a type of string
  ip_mode = var.ip_mode
  # ipv6_dns_server1 - (optional) is a type of string
  ipv6_dns_server1 = var.ipv6_dns_server1
  # ipv6_dns_server2 - (optional) is a type of string
  ipv6_dns_server2 = var.ipv6_dns_server2
  # ipv6_exclusive_routing - (optional) is a type of string
  ipv6_exclusive_routing = var.ipv6_exclusive_routing
  # ipv6_service_restriction - (optional) is a type of string
  ipv6_service_restriction = var.ipv6_service_restriction
  # ipv6_split_tunneling - (optional) is a type of string
  ipv6_split_tunneling = var.ipv6_split_tunneling
  # ipv6_split_tunneling_routing_negate - (optional) is a type of string
  ipv6_split_tunneling_routing_negate = var.ipv6_split_tunneling_routing_negate
  # ipv6_tunnel_mode - (optional) is a type of string
  ipv6_tunnel_mode = var.ipv6_tunnel_mode
  # ipv6_wins_server1 - (optional) is a type of string
  ipv6_wins_server1 = var.ipv6_wins_server1
  # ipv6_wins_server2 - (optional) is a type of string
  ipv6_wins_server2 = var.ipv6_wins_server2
  # keep_alive - (optional) is a type of string
  keep_alive = var.keep_alive
  # limit_user_logins - (optional) is a type of string
  limit_user_logins = var.limit_user_logins
  # mac_addr_action - (optional) is a type of string
  mac_addr_action = var.mac_addr_action
  # mac_addr_check - (optional) is a type of string
  mac_addr_check = var.mac_addr_check
  # macos_forticlient_download_url - (optional) is a type of string
  macos_forticlient_download_url = var.macos_forticlient_download_url
  # name - (optional) is a type of string
  name = var.name
  # os_check - (optional) is a type of string
  os_check = var.os_check
  # redir_url - (optional) is a type of string
  redir_url = var.redir_url
  # save_password - (optional) is a type of string
  save_password = var.save_password
  # service_restriction - (optional) is a type of string
  service_restriction = var.service_restriction
  # skip_check_for_browser - (optional) is a type of string
  skip_check_for_browser = var.skip_check_for_browser
  # skip_check_for_unsupported_os - (optional) is a type of string
  skip_check_for_unsupported_os = var.skip_check_for_unsupported_os
  # smb_max_version - (optional) is a type of string
  smb_max_version = var.smb_max_version
  # smb_min_version - (optional) is a type of string
  smb_min_version = var.smb_min_version
  # smb_ntlmv1_auth - (optional) is a type of string
  smb_ntlmv1_auth = var.smb_ntlmv1_auth
  # smbv1 - (optional) is a type of string
  smbv1 = var.smbv1
  # split_tunneling - (optional) is a type of string
  split_tunneling = var.split_tunneling
  # split_tunneling_routing_negate - (optional) is a type of string
  split_tunneling_routing_negate = var.split_tunneling_routing_negate
  # theme - (optional) is a type of string
  theme = var.theme
  # transform_backward_slashes - (optional) is a type of string
  transform_backward_slashes = var.transform_backward_slashes
  # tunnel_mode - (optional) is a type of string
  tunnel_mode = var.tunnel_mode
  # use_sdwan - (optional) is a type of string
  use_sdwan = var.use_sdwan
  # user_bookmark - (optional) is a type of string
  user_bookmark = var.user_bookmark
  # user_group_bookmark - (optional) is a type of string
  user_group_bookmark = var.user_group_bookmark
  # web_mode - (optional) is a type of string
  web_mode = var.web_mode
  # windows_forticlient_download_url - (optional) is a type of string
  windows_forticlient_download_url = var.windows_forticlient_download_url
  # wins_server1 - (optional) is a type of string
  wins_server1 = var.wins_server1
  # wins_server2 - (optional) is a type of string
  wins_server2 = var.wins_server2

  dynamic "bookmark_group" {
    for_each = var.bookmark_group
    content {
      # name - (optional) is a type of string
      name = bookmark_group.value["name"]

      dynamic "bookmarks" {
        for_each = bookmark_group.value.bookmarks
        content {
          # additional_params - (optional) is a type of string
          additional_params = bookmarks.value["additional_params"]
          # apptype - (optional) is a type of string
          apptype = bookmarks.value["apptype"]
          # description - (optional) is a type of string
          description = bookmarks.value["description"]
          # domain - (optional) is a type of string
          domain = bookmarks.value["domain"]
          # folder - (optional) is a type of string
          folder = bookmarks.value["folder"]
          # host - (optional) is a type of string
          host = bookmarks.value["host"]
          # listening_port - (optional) is a type of number
          listening_port = bookmarks.value["listening_port"]
          # load_balancing_info - (optional) is a type of string
          load_balancing_info = bookmarks.value["load_balancing_info"]
          # logon_password - (optional) is a type of string
          logon_password = bookmarks.value["logon_password"]
          # logon_user - (optional) is a type of string
          logon_user = bookmarks.value["logon_user"]
          # name - (optional) is a type of string
          name = bookmarks.value["name"]
          # port - (optional) is a type of number
          port = bookmarks.value["port"]
          # preconnection_blob - (optional) is a type of string
          preconnection_blob = bookmarks.value["preconnection_blob"]
          # preconnection_id - (optional) is a type of number
          preconnection_id = bookmarks.value["preconnection_id"]
          # remote_port - (optional) is a type of number
          remote_port = bookmarks.value["remote_port"]
          # security - (optional) is a type of string
          security = bookmarks.value["security"]
          # server_layout - (optional) is a type of string
          server_layout = bookmarks.value["server_layout"]
          # show_status_window - (optional) is a type of string
          show_status_window = bookmarks.value["show_status_window"]
          # sso - (optional) is a type of string
          sso = bookmarks.value["sso"]
          # sso_credential - (optional) is a type of string
          sso_credential = bookmarks.value["sso_credential"]
          # sso_credential_sent_once - (optional) is a type of string
          sso_credential_sent_once = bookmarks.value["sso_credential_sent_once"]
          # sso_password - (optional) is a type of string
          sso_password = bookmarks.value["sso_password"]
          # sso_username - (optional) is a type of string
          sso_username = bookmarks.value["sso_username"]
          # url - (optional) is a type of string
          url = bookmarks.value["url"]

          dynamic "form_data" {
            for_each = bookmarks.value.form_data
            content {
              # name - (optional) is a type of string
              name = form_data.value["name"]
              # value - (optional) is a type of string
              value = form_data.value["value"]
            }
          }

        }
      }

    }
  }

  dynamic "host_check_policy" {
    for_each = var.host_check_policy
    content {
      # name - (optional) is a type of string
      name = host_check_policy.value["name"]
    }
  }

  dynamic "ip_pools" {
    for_each = var.ip_pools
    content {
      # name - (optional) is a type of string
      name = ip_pools.value["name"]
    }
  }

  dynamic "ipv6_pools" {
    for_each = var.ipv6_pools
    content {
      # name - (optional) is a type of string
      name = ipv6_pools.value["name"]
    }
  }

  dynamic "ipv6_split_tunneling_routing_address" {
    for_each = var.ipv6_split_tunneling_routing_address
    content {
      # name - (optional) is a type of string
      name = ipv6_split_tunneling_routing_address.value["name"]
    }
  }

  dynamic "mac_addr_check_rule" {
    for_each = var.mac_addr_check_rule
    content {
      # mac_addr_mask - (optional) is a type of number
      mac_addr_mask = mac_addr_check_rule.value["mac_addr_mask"]
      # name - (optional) is a type of string
      name = mac_addr_check_rule.value["name"]

      dynamic "mac_addr_list" {
        for_each = mac_addr_check_rule.value.mac_addr_list
        content {
          # addr - (optional) is a type of string
          addr = mac_addr_list.value["addr"]
        }
      }

    }
  }

  dynamic "os_check_list" {
    for_each = var.os_check_list
    content {
      # action - (optional) is a type of string
      action = os_check_list.value["action"]
      # latest_patch_level - (optional) is a type of string
      latest_patch_level = os_check_list.value["latest_patch_level"]
      # name - (optional) is a type of string
      name = os_check_list.value["name"]
      # tolerance - (optional) is a type of number
      tolerance = os_check_list.value["tolerance"]
    }
  }

  dynamic "split_dns" {
    for_each = var.split_dns
    content {
      # dns_server1 - (optional) is a type of string
      dns_server1 = split_dns.value["dns_server1"]
      # dns_server2 - (optional) is a type of string
      dns_server2 = split_dns.value["dns_server2"]
      # domains - (optional) is a type of string
      domains = split_dns.value["domains"]
      # id - (optional) is a type of number
      id = split_dns.value["id"]
      # ipv6_dns_server1 - (optional) is a type of string
      ipv6_dns_server1 = split_dns.value["ipv6_dns_server1"]
      # ipv6_dns_server2 - (optional) is a type of string
      ipv6_dns_server2 = split_dns.value["ipv6_dns_server2"]
    }
  }

  dynamic "split_tunneling_routing_address" {
    for_each = var.split_tunneling_routing_address
    content {
      # name - (optional) is a type of string
      name = split_tunneling_routing_address.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_user_access" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.allow_user_access
}

output "auto_connect" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.auto_connect
}

output "custom_lang" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.custom_lang
}

output "customize_forticlient_download_url" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.customize_forticlient_download_url
}

output "display_bookmark" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.display_bookmark
}

output "display_connection_tools" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.display_connection_tools
}

output "display_history" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.display_history
}

output "display_status" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.display_status
}

output "dns_server1" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.dns_server1
}

output "dns_server2" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.dns_server2
}

output "exclusive_routing" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.exclusive_routing
}

output "forticlient_download" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.forticlient_download
}

output "forticlient_download_method" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.forticlient_download_method
}

output "heading" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.heading
}

output "hide_sso_credential" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.hide_sso_credential
}

output "host_check" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.host_check
}

output "host_check_interval" {
  description = "returns a number"
  value       = fortios_vpnsslweb_portal.this.host_check_interval
}

output "id" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.id
}

output "ip_mode" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.ip_mode
}

output "ipv6_dns_server1" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.ipv6_dns_server1
}

output "ipv6_dns_server2" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.ipv6_dns_server2
}

output "ipv6_exclusive_routing" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.ipv6_exclusive_routing
}

output "ipv6_service_restriction" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.ipv6_service_restriction
}

output "ipv6_split_tunneling" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.ipv6_split_tunneling
}

output "ipv6_split_tunneling_routing_negate" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.ipv6_split_tunneling_routing_negate
}

output "ipv6_tunnel_mode" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.ipv6_tunnel_mode
}

output "ipv6_wins_server1" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.ipv6_wins_server1
}

output "ipv6_wins_server2" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.ipv6_wins_server2
}

output "keep_alive" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.keep_alive
}

output "limit_user_logins" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.limit_user_logins
}

output "mac_addr_action" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.mac_addr_action
}

output "mac_addr_check" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.mac_addr_check
}

output "name" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.name
}

output "os_check" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.os_check
}

output "save_password" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.save_password
}

output "service_restriction" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.service_restriction
}

output "skip_check_for_browser" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.skip_check_for_browser
}

output "skip_check_for_unsupported_os" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.skip_check_for_unsupported_os
}

output "smb_max_version" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.smb_max_version
}

output "smb_min_version" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.smb_min_version
}

output "smb_ntlmv1_auth" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.smb_ntlmv1_auth
}

output "smbv1" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.smbv1
}

output "split_tunneling" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.split_tunneling
}

output "split_tunneling_routing_negate" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.split_tunneling_routing_negate
}

output "theme" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.theme
}

output "transform_backward_slashes" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.transform_backward_slashes
}

output "tunnel_mode" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.tunnel_mode
}

output "use_sdwan" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.use_sdwan
}

output "user_bookmark" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.user_bookmark
}

output "user_group_bookmark" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.user_group_bookmark
}

output "web_mode" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.web_mode
}

output "wins_server1" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.wins_server1
}

output "wins_server2" {
  description = "returns a string"
  value       = fortios_vpnsslweb_portal.this.wins_server2
}

output "this" {
  value = fortios_vpnsslweb_portal.this
}
```

[top](#index)