# cloudflare_access_policy

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_access_policy" {
  source = "./modules/cloudflare/r/cloudflare_access_policy"

  # account_id - (optional) is a type of string
  account_id = null
  # application_id - (required) is a type of string
  application_id = null
  # decision - (required) is a type of string
  decision = null
  # name - (required) is a type of string
  name = null
  # precedence - (required) is a type of number
  precedence = null
  # zone_id - (optional) is a type of string
  zone_id = null

  exclude = [{
    any_valid_service_token = null
    auth_method             = null
    azure = [{
      id                   = []
      identity_provider_id = null
    }]
    certificate  = null
    common_name  = null
    email        = []
    email_domain = []
    everyone     = null
    geo          = []
    github = [{
      identity_provider_id = null
      name                 = null
      teams                = []
    }]
    group = []
    gsuite = [{
      email                = []
      identity_provider_id = null
    }]
    ip = []
    okta = [{
      identity_provider_id = null
      name                 = []
    }]
    saml = [{
      attribute_name       = null
      attribute_value      = null
      identity_provider_id = null
    }]
    service_token = []
  }]

  include = [{
    any_valid_service_token = null
    auth_method             = null
    azure = [{
      id                   = []
      identity_provider_id = null
    }]
    certificate  = null
    common_name  = null
    email        = []
    email_domain = []
    everyone     = null
    geo          = []
    github = [{
      identity_provider_id = null
      name                 = null
      teams                = []
    }]
    group = []
    gsuite = [{
      email                = []
      identity_provider_id = null
    }]
    ip = []
    okta = [{
      identity_provider_id = null
      name                 = []
    }]
    saml = [{
      attribute_name       = null
      attribute_value      = null
      identity_provider_id = null
    }]
    service_token = []
  }]

  require = [{
    any_valid_service_token = null
    auth_method             = null
    azure = [{
      id                   = []
      identity_provider_id = null
    }]
    certificate  = null
    common_name  = null
    email        = []
    email_domain = []
    everyone     = null
    geo          = []
    github = [{
      identity_provider_id = null
      name                 = null
      teams                = []
    }]
    group = []
    gsuite = [{
      email                = []
      identity_provider_id = null
    }]
    ip = []
    okta = [{
      identity_provider_id = null
      name                 = []
    }]
    saml = [{
      attribute_name       = null
      attribute_value      = null
      identity_provider_id = null
    }]
    service_token = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_id" {
  description = "(required)"
  type        = string
}

variable "decision" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "precedence" {
  description = "(required)"
  type        = number
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "exclude" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      any_valid_service_token = bool
      auth_method             = string
      azure = list(object(
        {
          id                   = list(string)
          identity_provider_id = string
        }
      ))
      certificate  = bool
      common_name  = string
      email        = list(string)
      email_domain = list(string)
      everyone     = bool
      geo          = list(string)
      github = list(object(
        {
          identity_provider_id = string
          name                 = string
          teams                = list(string)
        }
      ))
      group = list(string)
      gsuite = list(object(
        {
          email                = list(string)
          identity_provider_id = string
        }
      ))
      ip = list(string)
      okta = list(object(
        {
          identity_provider_id = string
          name                 = list(string)
        }
      ))
      saml = list(object(
        {
          attribute_name       = string
          attribute_value      = string
          identity_provider_id = string
        }
      ))
      service_token = list(string)
    }
  ))
  default = []
}

variable "include" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      any_valid_service_token = bool
      auth_method             = string
      azure = list(object(
        {
          id                   = list(string)
          identity_provider_id = string
        }
      ))
      certificate  = bool
      common_name  = string
      email        = list(string)
      email_domain = list(string)
      everyone     = bool
      geo          = list(string)
      github = list(object(
        {
          identity_provider_id = string
          name                 = string
          teams                = list(string)
        }
      ))
      group = list(string)
      gsuite = list(object(
        {
          email                = list(string)
          identity_provider_id = string
        }
      ))
      ip = list(string)
      okta = list(object(
        {
          identity_provider_id = string
          name                 = list(string)
        }
      ))
      saml = list(object(
        {
          attribute_name       = string
          attribute_value      = string
          identity_provider_id = string
        }
      ))
      service_token = list(string)
    }
  ))
}

