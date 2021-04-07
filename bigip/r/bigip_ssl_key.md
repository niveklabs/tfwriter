# bigip_ssl_key

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
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ssl_key" {
  source = "./modules/bigip/r/bigip_ssl_key"

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
  description = "(required) - Content of SSL certificate key present on local Disk"
  type        = string
}

variable "name" {
  description = "(required) - Name of SSL Certificate key with .key extension"
  type        = string
}

variable "partition" {
  description = "(optional) - Partition of ssl certificate key"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ssl_key" "this" {
  # content - (required) is a type of string
  content = var.content
  # name - (required) is a type of string
  name = var.name
  # partition - (optional) is a type of string
  partition = var.partition
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_ssl_key.this.id
}

output "this" {
  value = bigip_ssl_key.this
}
```

[top](#index)