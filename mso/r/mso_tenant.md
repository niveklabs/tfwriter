# mso_tenant

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_tenant" {
  source = "./modules/mso/r/mso_tenant"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # name - (required) is a type of string
  name = null

  site_associations = [{
    aws_access_key_id         = null
    aws_account_id            = null
    aws_secret_key            = null
    azure_access_type         = null
    azure_active_directory_id = null
    azure_application_id      = null
    azure_client_secret       = null
    azure_shared_account_id   = null
    azure_subscription_id     = null
    is_aws_account_trusted    = null
    security_domains          = []
    site_id                   = null
    vendor                    = null
  }]

  user_associations = [{
    user_id = null
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

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "site_associations" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      aws_access_key_id         = string
      aws_account_id            = string
      aws_secret_key            = string
      azure_access_type         = string
      azure_active_directory_id = string
      azure_application_id      = string
      azure_client_secret       = string
      azure_shared_account_id   = string
      azure_subscription_id     = string
      is_aws_account_trusted    = bool
      security_domains          = list(string)
      site_id                   = string
      vendor                    = string
    }
  ))
  default = []
}

variable "user_associations" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      user_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "mso_tenant" "this" {
  description  = var.description
  display_name = var.display_name
  name         = var.name

  dynamic "site_associations" {
    for_each = var.site_associations
    content {
      aws_access_key_id         = site_associations.value["aws_access_key_id"]
      aws_account_id            = site_associations.value["aws_account_id"]
      aws_secret_key            = site_associations.value["aws_secret_key"]
      azure_access_type         = site_associations.value["azure_access_type"]
      azure_active_directory_id = site_associations.value["azure_active_directory_id"]
      azure_application_id      = site_associations.value["azure_application_id"]
      azure_client_secret       = site_associations.value["azure_client_secret"]
      azure_shared_account_id   = site_associations.value["azure_shared_account_id"]
      azure_subscription_id     = site_associations.value["azure_subscription_id"]
      is_aws_account_trusted    = site_associations.value["is_aws_account_trusted"]
      security_domains          = site_associations.value["security_domains"]
      site_id                   = site_associations.value["site_id"]
      vendor                    = site_associations.value["vendor"]
    }
  }

  dynamic "user_associations" {
    for_each = var.user_associations
    content {
      user_id = user_associations.value["user_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = mso_tenant.this.description
}

output "id" {
  description = "returns a string"
  value       = mso_tenant.this.id
}

output "this" {
  value = mso_tenant.this
}
```

[top](#index)