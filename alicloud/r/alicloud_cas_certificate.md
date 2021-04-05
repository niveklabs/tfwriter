# alicloud_cas_certificate

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cas_certificate" {
  source = "./modules/alicloud/r/alicloud_cas_certificate"

  # cert - (required) is a type of string
  cert = null
  # key - (required) is a type of string
  key = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "cert" {
  description = "(required)"
  type        = string
}

variable "key" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cas_certificate" "this" {
  cert = var.cert
  key  = var.key
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cas_certificate.this.id
}

output "this" {
  value = alicloud_cas_certificate.this
}
```

[top](#index)