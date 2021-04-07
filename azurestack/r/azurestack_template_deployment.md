# azurestack_template_deployment

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurestack = ">= 0.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurestack_template_deployment" {
  source = "./modules/azurestack/r/azurestack_template_deployment"

  # deployment_mode - (required) is a type of string
  deployment_mode = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # parameters_body - (optional) is a type of string
  parameters_body = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # template_body - (optional) is a type of string
  template_body = null
}
```

[top](#index)

### Variables

```terraform
variable "deployment_mode" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "parameters_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "template_body" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_template_deployment" "this" {
  # deployment_mode - (required) is a type of string
  deployment_mode = var.deployment_mode
  # name - (required) is a type of string
  name = var.name
  # parameters - (optional) is a type of map of string
  parameters = var.parameters
  # parameters_body - (optional) is a type of string
  parameters_body = var.parameters_body
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # template_body - (optional) is a type of string
  template_body = var.template_body
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_template_deployment.this.id
}

output "outputs" {
  description = "returns a map of string"
  value       = azurestack_template_deployment.this.outputs
}

output "template_body" {
  description = "returns a string"
  value       = azurestack_template_deployment.this.template_body
}

output "this" {
  value = azurestack_template_deployment.this
}
```

[top](#index)