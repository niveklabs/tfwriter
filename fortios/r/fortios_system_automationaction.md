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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_automationaction" {
  source = "./modules/fortios/r/fortios_system_automationaction"

  # accprofile - (optional) is a type of string
  accprofile = null
  # action_type - (optional) is a type of string
  action_type = null
  # alicloud_access_key_id - (optional) is a type of string
  alicloud_access_key_id = null
  # alicloud_access_key_secret - (optional) is a type of string
  alicloud_access_key_secret = null
  # alicloud_account_id - (optional) is a type of string
  alicloud_account_id = null
  # alicloud_function - (optional) is a type of string
  alicloud_function = null
  # alicloud_function_authorization - (optional) is a type of string
  alicloud_function_authorization = null
  # alicloud_function_domain - (optional) is a type of string
  alicloud_function_domain = null
  # alicloud_region - (optional) is a type of string
  alicloud_region = null
  # alicloud_service - (optional) is a type of string
  alicloud_service = null
  # alicloud_version - (optional) is a type of string
  alicloud_version = null
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
  # azure_api_key - (optional) is a type of string
  azure_api_key = null
  # azure_app - (optional) is a type of string
  azure_app = null
  # azure_domain - (optional) is a type of string
  azure_domain = null
  # azure_function - (optional) is a type of string
  azure_function = null
  # azure_function_authorization - (optional) is a type of string
  azure_function_authorization = null
  # delay - (optional) is a type of number
  delay = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # email_body - (optional) is a type of string
  email_body = null
  # email_from - (optional) is a type of string
  email_from = null
  # email_subject - (optional) is a type of string
  email_subject = null
  # gcp_function - (optional) is a type of string
  gcp_function = null
  # gcp_function_domain - (optional) is a type of string
  gcp_function_domain = null
  # gcp_function_region - (optional) is a type of string
  gcp_function_region = null
  # gcp_project - (optional) is a type of string
  gcp_project = null
  # http_body - (optional) is a type of string
  http_body = null
  # message - (optional) is a type of string
  message = null
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
  # replacement_message - (optional) is a type of string
  replacement_message = null
  # required - (optional) is a type of string
  required = null
  # script - (optional) is a type of string
  script = null
  # security_tag - (optional) is a type of string
  security_tag = null
  # tls_certificate - (optional) is a type of string
  tls_certificate = null
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
variable "accprofile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "action_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_access_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_access_key_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_function" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_function_authorization" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_function_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alicloud_version" {
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

variable "azure_api_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "azure_app" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "azure_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "azure_function" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "azure_function_authorization" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email_from" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email_subject" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gcp_function" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gcp_function_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gcp_function_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gcp_project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "message" {
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

