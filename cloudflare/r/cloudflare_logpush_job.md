# cloudflare_logpush_job

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
    cloudflare = ">= 2.15.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_logpush_job" {
  source = "./modules/cloudflare/r/cloudflare_logpush_job"

  # dataset - (required) is a type of string
  dataset = null
  # destination_conf - (required) is a type of string
  destination_conf = null
  # enabled - (optional) is a type of bool
  enabled = null
  # logpull_options - (optional) is a type of string
  logpull_options = null
  # name - (optional) is a type of string
  name = null
  # ownership_challenge - (required) is a type of string
  ownership_challenge = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "dataset" {
  description = "(required)"
  type        = string
}

variable "destination_conf" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "logpull_options" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ownership_challenge" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_logpush_job" "this" {
  dataset             = var.dataset
  destination_conf    = var.destination_conf
  enabled             = var.enabled
  logpull_options     = var.logpull_options
  name                = var.name
  ownership_challenge = var.ownership_challenge
  zone_id             = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_logpush_job.this.id
}

output "this" {
  value = cloudflare_logpush_job.this
}
```

[top](#index)