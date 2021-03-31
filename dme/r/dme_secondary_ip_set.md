# dme_secondary_ip_set

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
module "dme_secondary_ip_set" {
  source = "./modules/dme/r/dme_secondary_ip_set"

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
resource "dme_secondary_ip_set" "this" {
  ips  = var.ips
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dme_secondary_ip_set.this.id
}

output "this" {
  value = dme_secondary_ip_set.this
}
```

[top](#index)