# aviatrix_splunk_logging

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
module "aviatrix_splunk_logging" {
  source = "./modules/aviatrix/r/aviatrix_splunk_logging"

  # custom_input_config - (optional) is a type of string
  custom_input_config = null
  # custom_output_config_file - (optional) is a type of string
  custom_output_config_file = null
  # excluded_gateways - (optional) is a type of set of string
  excluded_gateways = []
  # port - (optional) is a type of number
  port = null
  # server - (optional) is a type of string
  server = null
}
```

[top](#index)

### Variables

```terraform
variable "custom_input_config" {
  description = "(optional) - Custom configuration."
  type        = string
  default     = null
}

variable "custom_output_config_file" {
  description = "(optional) - Configuration file. Use the filebase64 function to read from a file."
  type        = string
  default     = null
}

variable "excluded_gateways" {
  description = "(optional) - List of excluded gateways."
  type        = set(string)
  default     = null
}

variable "port" {
  description = "(optional) - Port number."
  type        = number
  default     = null
}

variable "server" {
  description = "(optional) - Server IP."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_splunk_logging" "this" {
  custom_input_config       = var.custom_input_config
  custom_output_config_file = var.custom_output_config_file
  excluded_gateways         = var.excluded_gateways
  port                      = var.port
  server                    = var.server
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_splunk_logging.this.id
}

output "status" {
  description = "returns a string"
  value       = aviatrix_splunk_logging.this.status
}

output "this" {
  value = aviatrix_splunk_logging.this
}
```

[top](#index)