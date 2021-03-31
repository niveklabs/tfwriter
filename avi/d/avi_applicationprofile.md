# avi_applicationprofile

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
module "avi_applicationprofile" {
  source = "./modules/avi/d/avi_applicationprofile"

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
data "avi_applicationprofile" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "cloud_config_cksum" {
  description = "returns a string"
  value       = data.avi_applicationprofile.this.cloud_config_cksum
}

output "created_by" {
  description = "returns a string"
  value       = data.avi_applicationprofile.this.created_by
}

output "description" {
  description = "returns a string"
  value       = data.avi_applicationprofile.this.description
}

output "dns_service_profile" {
  description = "returns a set of object"
  value       = data.avi_applicationprofile.this.dns_service_profile
}

output "dos_rl_profile" {
  description = "returns a set of object"
  value       = data.avi_applicationprofile.this.dos_rl_profile
}

output "http_profile" {
  description = "returns a set of object"
  value       = data.avi_applicationprofile.this.http_profile
}

output "id" {
  description = "returns a string"
  value       = data.avi_applicationprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_applicationprofile.this.name
}

output "preserve_client_ip" {
  description = "returns a bool"
  value       = data.avi_applicationprofile.this.preserve_client_ip
}

output "preserve_client_port" {
  description = "returns a bool"
  value       = data.avi_applicationprofile.this.preserve_client_port
}

output "sip_service_profile" {
  description = "returns a set of object"
  value       = data.avi_applicationprofile.this.sip_service_profile
}

output "tcp_app_profile" {
  description = "returns a set of object"
  value       = data.avi_applicationprofile.this.tcp_app_profile
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_applicationprofile.this.tenant_ref
}

output "type" {
  description = "returns a string"
  value       = data.avi_applicationprofile.this.type
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_applicationprofile.this.uuid
}

output "this" {
  value = avi_applicationprofile.this
}
```

[top](#index)