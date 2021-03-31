# aci_cloud_provider_profile

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_cloud_provider_profile" {
  source = "./modules/aci/d/aci_cloud_provider_profile"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # vendor - (required) is a type of string
  vendor = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vendor" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aci_cloud_provider_profile" "this" {
  annotation  = var.annotation
  description = var.description
  vendor      = var.vendor
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_cloud_provider_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_cloud_provider_profile.this.id
}

output "this" {
  value = aci_cloud_provider_profile.this
}
```

[top](#index)