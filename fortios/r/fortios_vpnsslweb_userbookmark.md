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
    fortios = ">= 1.6.18"
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
  # name - (optional) is a type of string
  name = null

  bookmarks = [{
    additional_params = null
    apptype           = null
    description       = null
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
  custom_lang = var.custom_lang
  name        = var.name

  dynamic "bookmarks" {
    for_each = var.bookmarks
    content {
      additional_params        = bookmarks.value["additional_params"]
      apptype                  = bookmarks.value["apptype"]
      description              = bookmarks.value["description"]
      folder                   = bookmarks.value["folder"]
      host                     = bookmarks.value["host"]
      listening_port           = bookmarks.value["listening_port"]
      load_balancing_info      = bookmarks.value["load_balancing_info"]
      logon_password           = bookmarks.value["logon_password"]
      logon_user               = bookmarks.value["logon_user"]
      name                     = bookmarks.value["name"]
      port                     = bookmarks.value["port"]
      preconnection_blob       = bookmarks.value["preconnection_blob"]
      preconnection_id         = bookmarks.value["preconnection_id"]
      remote_port              = bookmarks.value["remote_port"]
      security                 = bookmarks.value["security"]
      server_layout            = bookmarks.value["server_layout"]
      show_status_window       = bookmarks.value["show_status_window"]
      sso                      = bookmarks.value["sso"]
      sso_credential           = bookmarks.value["sso_credential"]
      sso_credential_sent_once = bookmarks.value["sso_credential_sent_once"]
      sso_password             = bookmarks.value["sso_password"]
      sso_username             = bookmarks.value["sso_username"]
      url                      = bookmarks.value["url"]

      dynamic "form_data" {
        for_each = bookmarks.value.form_data
        content {
          name  = form_data.value["name"]
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