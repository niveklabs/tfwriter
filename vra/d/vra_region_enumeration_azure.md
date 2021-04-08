# vra_region_enumeration_azure

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
module "vra_region_enumeration_azure" {
  source = "./modules/vra/d/vra_region_enumeration_azure"

  # application_id - (required) is a type of string
  application_id = null
  # application_key - (required) is a type of string
  application_key = null
  # subscription_id - (required) is a type of string
  subscription_id = null
  # tenant_id - (required) is a type of string
  tenant_id = null
}
```

[top](#index)

### Variables

```terraform
variable "application_id" {
  description = "(required)"
  type        = string
}

variable "application_key" {
  description = "(required)"
  type        = string
}

variable "subscription_id" {
  description = "(required)"
  type        = string
}

variable "tenant_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vra_region_enumeration_azure" "this" {
  # application_id - (required) is a type of string
  application_id = var.application_id
  # application_key - (required) is a type of string
  application_key = var.application_key
  # subscription_id - (required) is a type of string
  subscription_id = var.subscription_id
  # tenant_id - (required) is a type of string
  tenant_id = var.tenant_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vra_region_enumeration_azure.this.id
}

output "regions" {
  description = "returns a list of string"
  value       = data.vra_region_enumeration_azure.this.regions
}

output "this" {
  value = vra_region_enumeration_azure.this
}
```

[top](#index)