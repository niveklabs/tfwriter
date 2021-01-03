# prismacloud_compliance_standard_requirements

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.0.8"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_compliance_standard_requirements" {
  source = "./modules/prismacloud/d/prismacloud_compliance_standard_requirements"

  # cs_id - (required) is a type of string
  cs_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cs_id" {
  description = "(required) - Compliance standard ID"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_compliance_standard_requirements" "this" {
  cs_id = var.cs_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirements.this.id
}

output "listing" {
  description = "returns a list of object"
  value       = data.prismacloud_compliance_standard_requirements.this.listing
}

output "total" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard_requirements.this.total
}

output "this" {
  value = prismacloud_compliance_standard_requirements.this
}
```

[top](#index)