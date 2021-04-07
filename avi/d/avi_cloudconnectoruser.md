# avi_cloudconnectoruser

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_cloudconnectoruser" {
  source = "./modules/avi/d/avi_cloudconnectoruser"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_cloudconnectoruser" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "azure_serviceprincipal" {
  description = "returns a set of object"
  value       = data.avi_cloudconnectoruser.this.azure_serviceprincipal
}

output "azure_userpass" {
  description = "returns a set of object"
  value       = data.avi_cloudconnectoruser.this.azure_userpass
}

output "gcp_credentials" {
  description = "returns a set of object"
  value       = data.avi_cloudconnectoruser.this.gcp_credentials
}

output "id" {
  description = "returns a string"
  value       = data.avi_cloudconnectoruser.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_cloudconnectoruser.this.name
}

output "oci_credentials" {
  description = "returns a set of object"
  value       = data.avi_cloudconnectoruser.this.oci_credentials
}

output "password" {
  description = "returns a string"
  value       = data.avi_cloudconnectoruser.this.password
}

output "private_key" {
  description = "returns a string"
  value       = data.avi_cloudconnectoruser.this.private_key
}

output "public_key" {
  description = "returns a string"
  value       = data.avi_cloudconnectoruser.this.public_key
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_cloudconnectoruser.this.tenant_ref
}

output "tencent_credentials" {
  description = "returns a set of object"
  value       = data.avi_cloudconnectoruser.this.tencent_credentials
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_cloudconnectoruser.this.uuid
}

output "this" {
  value = avi_cloudconnectoruser.this
}
```

[top](#index)