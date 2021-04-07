# avi_ipamdnsproviderprofile

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
module "avi_ipamdnsproviderprofile" {
  source = "./modules/avi/d/avi_ipamdnsproviderprofile"

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
data "avi_ipamdnsproviderprofile" "this" {
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
output "allocate_ip_in_vrf" {
  description = "returns a bool"
  value       = data.avi_ipamdnsproviderprofile.this.allocate_ip_in_vrf
}

output "aws_profile" {
  description = "returns a set of object"
  value       = data.avi_ipamdnsproviderprofile.this.aws_profile
}

output "azure_profile" {
  description = "returns a set of object"
  value       = data.avi_ipamdnsproviderprofile.this.azure_profile
}

output "custom_profile" {
  description = "returns a set of object"
  value       = data.avi_ipamdnsproviderprofile.this.custom_profile
}

output "gcp_profile" {
  description = "returns a set of object"
  value       = data.avi_ipamdnsproviderprofile.this.gcp_profile
}

output "id" {
  description = "returns a string"
  value       = data.avi_ipamdnsproviderprofile.this.id
}

output "infoblox_profile" {
  description = "returns a set of object"
  value       = data.avi_ipamdnsproviderprofile.this.infoblox_profile
}

output "internal_profile" {
  description = "returns a set of object"
  value       = data.avi_ipamdnsproviderprofile.this.internal_profile
}

output "name" {
  description = "returns a string"
  value       = data.avi_ipamdnsproviderprofile.this.name
}

output "oci_profile" {
  description = "returns a set of object"
  value       = data.avi_ipamdnsproviderprofile.this.oci_profile
}

output "openstack_profile" {
  description = "returns a set of object"
  value       = data.avi_ipamdnsproviderprofile.this.openstack_profile
}

output "proxy_configuration" {
  description = "returns a set of object"
  value       = data.avi_ipamdnsproviderprofile.this.proxy_configuration
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_ipamdnsproviderprofile.this.tenant_ref
}

output "tencent_profile" {
  description = "returns a set of object"
  value       = data.avi_ipamdnsproviderprofile.this.tencent_profile
}

output "type" {
  description = "returns a string"
  value       = data.avi_ipamdnsproviderprofile.this.type
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_ipamdnsproviderprofile.this.uuid
}

output "this" {
  value = avi_ipamdnsproviderprofile.this
}
```

[top](#index)