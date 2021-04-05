# okta_users

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_users" {
  source = "./modules/okta/d/okta_users"


  search = [{
    comparison = null
    name       = null
    value      = null
  }]

  users = [{
    admin_roles               = []
    city                      = null
    cost_center               = null
    country_code              = null
    custom_profile_attributes = null
    department                = null
    display_name              = null
    division                  = null
    email                     = null
    employee_number           = null
    first_name                = null
    group_memberships         = []
    honorific_prefix          = null
    honorific_suffix          = null
    id                        = null
    last_name                 = null
    locale                    = null
    login                     = null
    manager                   = null
    manager_id                = null
    middle_name               = null
    mobile_phone              = null
    nick_name                 = null
    organization              = null
    postal_address            = null
    preferred_language        = null
    primary_phone             = null
    profile_url               = null
    second_email              = null
    state                     = null
    status                    = null
    street_address            = null
    timezone                  = null
    title                     = null
    user_type                 = null
    zip_code                  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "search" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      comparison = string
      name       = string
      value      = string
    }
  ))
}

variable "users" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      admin_roles               = set(string)
      city                      = string
      cost_center               = string
      country_code              = string
      custom_profile_attributes = string
      department                = string
      display_name              = string
      division                  = string
      email                     = string
      employee_number           = string
      first_name                = string
      group_memberships         = set(string)
      honorific_prefix          = string
      honorific_suffix          = string
      id                        = string
      last_name                 = string
      locale                    = string
      login                     = string
      manager                   = string
      manager_id                = string
      middle_name               = string
      mobile_phone              = string
      nick_name                 = string
      organization              = string
      postal_address            = string
      preferred_language        = string
      primary_phone             = string
      profile_url               = string
      second_email              = string
      state                     = string
      status                    = string
      street_address            = string
      timezone                  = string
      title                     = string
      user_type                 = string
      zip_code                  = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "okta_users" "this" {

  dynamic "search" {
    for_each = var.search
    content {
      comparison = search.value["comparison"]
      name       = search.value["name"]
      value      = search.value["value"]
    }
  }

  dynamic "users" {
    for_each = var.users
    content {
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.okta_users.this.id
}

output "this" {
  value = okta_users.this
}
```

[top](#index)