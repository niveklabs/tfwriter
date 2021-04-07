# fortios_vpnsslweb_userbookmark

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
module "fortios_vpnsslweb_userbookmark" {
  source = "./modules/fortios/r/fortios_vpnsslweb_userbookmark"

  # custom_lang - (optional) is a type of string
  custom_lang = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null

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
}
```

[top](#index)

### Variables

```terraform
variable "custom_lang" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bookmarks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
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
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpnsslweb_userbookmark" "this" {
  # custom_lang - (optional) is a type of string
  custom_lang = var.custom_lang
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name

  dynamic "bookmarks" {
    for_each = var.bookmarks
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
```

[top](#index)

### Outputs

```terraform
output "custom_lang" {
  description = "returns a string"
  value       = fortios_vpnsslweb_userbookmark.this.custom_lang
}

output "id" {
  description = "returns a string"
  value       = fortios_vpnsslweb_userbookmark.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_vpnsslweb_userbookmark.this.name
}

output "this" {
  value = fortios_vpnsslweb_userbookmark.this
}
```

[top](#index)