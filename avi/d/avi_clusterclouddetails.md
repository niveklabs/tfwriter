# avi_clusterclouddetails

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
module "avi_clusterclouddetails" {
  source = "./modules/avi/d/avi_clusterclouddetails"

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
data "avi_clusterclouddetails" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "azure_info" {
  description = "returns a set of object"
  value       = data.avi_clusterclouddetails.this.azure_info
}

output "id" {
  description = "returns a string"
  value       = data.avi_clusterclouddetails.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_clusterclouddetails.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_clusterclouddetails.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_clusterclouddetails.this.uuid
}

output "this" {
  value = avi_clusterclouddetails.this
}
```

[top](#index)