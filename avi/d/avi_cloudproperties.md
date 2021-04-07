# avi_cloudproperties

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
module "avi_cloudproperties" {
  source = "./modules/avi/d/avi_cloudproperties"

  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_cloudproperties" "this" {
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "cc_props" {
  description = "returns a set of object"
  value       = data.avi_cloudproperties.this.cc_props
}

output "cc_vtypes" {
  description = "returns a list of string"
  value       = data.avi_cloudproperties.this.cc_vtypes
}

output "hyp_props" {
  description = "returns a list of object"
  value       = data.avi_cloudproperties.this.hyp_props
}

output "id" {
  description = "returns a string"
  value       = data.avi_cloudproperties.this.id
}

output "info" {
  description = "returns a list of object"
  value       = data.avi_cloudproperties.this.info
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_cloudproperties.this.uuid
}

output "this" {
  value = avi_cloudproperties.this
}
```

[top](#index)