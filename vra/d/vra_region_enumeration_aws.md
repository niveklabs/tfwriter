# vra_region_enumeration_aws

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_region_enumeration_aws" {
  source = "./modules/vra/d/vra_region_enumeration_aws"

  # access_key - (optional) is a type of string
  access_key = null
  # secret_key - (required) is a type of string
  secret_key = null
}
```

[top](#index)

### Variables

```terraform
variable "access_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vra_region_enumeration_aws" "this" {
  # access_key - (optional) is a type of string
  access_key = var.access_key
  # secret_key - (required) is a type of string
  secret_key = var.secret_key
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vra_region_enumeration_aws.this.id
}

output "regions" {
  description = "returns a list of string"
  value       = data.vra_region_enumeration_aws.this.regions
}

output "this" {
  value = vra_region_enumeration_aws.this
}
```

[top](#index)