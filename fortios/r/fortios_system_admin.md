# fortios_system_admin

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_admin" {
  source = "./modules/fortios/r/fortios_system_admin"

  # accprofile - (optional) is a type of string
  accprofile = null
  # accprofile_override - (optional) is a type of string
  accprofile_override = null
  # allow_remove_admin_session - (optional) is a type of string
  allow_remove_admin_session = null
  # comments - (optional) is a type of string
  comments = null
  # email_to - (optional) is a type of string
  email_to = null
  # force_password_change - (optional) is a type of string
  force_password_change = null
  # fortitoken - (optional) is a type of string
  fortitoken = null
  # guest_auth - (optional) is a type of string
  guest_auth = null
  # guest_lang - (optional) is a type of string
  guest_lang = null
  # hidden - (optional) is a type of number
  hidden = null
  # history0 - (optional) is a type of string
  history0 = null
  # history1 - (optional) is a type of string
  history1 = null
  # ip6_trusthost1 - (optional) is a type of string
  ip6_trusthost1 = null
  # ip6_trusthost10 - (optional) is a type of string
  ip6_trusthost10 = null
  # ip6_trusthost2 - (optional) is a type of string
  ip6_trusthost2 = null
  # ip6_trusthost3 - (optional) is a type of string
  ip6_trusthost3 = null
  # ip6_trusthost4 - (optional) is a type of string
  ip6_trusthost4 = null
  # ip6_trusthost5 - (optional) is a type of string
  ip6_trusthost5 = null
  # ip6_trusthost6 - (optional) is a type of string
  ip6_trusthost6 = null
  # ip6_trusthost7 - (optional) is a type of string
  ip6_trusthost7 = null
  # ip6_trusthost8 - (optional) is a type of string
  ip6_trusthost8 = null
  # ip6_trusthost9 - (optional) is a type of string
  ip6_trusthost9 = null
  # name - (optional) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # password_expire - (optional) is a type of string
  password_expire = null
  # peer_auth - (optional) is a type of string
  peer_auth = null
  # peer_group - (optional) is a type of string
  peer_group = null
  # radius_vdom_override - (optional) is a type of string
  radius_vdom_override = null
  # remote_auth - (optional) is a type of string
  remote_auth = null
  # remote_group - (optional) is a type of string
  remote_group = null
  # schedule - (optional) is a type of string
  schedule = null
  # sms_custom_server - (optional) is a type of string
  sms_custom_server = null
  # sms_phone - (optional) is a type of string
  sms_phone = null
  # sms_server - (optional) is a type of string
  sms_server = null
  # ssh_certificate - (optional) is a type of string
  ssh_certificate = null
  # ssh_public_key1 - (optional) is a type of string
  ssh_public_key1 = null
  # ssh_public_key2 - (optional) is a type of string
  ssh_public_key2 = null
  # ssh_public_key3 - (optional) is a type of string
  ssh_public_key3 = null
  # trusthost1 - (optional) is a type of string
  trusthost1 = null
  # trusthost10 - (optional) is a type of string
  trusthost10 = null
  # trusthost2 - (optional) is a type of string
  trusthost2 = null
  # trusthost3 - (optional) is a type of string
  trusthost3 = null
  # trusthost4 - (optional) is a type of string
  trusthost4 = null
  # trusthost5 - (optional) is a type of string
  trusthost5 = null
  # trusthost6 - (optional) is a type of string
  trusthost6 = null
  # trusthost7 - (optional) is a type of string
  trusthost7 = null
  # trusthost8 - (optional) is a type of string
  trusthost8 = null
  # trusthost9 - (optional) is a type of string
  trusthost9 = null
  # two_factor - (optional) is a type of string
  two_factor = null
  # wildcard - (optional) is a type of string
  wildcard = null

  guest_usergroups = [{
    name = null
  }]

  gui_dashboard = [{
    columns     = null
    id          = null
    layout_type = null
    name        = null
    scope       = null
    widget = [{
      fabric_device = null
      filters = [{
        id    = null
        key   = null
        value = null
      }]
      height        = null
      id            = null
      industry      = null
      interface     = null
      region        = null
      report_by     = null
      sort_by       = null
      timeframe     = null
      title         = null
      type          = null
      visualization = null
      width         = null
      x_pos         = null
      y_pos         = null
    }]
  }]

  gui_global_menu_favorites = [{
    id = null
  }]

  gui_new_feature_acknowledge = [{
    id = null
  }]

  gui_vdom_menu_favorites = [{
    id = null
  }]

  login_time = [{
    last_failed_login = null
    last_login        = null
    usr_name          = null
  }]

  vdom = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accprofile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "accprofile_override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_remove_admin_session" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_password_change" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortitoken" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "guest_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "guest_lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hidden" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "history0" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "history1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6_trusthost1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6_trusthost10" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6_trusthost2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6_trusthost3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6_trusthost4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6_trusthost5" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6_trusthost6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6_trusthost7" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6_trusthost8" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6_trusthost9" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password_expire" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "radius_vdom_override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remote_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sms_custom_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sms_phone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sms_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_public_key1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_public_key2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_public_key3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost10" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost5" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost7" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost8" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost9" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "two_factor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wildcard" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "guest_usergroups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "gui_dashboard" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      columns     = number
      id          = number
      layout_type = string
      name        = string
      scope       = string
      widget = list(object(
        {
          fabric_device = string
          filters = list(object(
            {
              id    = number
              key   = string
              value = string
            }
          ))
          height        = number
          id            = number
          industry      = string
          interface     = string
          region        = string
          report_by     = string
          sort_by       = string
          timeframe     = string
          title         = string
          type          = string
          visualization = string
          width         = number
          x_pos         = number
          y_pos         = number
        }
      ))
    }
  ))
  default = []
}

