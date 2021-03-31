# avi_snmptrapprofile

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
module "avi_snmptrapprofile" {
  source = "./modules/avi/d/avi_snmptrapprofile"

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
data "avi_snmptrapprofile" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.avi_snmptrapprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_snmptrapprofile.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_snmptrapprofile.this.tenant_ref
}

output "trap_servers" {
  description = "returns a list of object"
  value       = data.avi_snmptrapprofile.this.trap_servers
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_snmptrapprofile.this.uuid
}

output "this" {
  value = avi_snmptrapprofile.this
}
```

[top](#index)