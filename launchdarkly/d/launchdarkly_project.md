# launchdarkly_project

[back](../launchdarkly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    launchdarkly = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "launchdarkly_project" {
  source = "./modules/launchdarkly/d/launchdarkly_project"

  # key - (required) is a type of string
  key = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "key" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "launchdarkly_project" "this" {
  key  = var.key
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "client_side_availability" {
  description = "returns a map of string"
  value       = data.launchdarkly_project.this.client_side_availability
}

output "id" {
  description = "returns a string"
  value       = data.launchdarkly_project.this.id
}

output "name" {
  description = "returns a string"
  value       = data.launchdarkly_project.this.name
}

output "this" {
  value = launchdarkly_project.this
}
```

[top](#index)