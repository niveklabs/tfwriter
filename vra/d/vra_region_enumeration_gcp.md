# vra_region_enumeration_gcp

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
module "vra_region_enumeration_gcp" {
  source = "./modules/vra/d/vra_region_enumeration_gcp"

  # client_email - (required) is a type of string
  client_email = null
  # private_key - (required) is a type of string
  private_key = null
  # private_key_id - (required) is a type of string
  private_key_id = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "client_email" {
  description = "(required)"
  type        = string
}

variable "private_key" {
  description = "(required)"
  type        = string
}

variable "private_key_id" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vra_region_enumeration_gcp" "this" {
  # client_email - (required) is a type of string
  client_email = var.client_email
  # private_key - (required) is a type of string
  private_key = var.private_key
  # private_key_id - (required) is a type of string
  private_key_id = var.private_key_id
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vra_region_enumeration_gcp.this.id
}

output "regions" {
  description = "returns a list of string"
  value       = data.vra_region_enumeration_gcp.this.regions
}

output "this" {
  value = vra_region_enumeration_gcp.this
}
```

[top](#index)