variable "replacement_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "required" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "script" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tls_certificate" {
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
  # accprofile - (optional) is a type of string
  accprofile = var.accprofile
  # action_type - (optional) is a type of string
  action_type = var.action_type
  # alicloud_access_key_id - (optional) is a type of string
  alicloud_access_key_id = var.alicloud_access_key_id
  # alicloud_access_key_secret - (optional) is a type of string
  alicloud_access_key_secret = var.alicloud_access_key_secret
  # alicloud_account_id - (optional) is a type of string
  alicloud_account_id = var.alicloud_account_id
  # alicloud_function - (optional) is a type of string
  alicloud_function = var.alicloud_function
  # alicloud_function_authorization - (optional) is a type of string
  alicloud_function_authorization = var.alicloud_function_authorization
  # alicloud_function_domain - (optional) is a type of string
  alicloud_function_domain = var.alicloud_function_domain
  # alicloud_region - (optional) is a type of string
  alicloud_region = var.alicloud_region
  # alicloud_service - (optional) is a type of string
  alicloud_service = var.alicloud_service
  # alicloud_version - (optional) is a type of string
  alicloud_version = var.alicloud_version
  # aws_api_id - (optional) is a type of string
  aws_api_id = var.aws_api_id
  # aws_api_key - (optional) is a type of string
  aws_api_key = var.aws_api_key
  # aws_api_path - (optional) is a type of string
  aws_api_path = var.aws_api_path
  # aws_api_stage - (optional) is a type of string
  aws_api_stage = var.aws_api_stage
  # aws_domain - (optional) is a type of string
  aws_domain = var.aws_domain
  # aws_region - (optional) is a type of string
  aws_region = var.aws_region
  # azure_api_key - (optional) is a type of string
  azure_api_key = var.azure_api_key
  # azure_app - (optional) is a type of string
  azure_app = var.azure_app
  # azure_domain - (optional) is a type of string
  azure_domain = var.azure_domain
  # azure_function - (optional) is a type of string
  azure_function = var.azure_function
  # azure_function_authorization - (optional) is a type of string
  azure_function_authorization = var.azure_function_authorization
  # delay - (optional) is a type of number
  delay = var.delay
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # email_body - (optional) is a type of string
  email_body = var.email_body
  # email_from - (optional) is a type of string
  email_from = var.email_from
  # email_subject - (optional) is a type of string
  email_subject = var.email_subject
  # gcp_function - (optional) is a type of string
  gcp_function = var.gcp_function
  # gcp_function_domain - (optional) is a type of string
  gcp_function_domain = var.gcp_function_domain
  # gcp_function_region - (optional) is a type of string
  gcp_function_region = var.gcp_function_region
  # gcp_project - (optional) is a type of string
  gcp_project = var.gcp_project
  # http_body - (optional) is a type of string
  http_body = var.http_body
  # message - (optional) is a type of string
  message = var.message
  # method - (optional) is a type of string
  method = var.method
  # minimum_interval - (optional) is a type of number
  minimum_interval = var.minimum_interval
  # name - (optional) is a type of string
  name = var.name
  # port - (optional) is a type of number
  port = var.port
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # replacement_message - (optional) is a type of string
  replacement_message = var.replacement_message
  # required - (optional) is a type of string
  required = var.required
  # script - (optional) is a type of string
  script = var.script
  # security_tag - (optional) is a type of string
  security_tag = var.security_tag
  # tls_certificate - (optional) is a type of string
  tls_certificate = var.tls_certificate
  # uri - (optional) is a type of string
  uri = var.uri

  dynamic "email_to" {
    for_each = var.email_to
    content {
      # name - (optional) is a type of string
      name = email_to.value["name"]
    }
  }

  dynamic "headers" {
    for_each = var.headers
    content {
      # header - (optional) is a type of string
      header = headers.value["header"]
    }
  }

  dynamic "sdn_connector" {
    for_each = var.sdn_connector
    content {
      # name - (optional) is a type of string
      name = sdn_connector.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "accprofile" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.accprofile
}

output "action_type" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.action_type
}

output "alicloud_access_key_id" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.alicloud_access_key_id
}

output "alicloud_account_id" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.alicloud_account_id
}

output "alicloud_function" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.alicloud_function
}

output "alicloud_function_authorization" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.alicloud_function_authorization
}

output "alicloud_function_domain" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.alicloud_function_domain
}

output "alicloud_region" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.alicloud_region
}

output "alicloud_service" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.alicloud_service
}

output "alicloud_version" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.alicloud_version
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

output "azure_app" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.azure_app
}

output "azure_domain" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.azure_domain
}

output "azure_function" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.azure_function
}

output "azure_function_authorization" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.azure_function_authorization
}

output "delay" {
  description = "returns a number"
  value       = fortios_system_automationaction.this.delay
}

output "email_body" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.email_body
}

output "gcp_function" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.gcp_function
}

output "gcp_function_domain" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.gcp_function_domain
}

output "gcp_function_region" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.gcp_function_region
}

output "gcp_project" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.gcp_project
}

output "id" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.id
}

output "message" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.message
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

output "replacement_message" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.replacement_message
}

output "required" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.required
}

output "security_tag" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.security_tag
}

output "tls_certificate" {
  description = "returns a string"
  value       = fortios_system_automationaction.this.tls_certificate
}

output "this" {
  value = fortios_system_automationaction.this
}
```

[top](#index)