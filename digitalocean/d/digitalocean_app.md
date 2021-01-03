# digitalocean_app

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_app" {
  source = "./modules/digitalocean/d/digitalocean_app"

  # app_id - (required) is a type of string
  app_id = null
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_app" "this" {
  app_id = var.app_id
}
```

[top](#index)

### Outputs

```terraform
output "active_deployment_id" {
  description = "returns a string"
  value       = data.digitalocean_app.this.active_deployment_id
}

output "created_at" {
  description = "returns a string"
  value       = data.digitalocean_app.this.created_at
}

output "default_ingress" {
  description = "returns a string"
  value       = data.digitalocean_app.this.default_ingress
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_app.this.id
}

output "live_url" {
  description = "returns a string"
  value       = data.digitalocean_app.this.live_url
}

output "spec" {
  description = "returns a list of object"
  value       = data.digitalocean_app.this.spec
}

output "updated_at" {
  description = "returns a string"
  value       = data.digitalocean_app.this.updated_at
}

output "this" {
  value = digitalocean_app.this
}
```

[top](#index)