variable "gui_global_menu_favorites" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = string
    }
  ))
  default = []
}

variable "gui_new_feature_acknowledge" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = string
    }
  ))
  default = []
}

variable "gui_vdom_menu_favorites" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = string
    }
  ))
  default = []
}

variable "login_time" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      last_failed_login = string
      last_login        = string
      usr_name          = string
    }
  ))
  default = []
}

variable "vdom" {
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
resource "fortios_system_admin" "this" {
  accprofile                 = var.accprofile
  accprofile_override        = var.accprofile_override
  allow_remove_admin_session = var.allow_remove_admin_session
  comments                   = var.comments
  email_to                   = var.email_to
  force_password_change      = var.force_password_change
  fortitoken                 = var.fortitoken
  guest_auth                 = var.guest_auth
  guest_lang                 = var.guest_lang
  hidden                     = var.hidden
  history0                   = var.history0
  history1                   = var.history1
  ip6_trusthost1             = var.ip6_trusthost1
  ip6_trusthost10            = var.ip6_trusthost10
  ip6_trusthost2             = var.ip6_trusthost2
  ip6_trusthost3             = var.ip6_trusthost3
  ip6_trusthost4             = var.ip6_trusthost4
  ip6_trusthost5             = var.ip6_trusthost5
  ip6_trusthost6             = var.ip6_trusthost6
  ip6_trusthost7             = var.ip6_trusthost7
  ip6_trusthost8             = var.ip6_trusthost8
  ip6_trusthost9             = var.ip6_trusthost9
  name                       = var.name
  password                   = var.password
  password_expire            = var.password_expire
  peer_auth                  = var.peer_auth
  peer_group                 = var.peer_group
  radius_vdom_override       = var.radius_vdom_override
  remote_auth                = var.remote_auth
  remote_group               = var.remote_group
  schedule                   = var.schedule
  sms_custom_server          = var.sms_custom_server
  sms_phone                  = var.sms_phone
  sms_server                 = var.sms_server
  ssh_certificate            = var.ssh_certificate
  ssh_public_key1            = var.ssh_public_key1
  ssh_public_key2            = var.ssh_public_key2
  ssh_public_key3            = var.ssh_public_key3
  trusthost1                 = var.trusthost1
  trusthost10                = var.trusthost10
  trusthost2                 = var.trusthost2
  trusthost3                 = var.trusthost3
  trusthost4                 = var.trusthost4
  trusthost5                 = var.trusthost5
  trusthost6                 = var.trusthost6
  trusthost7                 = var.trusthost7
  trusthost8                 = var.trusthost8
  trusthost9                 = var.trusthost9
  two_factor                 = var.two_factor
  wildcard                   = var.wildcard

  dynamic "guest_usergroups" {
    for_each = var.guest_usergroups
    content {
      name = guest_usergroups.value["name"]
    }
  }

  dynamic "gui_dashboard" {
    for_each = var.gui_dashboard
    content {
      columns     = gui_dashboard.value["columns"]
      id          = gui_dashboard.value["id"]
      layout_type = gui_dashboard.value["layout_type"]
      name        = gui_dashboard.value["name"]
      scope       = gui_dashboard.value["scope"]

      dynamic "widget" {
        for_each = gui_dashboard.value.widget
        content {
          fabric_device = widget.value["fabric_device"]
          height        = widget.value["height"]
          id            = widget.value["id"]
          industry      = widget.value["industry"]
          interface     = widget.value["interface"]
          region        = widget.value["region"]
          report_by     = widget.value["report_by"]
          sort_by       = widget.value["sort_by"]
          timeframe     = widget.value["timeframe"]
          title         = widget.value["title"]
          type          = widget.value["type"]
          visualization = widget.value["visualization"]
          width         = widget.value["width"]
          x_pos         = widget.value["x_pos"]
          y_pos         = widget.value["y_pos"]

          dynamic "filters" {
            for_each = widget.value.filters
            content {
              id    = filters.value["id"]
              key   = filters.value["key"]
              value = filters.value["value"]
            }
          }

        }
      }

    }
  }

  dynamic "gui_global_menu_favorites" {
    for_each = var.gui_global_menu_favorites
    content {
      id = gui_global_menu_favorites.value["id"]
    }
  }

  dynamic "gui_new_feature_acknowledge" {
    for_each = var.gui_new_feature_acknowledge
    content {
      id = gui_new_feature_acknowledge.value["id"]
    }
  }

  dynamic "gui_vdom_menu_favorites" {
    for_each = var.gui_vdom_menu_favorites
    content {
      id = gui_vdom_menu_favorites.value["id"]
    }
  }

  dynamic "login_time" {
    for_each = var.login_time
    content {
      last_failed_login = login_time.value["last_failed_login"]
      last_login        = login_time.value["last_login"]
      usr_name          = login_time.value["usr_name"]
    }
  }

  dynamic "vdom" {
    for_each = var.vdom
    content {
      name = vdom.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "accprofile" {
  description = "returns a string"
  value       = fortios_system_admin.this.accprofile
}

output "accprofile_override" {
  description = "returns a string"
  value       = fortios_system_admin.this.accprofile_override
}

output "allow_remove_admin_session" {
  description = "returns a string"
  value       = fortios_system_admin.this.allow_remove_admin_session
}

output "email_to" {
  description = "returns a string"
  value       = fortios_system_admin.this.email_to
}

output "force_password_change" {
  description = "returns a string"
  value       = fortios_system_admin.this.force_password_change
}

output "fortitoken" {
  description = "returns a string"
  value       = fortios_system_admin.this.fortitoken
}

output "guest_auth" {
  description = "returns a string"
  value       = fortios_system_admin.this.guest_auth
}

output "guest_lang" {
  description = "returns a string"
  value       = fortios_system_admin.this.guest_lang
}

output "hidden" {
  description = "returns a number"
  value       = fortios_system_admin.this.hidden
}

output "id" {
  description = "returns a string"
  value       = fortios_system_admin.this.id
}

output "ip6_trusthost1" {
  description = "returns a string"
  value       = fortios_system_admin.this.ip6_trusthost1
}

output "ip6_trusthost10" {
  description = "returns a string"
  value       = fortios_system_admin.this.ip6_trusthost10
}

output "ip6_trusthost2" {
  description = "returns a string"
  value       = fortios_system_admin.this.ip6_trusthost2
}

output "ip6_trusthost3" {
  description = "returns a string"
  value       = fortios_system_admin.this.ip6_trusthost3
}

output "ip6_trusthost4" {
  description = "returns a string"
  value       = fortios_system_admin.this.ip6_trusthost4
}

output "ip6_trusthost5" {
  description = "returns a string"
  value       = fortios_system_admin.this.ip6_trusthost5
}

output "ip6_trusthost6" {
  description = "returns a string"
  value       = fortios_system_admin.this.ip6_trusthost6
}

output "ip6_trusthost7" {
  description = "returns a string"
  value       = fortios_system_admin.this.ip6_trusthost7
}

output "ip6_trusthost8" {
  description = "returns a string"
  value       = fortios_system_admin.this.ip6_trusthost8
}

output "ip6_trusthost9" {
  description = "returns a string"
  value       = fortios_system_admin.this.ip6_trusthost9
}

output "name" {
  description = "returns a string"
  value       = fortios_system_admin.this.name
}

output "password_expire" {
  description = "returns a string"
  value       = fortios_system_admin.this.password_expire
}

output "peer_auth" {
  description = "returns a string"
  value       = fortios_system_admin.this.peer_auth
}

output "peer_group" {
  description = "returns a string"
  value       = fortios_system_admin.this.peer_group
}

output "radius_vdom_override" {
  description = "returns a string"
  value       = fortios_system_admin.this.radius_vdom_override
}

output "remote_auth" {
  description = "returns a string"
  value       = fortios_system_admin.this.remote_auth
}

output "remote_group" {
  description = "returns a string"
  value       = fortios_system_admin.this.remote_group
}

output "schedule" {
  description = "returns a string"
  value       = fortios_system_admin.this.schedule
}

output "sms_custom_server" {
  description = "returns a string"
  value       = fortios_system_admin.this.sms_custom_server
}

output "sms_phone" {
  description = "returns a string"
  value       = fortios_system_admin.this.sms_phone
}

output "sms_server" {
  description = "returns a string"
  value       = fortios_system_admin.this.sms_server
}

output "ssh_certificate" {
  description = "returns a string"
  value       = fortios_system_admin.this.ssh_certificate
}

output "ssh_public_key1" {
  description = "returns a string"
  value       = fortios_system_admin.this.ssh_public_key1
  sensitive   = true
}

output "ssh_public_key2" {
  description = "returns a string"
  value       = fortios_system_admin.this.ssh_public_key2
  sensitive   = true
}

output "ssh_public_key3" {
  description = "returns a string"
  value       = fortios_system_admin.this.ssh_public_key3
  sensitive   = true
}

output "trusthost1" {
  description = "returns a string"
  value       = fortios_system_admin.this.trusthost1
}

output "trusthost10" {
  description = "returns a string"
  value       = fortios_system_admin.this.trusthost10
}

output "trusthost2" {
  description = "returns a string"
  value       = fortios_system_admin.this.trusthost2
}

output "trusthost3" {
  description = "returns a string"
  value       = fortios_system_admin.this.trusthost3
}

output "trusthost4" {
  description = "returns a string"
  value       = fortios_system_admin.this.trusthost4
}

output "trusthost5" {
  description = "returns a string"
  value       = fortios_system_admin.this.trusthost5
}

output "trusthost6" {
  description = "returns a string"
  value       = fortios_system_admin.this.trusthost6
}

output "trusthost7" {
  description = "returns a string"
  value       = fortios_system_admin.this.trusthost7
}

output "trusthost8" {
  description = "returns a string"
  value       = fortios_system_admin.this.trusthost8
}

output "trusthost9" {
  description = "returns a string"
  value       = fortios_system_admin.this.trusthost9
}

output "two_factor" {
  description = "returns a string"
  value       = fortios_system_admin.this.two_factor
}

output "wildcard" {
  description = "returns a string"
  value       = fortios_system_admin.this.wildcard
}

output "this" {
  value = fortios_system_admin.this
}
```

[top](#index)