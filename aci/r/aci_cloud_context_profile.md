# aci_cloud_context_profile

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aci_cloud_context_profile" {
  source = "./modules/aci/r/aci_cloud_context_profile"

  # annotation - (optional) is a type of string
  annotation = null
  # cloud_vendor - (required) is a type of string
  cloud_vendor = null
  # description - (optional) is a type of string
  description = null
  # hub_network - (optional) is a type of string
  hub_network = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # primary_cidr - (required) is a type of string
  primary_cidr = null
  # region - (required) is a type of string
  region = null
  # relation_cloud_rs_ctx_profile_to_region - (optional) is a type of string
  relation_cloud_rs_ctx_profile_to_region = null
  # relation_cloud_rs_ctx_to_flow_log - (optional) is a type of string
  relation_cloud_rs_ctx_to_flow_log = null
  # relation_cloud_rs_to_ctx - (optional) is a type of string
  relation_cloud_rs_to_ctx = null
  # tenant_dn - (required) is a type of string
  tenant_dn = null
  # type - (optional) is a type of string
  type = null
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

variable "cloud_vendor" {
  description = "(required) - Name of the vendor"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hub_network" {
  description = "(optional) - hub network to enable transit gateway"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional) - Mo doc not defined in techpub!!!"
  type        = string
  default     = null
}

variable "primary_cidr" {
  description = "(required) - Primary CIDR block"
  type        = string
}

variable "region" {
  description = "(required) - region"
  type        = string
}

variable "relation_cloud_rs_ctx_profile_to_region" {
  description = "(optional) - Create relation to cloudRegion"
  type        = string
  default     = null
}

variable "relation_cloud_rs_ctx_to_flow_log" {
  description = "(optional) - Create relation to cloudAwsFlowLogPol"
  type        = string
  default     = null
}

variable "relation_cloud_rs_to_ctx" {
  description = "(optional) - Create relation to fvCtx"
  type        = string
  default     = null
}

variable "tenant_dn" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(optional) - component type"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aci_cloud_context_profile" "this" {
  annotation                              = var.annotation
  cloud_vendor                            = var.cloud_vendor
  description                             = var.description
  hub_network                             = var.hub_network
  name                                    = var.name
  name_alias                              = var.name_alias
  primary_cidr                            = var.primary_cidr
  region                                  = var.region
  relation_cloud_rs_ctx_profile_to_region = var.relation_cloud_rs_ctx_profile_to_region
  relation_cloud_rs_ctx_to_flow_log       = var.relation_cloud_rs_ctx_to_flow_log
  relation_cloud_rs_to_ctx                = var.relation_cloud_rs_to_ctx
  tenant_dn                               = var.tenant_dn
  type                                    = var.type
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = aci_cloud_context_profile.this.description
}

output "id" {
  description = "returns a string"
  value       = aci_cloud_context_profile.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = aci_cloud_context_profile.this.name_alias
}

output "type" {
  description = "returns a string"
  value       = aci_cloud_context_profile.this.type
}

output "this" {
  value = aci_cloud_context_profile.this
}
```

[top](#index)