# exoscale_security_group

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_security_group" {
  source = "./modules/exoscale/d/exoscale_security_group"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the Security Group"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "exoscale_security_group" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.exoscale_security_group.this.id
}

output "this" {
  value = exoscale_security_group.this
}
```

[top](#index)