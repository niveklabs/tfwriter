# aci_cloud_aws_provider

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
module "aci_cloud_aws_provider" {
  source = "./modules/aci/r/aci_cloud_aws_provider"

  # access_key_id - (optional) is a type of string
  access_key_id = null
  # account_id - (optional) is a type of string
  account_id = null
  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # email - (optional) is a type of string
  email = null
  # http_proxy - (optional) is a type of string
  http_proxy = null
  # is_account_in_org - (optional) is a type of string
  is_account_in_org = null
  # is_trusted - (optional) is a type of string
  is_trusted = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # provider_id - (optional) is a type of string
  provider_id = null
  # region - (optional) is a type of string
  region = null
  # secret_access_key - (optional) is a type of string
  secret_access_key = null
  # tenant_dn - (required) is a type of string
  tenant_dn = null
}
```

[top](#index)

### Variables

```terraform
variable "access_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_proxy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_account_in_org" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_trusted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provider_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret_access_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_dn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aci_cloud_aws_provider" "this" {
  access_key_id     = var.access_key_id
  account_id        = var.account_id
  annotation        = var.annotation
  description       = var.description
  email             = var.email
  http_proxy        = var.http_proxy
  is_account_in_org = var.is_account_in_org
  is_trusted        = var.is_trusted
  name_alias        = var.name_alias
  provider_id       = var.provider_id
  region            = var.region
  secret_access_key = var.secret_access_key
  tenant_dn         = var.tenant_dn
}
```

[top](#index)

### Outputs

```terraform
output "access_key_id" {
  description = "returns a string"
  value       = aci_cloud_aws_provider.this.access_key_id
}

output "account_id" {
  description = "returns a string"
  value       = aci_cloud_aws_provider.this.account_id
}

output "description" {
  description = "returns a string"
  value       = aci_cloud_aws_provider.this.description
}

output "email" {
  description = "returns a string"
  value       = aci_cloud_aws_provider.this.email
}

output "http_proxy" {
  description = "returns a string"
  value       = aci_cloud_aws_provider.this.http_proxy
}

output "id" {
  description = "returns a string"
  value       = aci_cloud_aws_provider.this.id
}

output "is_account_in_org" {
  description = "returns a string"
  value       = aci_cloud_aws_provider.this.is_account_in_org
}

output "is_trusted" {
  description = "returns a string"
  value       = aci_cloud_aws_provider.this.is_trusted
}

output "name_alias" {
  description = "returns a string"
  value       = aci_cloud_aws_provider.this.name_alias
}

output "provider_id" {
  description = "returns a string"
  value       = aci_cloud_aws_provider.this.provider_id
}

output "region" {
  description = "returns a string"
  value       = aci_cloud_aws_provider.this.region
}

output "secret_access_key" {
  description = "returns a string"
  value       = aci_cloud_aws_provider.this.secret_access_key
}

output "this" {
  value = aci_cloud_aws_provider.this
}
```

[top](#index)