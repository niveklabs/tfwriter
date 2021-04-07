# mso_tenant

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/mso/d/mso_tenant"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # name - (required) is a type of string
  name = null

  site_associations = [{
    security_domains = []
    site_id          = null
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
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      security_domains = list(string)
      site_id          = string
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

### Datasource

```terraform
data "mso_tenant" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # name - (required) is a type of string
  name = var.name

  dynamic "site_associations" {
    for_each = var.site_associations
    content {
      # security_domains - (optional) is a type of list of string
      security_domains = site_associations.value["security_domains"]
      # site_id - (optional) is a type of string
      site_id = site_associations.value["site_id"]
    }
  }

  dynamic "user_associations" {
    for_each = var.user_associations
    content {
      # user_id - (optional) is a type of string
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
  value       = data.mso_tenant.this.description
}

output "id" {
  description = "returns a string"
  value       = data.mso_tenant.this.id
}

output "this" {
  value = mso_tenant.this
}
```

[top](#index)