variable "require" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      any_valid_service_token = bool
      auth_method             = string
      azure = list(object(
        {
          id                   = list(string)
          identity_provider_id = string
        }
      ))
      certificate  = bool
      common_name  = string
      email        = list(string)
      email_domain = list(string)
      everyone     = bool
      geo          = list(string)
      github = list(object(
        {
          identity_provider_id = string
          name                 = string
          teams                = list(string)
        }
      ))
      group = list(string)
      gsuite = list(object(
        {
          email                = list(string)
          identity_provider_id = string
        }
      ))
      ip = list(string)
      okta = list(object(
        {
          identity_provider_id = string
          name                 = list(string)
        }
      ))
      saml = list(object(
        {
          attribute_name       = string
          attribute_value      = string
          identity_provider_id = string
        }
      ))
      service_token = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_access_policy" "this" {
  # account_id - (optional) is a type of string
  account_id = var.account_id
  # application_id - (required) is a type of string
  application_id = var.application_id
  # decision - (required) is a type of string
  decision = var.decision
  # name - (required) is a type of string
  name = var.name
  # precedence - (required) is a type of number
  precedence = var.precedence
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id

  dynamic "exclude" {
    for_each = var.exclude
    content {
      # any_valid_service_token - (optional) is a type of bool
      any_valid_service_token = exclude.value["any_valid_service_token"]
      # auth_method - (optional) is a type of string
      auth_method = exclude.value["auth_method"]
      # certificate - (optional) is a type of bool
      certificate = exclude.value["certificate"]
      # common_name - (optional) is a type of string
      common_name = exclude.value["common_name"]
      # email - (optional) is a type of list of string
      email = exclude.value["email"]
      # email_domain - (optional) is a type of list of string
      email_domain = exclude.value["email_domain"]
      # everyone - (optional) is a type of bool
      everyone = exclude.value["everyone"]
      # geo - (optional) is a type of list of string
      geo = exclude.value["geo"]
      # group - (optional) is a type of list of string
      group = exclude.value["group"]
      # ip - (optional) is a type of list of string
      ip = exclude.value["ip"]
      # service_token - (optional) is a type of list of string
      service_token = exclude.value["service_token"]

      dynamic "azure" {
        for_each = exclude.value.azure
        content {
          # id - (optional) is a type of list of string
          id = azure.value["id"]
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = azure.value["identity_provider_id"]
        }
      }

      dynamic "github" {
        for_each = exclude.value.github
        content {
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = github.value["identity_provider_id"]
          # name - (optional) is a type of string
          name = github.value["name"]
          # teams - (optional) is a type of list of string
          teams = github.value["teams"]
        }
      }

      dynamic "gsuite" {
        for_each = exclude.value.gsuite
        content {
          # email - (optional) is a type of list of string
          email = gsuite.value["email"]
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = gsuite.value["identity_provider_id"]
        }
      }

      dynamic "okta" {
        for_each = exclude.value.okta
        content {
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = okta.value["identity_provider_id"]
          # name - (optional) is a type of list of string
          name = okta.value["name"]
        }
      }

      dynamic "saml" {
        for_each = exclude.value.saml
        content {
          # attribute_name - (optional) is a type of string
          attribute_name = saml.value["attribute_name"]
          # attribute_value - (optional) is a type of string
          attribute_value = saml.value["attribute_value"]
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = saml.value["identity_provider_id"]
        }
      }

    }
  }

  dynamic "include" {
    for_each = var.include
    content {
      # any_valid_service_token - (optional) is a type of bool
      any_valid_service_token = include.value["any_valid_service_token"]
      # auth_method - (optional) is a type of string
      auth_method = include.value["auth_method"]
      # certificate - (optional) is a type of bool
      certificate = include.value["certificate"]
      # common_name - (optional) is a type of string
      common_name = include.value["common_name"]
      # email - (optional) is a type of list of string
      email = include.value["email"]
      # email_domain - (optional) is a type of list of string
      email_domain = include.value["email_domain"]
      # everyone - (optional) is a type of bool
      everyone = include.value["everyone"]
      # geo - (optional) is a type of list of string
      geo = include.value["geo"]
      # group - (optional) is a type of list of string
      group = include.value["group"]
      # ip - (optional) is a type of list of string
      ip = include.value["ip"]
      # service_token - (optional) is a type of list of string
      service_token = include.value["service_token"]

      dynamic "azure" {
        for_each = include.value.azure
        content {
          # id - (optional) is a type of list of string
          id = azure.value["id"]
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = azure.value["identity_provider_id"]
        }
      }

      dynamic "github" {
        for_each = include.value.github
        content {
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = github.value["identity_provider_id"]
          # name - (optional) is a type of string
          name = github.value["name"]
          # teams - (optional) is a type of list of string
          teams = github.value["teams"]
        }
      }

      dynamic "gsuite" {
        for_each = include.value.gsuite
        content {
          # email - (optional) is a type of list of string
          email = gsuite.value["email"]
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = gsuite.value["identity_provider_id"]
        }
      }

      dynamic "okta" {
        for_each = include.value.okta
        content {
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = okta.value["identity_provider_id"]
          # name - (optional) is a type of list of string
          name = okta.value["name"]
        }
      }

      dynamic "saml" {
        for_each = include.value.saml
        content {
          # attribute_name - (optional) is a type of string
          attribute_name = saml.value["attribute_name"]
          # attribute_value - (optional) is a type of string
          attribute_value = saml.value["attribute_value"]
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = saml.value["identity_provider_id"]
        }
      }

    }
  }

  dynamic "require" {
    for_each = var.require
    content {
      # any_valid_service_token - (optional) is a type of bool
      any_valid_service_token = require.value["any_valid_service_token"]
      # auth_method - (optional) is a type of string
      auth_method = require.value["auth_method"]
      # certificate - (optional) is a type of bool
      certificate = require.value["certificate"]
      # common_name - (optional) is a type of string
      common_name = require.value["common_name"]
      # email - (optional) is a type of list of string
      email = require.value["email"]
      # email_domain - (optional) is a type of list of string
      email_domain = require.value["email_domain"]
      # everyone - (optional) is a type of bool
      everyone = require.value["everyone"]
      # geo - (optional) is a type of list of string
      geo = require.value["geo"]
      # group - (optional) is a type of list of string
      group = require.value["group"]
      # ip - (optional) is a type of list of string
      ip = require.value["ip"]
      # service_token - (optional) is a type of list of string
      service_token = require.value["service_token"]

      dynamic "azure" {
        for_each = require.value.azure
        content {
          # id - (optional) is a type of list of string
          id = azure.value["id"]
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = azure.value["identity_provider_id"]
        }
      }

      dynamic "github" {
        for_each = require.value.github
        content {
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = github.value["identity_provider_id"]
          # name - (optional) is a type of string
          name = github.value["name"]
          # teams - (optional) is a type of list of string
          teams = github.value["teams"]
        }
      }

      dynamic "gsuite" {
        for_each = require.value.gsuite
        content {
          # email - (optional) is a type of list of string
          email = gsuite.value["email"]
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = gsuite.value["identity_provider_id"]
        }
      }

      dynamic "okta" {
        for_each = require.value.okta
        content {
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = okta.value["identity_provider_id"]
          # name - (optional) is a type of list of string
          name = okta.value["name"]
        }
      }

      dynamic "saml" {
        for_each = require.value.saml
        content {
          # attribute_name - (optional) is a type of string
          attribute_name = saml.value["attribute_name"]
          # attribute_value - (optional) is a type of string
          attribute_value = saml.value["attribute_value"]
          # identity_provider_id - (optional) is a type of string
          identity_provider_id = saml.value["identity_provider_id"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = cloudflare_access_policy.this.account_id
}

output "id" {
  description = "returns a string"
  value       = cloudflare_access_policy.this.id
}

output "zone_id" {
  description = "returns a string"
  value       = cloudflare_access_policy.this.zone_id
}

output "this" {
  value = cloudflare_access_policy.this
}
```

[top](#index)