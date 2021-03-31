# avi_authprofile

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
module "avi_authprofile" {
  source = "./modules/avi/r/avi_authprofile"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # pa_agent_ref - (optional) is a type of string
  pa_agent_ref = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # type - (required) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null

  http = [{
    cache_expiration_time = null
    request_header        = null
    require_user_groups   = []
  }]

  ldap = [{
    base_dn               = null
    bind_as_administrator = null
    email_attribute       = null
    full_name_attribute   = null
    port                  = null
    security_mode         = null
    server                = []
    settings = [{
      admin_bind_dn           = null
      group_filter            = null
      group_member_attribute  = null
      group_member_is_full_dn = null
      group_search_dn         = null
      group_search_scope      = null
      ignore_referrals        = null
      password                = null
      user_attributes         = []
      user_id_attribute       = null
      user_search_dn          = null
      user_search_scope       = null
    }]
    user_bind = [{
      dn_template       = null
      token             = null
      user_attributes   = []
      user_id_attribute = null
    }]
  }]

  saml = [{
    idp = [{
      metadata = null
    }]
    sp = [{
      fqdn             = null
      org_display_name = null
      org_name         = null
      org_url          = null
      saml_entity_type = null
      sp_nodes = [{
        entity_id                           = null
        name                                = null
        signing_ssl_key_and_certificate_ref = null
        single_signon_url                   = null
      }]
      tech_contact_email = null
      tech_contact_name  = null
    }]
  }]

  tacacs_plus = [{
    authorization_attrs = [{
      mandatory = null
      name      = null
      value     = null
    }]
    password = null
    port     = null
    server   = []
    service  = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "pa_agent_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cache_expiration_time = number
      request_header        = string
      require_user_groups   = list(string)
    }
  ))
  default = []
}

variable "ldap" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      base_dn               = string
      bind_as_administrator = bool
      email_attribute       = string
      full_name_attribute   = string
      port                  = number
      security_mode         = string
      server                = list(string)
      settings = set(object(
        {
          admin_bind_dn           = string
          group_filter            = string
          group_member_attribute  = string
          group_member_is_full_dn = bool
          group_search_dn         = string
          group_search_scope      = string
          ignore_referrals        = bool
          password                = string
          user_attributes         = list(string)
          user_id_attribute       = string
          user_search_dn          = string
          user_search_scope       = string
        }
      ))
      user_bind = set(object(
        {
          dn_template       = string
          token             = string
          user_attributes   = list(string)
          user_id_attribute = string
        }
      ))
    }
  ))
  default = []
}

variable "saml" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      idp = set(object(
        {
          metadata = string
        }
      ))
      sp = set(object(
        {
          fqdn             = string
          org_display_name = string
          org_name         = string
          org_url          = string
          saml_entity_type = string
          sp_nodes = list(object(
            {
              entity_id                           = string
              name                                = string
              signing_ssl_key_and_certificate_ref = string
              single_signon_url                   = string
            }
          ))
          tech_contact_email = string
          tech_contact_name  = string
        }
      ))
    }
  ))
  default = []
}

variable "tacacs_plus" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      authorization_attrs = list(object(
        {
          mandatory = bool
          name      = string
          value     = string
        }
      ))
      password = string
      port     = number
      server   = list(string)
      service  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_authprofile" "this" {
  description  = var.description
  name         = var.name
  pa_agent_ref = var.pa_agent_ref
  tenant_ref   = var.tenant_ref
  type         = var.type
  uuid         = var.uuid

  dynamic "http" {
    for_each = var.http
    content {
      cache_expiration_time = http.value["cache_expiration_time"]
      request_header        = http.value["request_header"]
      require_user_groups   = http.value["require_user_groups"]
    }
  }

  dynamic "ldap" {
    for_each = var.ldap
    content {
      base_dn               = ldap.value["base_dn"]
      bind_as_administrator = ldap.value["bind_as_administrator"]
      email_attribute       = ldap.value["email_attribute"]
      full_name_attribute   = ldap.value["full_name_attribute"]
      port                  = ldap.value["port"]
      security_mode         = ldap.value["security_mode"]
      server                = ldap.value["server"]

      dynamic "settings" {
        for_each = ldap.value.settings
        content {
          admin_bind_dn           = settings.value["admin_bind_dn"]
          group_filter            = settings.value["group_filter"]
          group_member_attribute  = settings.value["group_member_attribute"]
          group_member_is_full_dn = settings.value["group_member_is_full_dn"]
          group_search_dn         = settings.value["group_search_dn"]
          group_search_scope      = settings.value["group_search_scope"]
          ignore_referrals        = settings.value["ignore_referrals"]
          password                = settings.value["password"]
          user_attributes         = settings.value["user_attributes"]
          user_id_attribute       = settings.value["user_id_attribute"]
          user_search_dn          = settings.value["user_search_dn"]
          user_search_scope       = settings.value["user_search_scope"]
        }
      }

      dynamic "user_bind" {
        for_each = ldap.value.user_bind
        content {
          dn_template       = user_bind.value["dn_template"]
          token             = user_bind.value["token"]
          user_attributes   = user_bind.value["user_attributes"]
          user_id_attribute = user_bind.value["user_id_attribute"]
        }
      }

    }
  }

  dynamic "saml" {
    for_each = var.saml
    content {

      dynamic "idp" {
        for_each = saml.value.idp
        content {
          metadata = idp.value["metadata"]
        }
      }

      dynamic "sp" {
        for_each = saml.value.sp
        content {
          fqdn               = sp.value["fqdn"]
          org_display_name   = sp.value["org_display_name"]
          org_name           = sp.value["org_name"]
          org_url            = sp.value["org_url"]
          saml_entity_type   = sp.value["saml_entity_type"]
          tech_contact_email = sp.value["tech_contact_email"]
          tech_contact_name  = sp.value["tech_contact_name"]

          dynamic "sp_nodes" {
            for_each = sp.value.sp_nodes
            content {
              entity_id                           = sp_nodes.value["entity_id"]
              name                                = sp_nodes.value["name"]
              signing_ssl_key_and_certificate_ref = sp_nodes.value["signing_ssl_key_and_certificate_ref"]
              single_signon_url                   = sp_nodes.value["single_signon_url"]
            }
          }

        }
      }

    }
  }

  dynamic "tacacs_plus" {
    for_each = var.tacacs_plus
    content {
      password = tacacs_plus.value["password"]
      port     = tacacs_plus.value["port"]
      server   = tacacs_plus.value["server"]
      service  = tacacs_plus.value["service"]

      dynamic "authorization_attrs" {
        for_each = tacacs_plus.value.authorization_attrs
        content {
          mandatory = authorization_attrs.value["mandatory"]
          name      = authorization_attrs.value["name"]
          value     = authorization_attrs.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_authprofile.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_authprofile.this.id
}

output "pa_agent_ref" {
  description = "returns a string"
  value       = avi_authprofile.this.pa_agent_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_authprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_authprofile.this.uuid
}

output "this" {
  value = avi_authprofile.this
}
```

[top](#index)