# dme_contact_list

[back](../dme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dme = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dme_contact_list" {
  source = "./modules/dme/r/dme_contact_list"

  # emails - (required) is a type of list of string
  emails = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "emails" {
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
resource "dme_contact_list" "this" {
  # emails - (required) is a type of list of string
  emails = var.emails
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dme_contact_list.this.id
}

output "this" {
  value = dme_contact_list.this
}
```

[top](#index)