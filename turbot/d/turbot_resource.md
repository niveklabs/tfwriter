# turbot_resource

[back](../turbot.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    turbot = ">= 1.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "turbot_resource" {
  source = "./modules/turbot/d/turbot_resource"

  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "turbot_resource" "this" {
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "akas" {
  description = "returns a list of string"
  value       = data.turbot_resource.this.akas
}

output "data" {
  description = "returns a string"
  value       = data.turbot_resource.this.data
}

output "id" {
  description = "returns a string"
  value       = data.turbot_resource.this.id
}

output "metadata" {
  description = "returns a string"
  value       = data.turbot_resource.this.metadata
}

output "turbot" {
  description = "returns a map of string"
  value       = data.turbot_resource.this.turbot
}

output "this" {
  value = turbot_resource.this
}
```

[top](#index)