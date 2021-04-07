# cloudflare_workers_kv

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_workers_kv" {
  source = "./modules/cloudflare/r/cloudflare_workers_kv"

  # key - (required) is a type of string
  key = null
  # namespace_id - (required) is a type of string
  namespace_id = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "key" {
  description = "(required)"
  type        = string
}

variable "namespace_id" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_workers_kv" "this" {
  # key - (required) is a type of string
  key = var.key
  # namespace_id - (required) is a type of string
  namespace_id = var.namespace_id
  # value - (required) is a type of string
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_workers_kv.this.id
}

output "this" {
  value = cloudflare_workers_kv.this
}
```

[top](#index)