# constellix_contact_lists

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/constellix/r/constellix_contact_lists"

  # email_addresses - (required) is a type of list of string
  email_addresses = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "email_addresses" {
  description = "(required)"
  type        = list(string)
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "constellix_contact_lists" "this" {
  # email_addresses - (required) is a type of list of string
  email_addresses = var.email_addresses
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = constellix_contact_lists.this.id
}

output "this" {
  value = constellix_contact_lists.this
}
```

[top](#index)