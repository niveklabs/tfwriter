# aviatrix_netflow_agent

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
module "aviatrix_netflow_agent" {
  source = "./modules/aviatrix/r/aviatrix_netflow_agent"

  # excluded_gateways - (optional) is a type of set of string
  excluded_gateways = []
  # port - (required) is a type of number
  port = null
  # server_ip - (required) is a type of string
  server_ip = null
  # version - (optional) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "excluded_gateways" {
  description = "(optional) - List of excluded gateways."
  type        = set(string)
  default     = null
}

variable "port" {
  description = "(required) - Netflow server port."
  type        = number
}

variable "server_ip" {
  description = "(required) - Netflow server IP address."
  type        = string
}

variable "version" {
  description = "(optional) - Netflow version."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_netflow_agent" "this" {
  excluded_gateways = var.excluded_gateways
  port              = var.port
  server_ip         = var.server_ip
  version           = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_netflow_agent.this.id
}

output "status" {
  description = "returns a string"
  value       = aviatrix_netflow_agent.this.status
}

output "this" {
  value = aviatrix_netflow_agent.this
}
```

[top](#index)