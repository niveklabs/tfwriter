# aviatrix_cloudwatch_agent

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_cloudwatch_agent" {
  source = "./modules/aviatrix/r/aviatrix_cloudwatch_agent"

  # cloudwatch_role_arn - (required) is a type of string
  cloudwatch_role_arn = null
  # excluded_gateways - (optional) is a type of set of string
  excluded_gateways = []
  # log_group_name - (optional) is a type of string
  log_group_name = null
  # region - (required) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "cloudwatch_role_arn" {
  description = "(required) - CloudWatch role ARN."
  type        = string
}

variable "excluded_gateways" {
  description = "(optional) - List of excluded gateways."
  type        = set(string)
  default     = null
}

variable "log_group_name" {
  description = "(optional) - Log group name."
  type        = string
  default     = null
}

variable "region" {
  description = "(required) - Name of AWS region."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_cloudwatch_agent" "this" {
  # cloudwatch_role_arn - (required) is a type of string
  cloudwatch_role_arn = var.cloudwatch_role_arn
  # excluded_gateways - (optional) is a type of set of string
  excluded_gateways = var.excluded_gateways
  # log_group_name - (optional) is a type of string
  log_group_name = var.log_group_name
  # region - (required) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_cloudwatch_agent.this.id
}

output "status" {
  description = "returns a string"
  value       = aviatrix_cloudwatch_agent.this.status
}

output "this" {
  value = aviatrix_cloudwatch_agent.this
}
```

[top](#index)