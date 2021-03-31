# digitalocean_spaces_bucket_objects

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
module "digitalocean_spaces_bucket_objects" {
  source = "./modules/digitalocean/d/digitalocean_spaces_bucket_objects"

  # bucket - (required) is a type of string
  bucket = null
  # delimiter - (optional) is a type of string
  delimiter = null
  # encoding_type - (optional) is a type of string
  encoding_type = null
  # max_keys - (optional) is a type of number
  max_keys = null
  # prefix - (optional) is a type of string
  prefix = null
  # region - (required) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "delimiter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encoding_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_keys" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_spaces_bucket_objects" "this" {
  bucket        = var.bucket
  delimiter     = var.delimiter
  encoding_type = var.encoding_type
  max_keys      = var.max_keys
  prefix        = var.prefix
  region        = var.region
}
```

[top](#index)

### Outputs

```terraform
output "common_prefixes" {
  description = "returns a list of string"
  value       = data.digitalocean_spaces_bucket_objects.this.common_prefixes
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_spaces_bucket_objects.this.id
}

output "keys" {
  description = "returns a list of string"
  value       = data.digitalocean_spaces_bucket_objects.this.keys
}

output "owners" {
  description = "returns a list of string"
  value       = data.digitalocean_spaces_bucket_objects.this.owners
}

output "this" {
  value = digitalocean_spaces_bucket_objects.this
}
```

[top](#index)