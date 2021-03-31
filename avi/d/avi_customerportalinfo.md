# avi_customerportalinfo

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
module "avi_customerportalinfo" {
  source = "./modules/avi/d/avi_customerportalinfo"

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
data "avi_customerportalinfo" "this" {
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.avi_customerportalinfo.this.id
}

output "polling_interval" {
  description = "returns a number"
  value       = data.avi_customerportalinfo.this.polling_interval
}

output "portal_url" {
  description = "returns a string"
  value       = data.avi_customerportalinfo.this.portal_url
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_customerportalinfo.this.uuid
}

output "this" {
  value = avi_customerportalinfo.this
}
```

[top](#index)