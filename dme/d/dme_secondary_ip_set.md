# dme_secondary_ip_set

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
module "dme_secondary_ip_set" {
  source = "./modules/dme/d/dme_secondary_ip_set"

  # ips - (optional) is a type of list of string
  ips = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "ips" {
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
data "dme_secondary_ip_set" "this" {
  # ips - (optional) is a type of list of string
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
  value       = data.dme_secondary_ip_set.this.id
}

output "ips" {
  description = "returns a list of string"
  value       = data.dme_secondary_ip_set.this.ips
}

output "this" {
  value = dme_secondary_ip_set.this
}
```

[top](#index)