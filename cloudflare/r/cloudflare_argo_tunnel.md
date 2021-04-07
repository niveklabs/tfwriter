# cloudflare_argo_tunnel

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
module "cloudflare_argo_tunnel" {
  source = "./modules/cloudflare/r/cloudflare_argo_tunnel"

  # account_id - (required) is a type of string
  account_id = null
  # name - (required) is a type of string
  name = null
  # secret - (required) is a type of string
  secret = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "secret" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_argo_tunnel" "this" {
  # account_id - (required) is a type of string
  account_id = var.account_id
  # name - (required) is a type of string
  name = var.name
  # secret - (required) is a type of string
  secret = var.secret
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_argo_tunnel.this.id
}

output "this" {
  value = cloudflare_argo_tunnel.this
}
```

[top](#index)