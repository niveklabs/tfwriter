# dme_transfer_acl

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
module "dme_transfer_acl" {
  source = "./modules/dme/r/dme_transfer_acl"

  # ips - (required) is a type of list of string
  ips = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "ips" {
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
resource "dme_transfer_acl" "this" {
  # ips - (required) is a type of list of string
  ips = var.ips
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dme_transfer_acl.this.id
}

output "this" {
  value = dme_transfer_acl.this
}
```

[top](#index)