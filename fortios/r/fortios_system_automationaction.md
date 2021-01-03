# fortios_system_automationaction

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_automationaction" {
  source = "./modules/fortios/r/fortios_system_automationaction"

  # action_type - (optional) is a type of string
  action_type = null
  # aws_api_id - (optional) is a type of string
  aws_api_id = null
  # aws_api_key - (optional) is a type of string
  aws_api_key = null
  # aws_api_path - (optional) is a type of string
  aws_api_path = null
  # aws_api_stage - (optional) is a type of string
  aws_api_stage = null
  # aws_domain - (optional) is a type of string
  aws_domain = null
  # aws_region - (optional) is a type of string
  aws_region = null
  # delay - (optional) is a type of number
  delay = null
  # email_subject - (optional) is a type of string
  email_subject = null
  # http_body - (optional) is a type of string
  http_body = null
  # method - (optional) is a type of string
  method = null
  # minimum_interval - (optional) is a type of number
  minimum_interval = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # required - (optional) is a type of string
  required = null
  # security_tag - (optional) is a type of string
  security_tag = null
  # uri - (optional) is a type of string
  uri = null

  email_to = [{
    name = null
  }]

  headers = [{
    header = null
  }]

  sdn_connector = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aws_api_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aws_api_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aws_api_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aws_api_stage" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aws_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "aws_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "email_subject" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "minimum_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "required" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email_to" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "headers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      header = string
    }
  ))
  default = []
}

variable "sdn_connector" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_automationaction" "this" {
  action_type      = var.action_type
  aws_api_id       = var.aws_api_id
  aws_api_key      = var.aws_api_key
  aws_api_path     = var.aws_api_path
  aws_api_stage    = var.aws_api_stage
  aws_domain       = var.aws_domain
  aws_region       = var.aws_region
  delay            = var.delay
  email_subject    = var.email_subject
  http_body        = var.http_body
  method           = var.method
  minimum_interval = var.minimum_interval
  name             = var.name
  port             = var.port
  protocol         = var.protocol
  required         = var.required
  security_tag     = var.security_tag
  uri              = var.uri

  dynamic "email_to" {
    for_each = var.email_to
    content {
      name = email_to.value["name"]
    }
  }

  dynamic "headers" {
    for_each = var.headers
    content {
      header = headers.value["header"]
    }
  }

  dynamic "sdn_connector" {
    for_each = var.sdn_connector
    content {
      name = sdn_connector.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "action_type" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.action_type
}

output "aws_api_id" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.aws_api_id
}

output "aws_api_path" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.aws_api_path
}

output "aws_api_stage" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.aws_api_stage
}

output "aws_domain" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.aws_domain
}

output "aws_region" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.aws_region
}

output "delay" {
  description = "returns a number"
  value       = fortios_system_automationaction.this.delay
}

output "id" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.id
}

output "method" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.method
}

output "minimum_interval" {
  description = "returns a number"
  value       = fortios_system_automationaction.this.minimum_interval
}

output "name" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.name
}

output "port" {
  description = "returns a number"
  value       = fortios_system_automationaction.this.port
}

output "protocol" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.protocol
}

output "required" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.required
}

output "security_tag" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.security_tag
}

output "this" {
  value = fortios_system_automationaction.this
}
```

[top](#index)