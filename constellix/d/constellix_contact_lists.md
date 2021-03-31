# constellix_contact_lists

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    constellix = ">= 0.3.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "constellix_contact_lists" {
  source = "./modules/constellix/d/constellix_contact_lists"

  # email_addresses - (optional) is a type of list of string
  email_addresses = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "email_addresses" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "constellix_contact_lists" "this" {
  email_addresses = var.email_addresses
  name            = var.name
}
```

[top](#index)

### Outputs

```terraform
output "email_addresses" {
  description = "returns a list of string"
  value       = data.constellix_contact_lists.this.email_addresses
}

output "id" {
  description = "returns a string"
  value       = data.constellix_contact_lists.this.id
}

output "this" {
  value = constellix_contact_lists.this
}
```

[top](#index)