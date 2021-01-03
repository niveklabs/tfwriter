# digitalocean_spaces_bucket

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
module "digitalocean_spaces_bucket" {
  source = "./modules/digitalocean/d/digitalocean_spaces_bucket"

  # name - (required) is a type of string
  name = null
  # region - (required) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Bucket name"
  type        = string
}

variable "region" {
  description = "(required) - Bucket region"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_spaces_bucket" "this" {
  name   = var.name
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "bucket_domain_name" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket.this.bucket_domain_name
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket.this.id
}

output "urn" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket.this.urn
}

output "this" {
  value = digitalocean_spaces_bucket.this
}
```

[top](#index)