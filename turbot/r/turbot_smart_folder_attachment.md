# turbot_smart_folder_attachment

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
module "turbot_smart_folder_attachment" {
  source = "./modules/turbot/r/turbot_smart_folder_attachment"

  # resource - (required) is a type of string
  resource = null
  # smart_folder - (required) is a type of string
  smart_folder = null
}
```

[top](#index)

### Variables

```terraform
variable "resource" {
  description = "(required)"
  type        = string
}

variable "smart_folder" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "turbot_smart_folder_attachment" "this" {
  # resource - (required) is a type of string
  resource = var.resource
  # smart_folder - (required) is a type of string
  smart_folder = var.smart_folder
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = turbot_smart_folder_attachment.this.id
}

output "resource_akas" {
  description = "returns a list of string"
  value       = turbot_smart_folder_attachment.this.resource_akas
}

output "this" {
  value = turbot_smart_folder_attachment.this
}
```

[top](#index)