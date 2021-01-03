# aci_cloud_domain_profile

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
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_cloud_domain_profile" {
  source = "./modules/aci/d/aci_cloud_domain_profile"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # site_id - (optional) is a type of string
  site_id = null
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

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "site_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_cloud_domain_profile" "this" {
  annotation  = var.annotation
  description = var.description
  name_alias  = var.name_alias
  site_id     = var.site_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_cloud_domain_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_cloud_domain_profile.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_cloud_domain_profile.this.name_alias
}

output "site_id" {
  description = "returns a string"
  value       = data.aci_cloud_domain_profile.this.site_id
}

output "this" {
  value = aci_cloud_domain_profile.this
}
```

[top](#index)