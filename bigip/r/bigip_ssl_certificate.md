# bigip_ssl_certificate

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ssl_certificate" {
  source = "./modules/bigip/r/bigip_ssl_certificate"

  # content - (required) is a type of string
  content = null
  # name - (required) is a type of string
  name = null
  # partition - (optional) is a type of string
  partition = null
}
```

[top](#index)

### Variables

```terraform
variable "content" {
  description = "(required) - Content of certificate on Disk"
  type        = string
}

variable "name" {
  description = "(required) - Name of SSL Certificate with .crt extension"
  type        = string
}

variable "partition" {
  description = "(optional) - Partition of ssl certificate"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ssl_certificate" "this" {
  content   = var.content
  name      = var.name
  partition = var.partition
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_ssl_certificate.this.id
}

output "this" {
  value = bigip_ssl_certificate.this
}
```

[top](#index)