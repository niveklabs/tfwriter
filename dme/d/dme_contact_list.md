# dme_contact_list

[back](../dme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/dme/d/dme_contact_list"

  # emails - (optional) is a type of list of string
  emails = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "emails" {
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
data "dme_contact_list" "this" {
  emails = var.emails
  name   = var.name
}
```

[top](#index)

### Outputs

```terraform
output "emails" {
  description = "returns a list of string"
  value       = data.dme_contact_list.this.emails
}

output "id" {
  description = "returns a string"
  value       = data.dme_contact_list.this.id
}

output "this" {
  value = dme_contact_list.this
}
```

[top](#index)