# avi_trafficcloneprofile

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
module "avi_trafficcloneprofile" {
  source = "./modules/avi/d/avi_trafficcloneprofile"

  # cloud_ref - (optional) is a type of string
  cloud_ref = null
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
variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

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
data "avi_trafficcloneprofile" "this" {
  # cloud_ref - (optional) is a type of string
  cloud_ref = var.cloud_ref
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
output "clone_servers" {
  description = "returns a list of object"
  value       = data.avi_trafficcloneprofile.this.clone_servers
}

output "cloud_ref" {
  description = "returns a string"
  value       = data.avi_trafficcloneprofile.this.cloud_ref
}

output "id" {
  description = "returns a string"
  value       = data.avi_trafficcloneprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_trafficcloneprofile.this.name
}

output "preserve_client_ip" {
  description = "returns a bool"
  value       = data.avi_trafficcloneprofile.this.preserve_client_ip
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_trafficcloneprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_trafficcloneprofile.this.uuid
}

output "this" {
  value = avi_trafficcloneprofile.this
}
```

[top](#index)