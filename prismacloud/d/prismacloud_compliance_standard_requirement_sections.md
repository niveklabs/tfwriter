# prismacloud_compliance_standard_requirement_sections

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
    prismacloud = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_compliance_standard_requirement_sections" {
  source = "./modules/prismacloud/d/prismacloud_compliance_standard_requirement_sections"

  # csr_id - (required) is a type of string
  csr_id = null
}
```

[top](#index)

### Variables

```terraform
variable "csr_id" {
  description = "(required) - Compliance standard requirement ID"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_compliance_standard_requirement_sections" "this" {
  # csr_id - (required) is a type of string
  csr_id = var.csr_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.prismacloud_compliance_standard_requirement_sections.this.id
}

output "listing" {
  description = "returns a list of object"
  value       = data.prismacloud_compliance_standard_requirement_sections.this.listing
}

output "total" {
  description = "returns a number"
  value       = data.prismacloud_compliance_standard_requirement_sections.this.total
}

output "this" {
  value = prismacloud_compliance_standard_requirement_sections.this
}
```

[top](#index)