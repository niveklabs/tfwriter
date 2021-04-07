# cloudflare_workers_kv_namespace

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
module "cloudflare_workers_kv_namespace" {
  source = "./modules/cloudflare/r/cloudflare_workers_kv_namespace"

  # title - (required) is a type of string
  title = null
}
```

[top](#index)

### Variables

```terraform
variable "title" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_workers_kv_namespace" "this" {
  # title - (required) is a type of string
  title = var.title
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_workers_kv_namespace.this.id
}

output "this" {
  value = cloudflare_workers_kv_namespace.this
}
```

[top](#index)