# nsxt_policy_context_profile

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_context_profile" {
  source = "./modules/nsxt/r/nsxt_policy_context_profile"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # nsx_id - (optional) is a type of string
  nsx_id = null

  app_id = [{
    description = null
    is_alg_type = null
    sub_attribute = [{
      cifs_smb_version = []
      tls_cipher_suite = []
      tls_version      = []
    }]
    value = []
  }]

  domain_name = [{
    description = null
    value       = []
  }]

  tag = [{
    scope = null
    tag   = null
  }]

  url_category = [{
    description = null
    value       = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "app_id" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      is_alg_type = bool
      sub_attribute = set(object(
        {
          cifs_smb_version = set(string)
          tls_cipher_suite = set(string)
          tls_version      = set(string)
        }
      ))
      value = set(string)
    }
  ))
  default = []
}

variable "domain_name" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      value       = set(string)
    }
  ))
  default = []
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}

variable "url_category" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      value       = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_policy_context_profile" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # nsx_id - (optional) is a type of string
  nsx_id = var.nsx_id

  dynamic "app_id" {
    for_each = var.app_id
    content {
      # description - (optional) is a type of string
      description = app_id.value["description"]
      # value - (required) is a type of set of string
      value = app_id.value["value"]

      dynamic "sub_attribute" {
        for_each = app_id.value.sub_attribute
        content {
          # cifs_smb_version - (optional) is a type of set of string
          cifs_smb_version = sub_attribute.value["cifs_smb_version"]
          # tls_cipher_suite - (optional) is a type of set of string
          tls_cipher_suite = sub_attribute.value["tls_cipher_suite"]
          # tls_version - (optional) is a type of set of string
          tls_version = sub_attribute.value["tls_version"]
        }
      }

    }
  }

  dynamic "domain_name" {
    for_each = var.domain_name
    content {
      # description - (optional) is a type of string
      description = domain_name.value["description"]
      # value - (required) is a type of set of string
      value = domain_name.value["value"]
    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

  dynamic "url_category" {
    for_each = var.url_category
    content {
      # description - (optional) is a type of string
      description = url_category.value["description"]
      # value - (required) is a type of set of string
      value = url_category.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nsxt_policy_context_profile.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_context_profile.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_context_profile.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_context_profile.this.revision
}

output "this" {
  value = nsxt_policy_context_profile.this
}
```

[top](#index)