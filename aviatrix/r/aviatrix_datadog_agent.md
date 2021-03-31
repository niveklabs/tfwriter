# aviatrix_datadog_agent

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
module "aviatrix_datadog_agent" {
  source = "./modules/aviatrix/r/aviatrix_datadog_agent"

  # api_key - (required) is a type of string
  api_key = null
  # excluded_gateways - (optional) is a type of set of string
  excluded_gateways = []
  # metrics_only - (optional) is a type of bool
  metrics_only = null
  # site - (optional) is a type of string
  site = null
}
```

[top](#index)

### Variables

```terraform
variable "api_key" {
  description = "(required) - API key."
  type        = string
}

variable "excluded_gateways" {
  description = "(optional) - List of excluded gateways."
  type        = set(string)
  default     = null
}

variable "metrics_only" {
  description = "(optional) - Only export metrics without exporting logs."
  type        = bool
  default     = null
}

variable "site" {
  description = "(optional) - Site preference."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_datadog_agent" "this" {
  api_key           = var.api_key
  excluded_gateways = var.excluded_gateways
  metrics_only      = var.metrics_only
  site              = var.site
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_datadog_agent.this.id
}

output "status" {
  description = "returns a string"
  value       = aviatrix_datadog_agent.this.status
}

output "this" {
  value = aviatrix_datadog_agent.this
}
```

[top](#index)