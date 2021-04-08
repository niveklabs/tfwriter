# turbot_grant_activation

[back](../turbot.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "turbot_grant_activation" {
  source = "./modules/turbot/r/turbot_grant_activation"

  # grant - (required) is a type of string
  grant = null
  # resource - (required) is a type of string
  resource = null
}
```

[top](#index)

### Variables

```terraform
variable "grant" {
  description = "(required)"
  type        = string
}

variable "resource" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "turbot_grant_activation" "this" {
  # grant - (required) is a type of string
  grant = var.grant
  # resource - (required) is a type of string
  resource = var.resource
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = turbot_grant_activation.this.id
}

output "resource_akas" {
  description = "returns a list of string"
  value       = turbot_grant_activation.this.resource_akas
}

output "this" {
  value = turbot_grant_activation.this
}
```

[top](#index)