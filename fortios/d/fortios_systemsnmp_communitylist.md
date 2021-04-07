# fortios_systemsnmp_communitylist

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_systemsnmp_communitylist" {
  source = "./modules/fortios/d/fortios_systemsnmp_communitylist"

  # filter - (optional) is a type of string
  filter = null
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "fortios_systemsnmp_communitylist" "this" {
  # filter - (optional) is a type of string
  filter = var.filter
}
```

[top](#index)

### Outputs

```terraform
output "fosidlist" {
  description = "returns a list of number"
  value       = data.fortios_systemsnmp_communitylist.this.fosidlist
}

output "id" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_communitylist.this.id
}

output "this" {
  value = fortios_systemsnmp_communitylist.this
}
```

[top](#index)