# digitalocean_kubernetes_versions

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
    digitalocean = ">= 2.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_kubernetes_versions" {
  source = "./modules/digitalocean/d/digitalocean_kubernetes_versions"

  # version_prefix - (optional) is a type of string
  version_prefix = null
}
```

[top](#index)

### Variables

```terraform
variable "version_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_kubernetes_versions" "this" {
  # version_prefix - (optional) is a type of string
  version_prefix = var.version_prefix
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_versions.this.id
}

output "latest_version" {
  description = "returns a string"
  value       = data.digitalocean_kubernetes_versions.this.latest_version
}

output "valid_versions" {
  description = "returns a list of string"
  value       = data.digitalocean_kubernetes_versions.this.valid_versions
}

output "this" {
  value = digitalocean_kubernetes_versions.this
}
```

[top](#index)