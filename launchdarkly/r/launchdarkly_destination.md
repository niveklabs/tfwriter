# launchdarkly_destination

[back](../launchdarkly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    launchdarkly = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "launchdarkly_destination" {
  source = "./modules/launchdarkly/r/launchdarkly_destination"

  # config - (optional) is a type of map of string
  config = {}
  # enabled - (optional) is a type of bool
  enabled = null
  # env_key - (required) is a type of string
  env_key = null
  # kind - (required) is a type of string
  kind = null
  # name - (required) is a type of string
  name = null
  # project_key - (required) is a type of string
  project_key = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "config" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "env_key" {
  description = "(required) - The LaunchDarkly environment key"
  type        = string
}

variable "kind" {
  description = "(required) - The data export destination type - must be 'kinesis', 'google-pubsub', 'mparticle', or 'segment'"
  type        = string
}

variable "name" {
  description = "(required) - a human-readable name for your data export destination"
  type        = string
}

variable "project_key" {
  description = "(required) - The LaunchDarkly project key"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "launchdarkly_destination" "this" {
  config      = var.config
  enabled     = var.enabled
  env_key     = var.env_key
  kind        = var.kind
  name        = var.name
  project_key = var.project_key
  tags        = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = launchdarkly_destination.this.id
}

output "this" {
  value = launchdarkly_destination.this
}
```

[top](#index)