# fortios_system_automationaction

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/fortios/d/fortios_system_automationaction"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_automationaction" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "accprofile" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.accprofile
}

output "action_type" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.action_type
}

output "alicloud_access_key_id" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.alicloud_access_key_id
}

output "alicloud_access_key_secret" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.alicloud_access_key_secret
  sensitive   = true
}

output "alicloud_account_id" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.alicloud_account_id
}

output "alicloud_function" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.alicloud_function
}

output "alicloud_function_authorization" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.alicloud_function_authorization
}

output "alicloud_function_domain" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.alicloud_function_domain
}

output "alicloud_region" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.alicloud_region
}

output "alicloud_service" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.alicloud_service
}

output "alicloud_version" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.alicloud_version
}

output "aws_api_id" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.aws_api_id
}

output "aws_api_key" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.aws_api_key
  sensitive   = true
}

output "aws_api_path" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.aws_api_path
}

output "aws_api_stage" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.aws_api_stage
}

output "aws_domain" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.aws_domain
}

output "aws_region" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.aws_region
}

output "azure_api_key" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.azure_api_key
  sensitive   = true
}

output "azure_app" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.azure_app
}

output "azure_domain" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.azure_domain
}

output "azure_function" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.azure_function
}

output "azure_function_authorization" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.azure_function_authorization
}

output "delay" {
  description = "returns a number"
  value       = data.fortios_system_automationaction.this.delay
}

output "email_body" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.email_body
}

output "email_from" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.email_from
}

output "email_subject" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.email_subject
}

output "email_to" {
  description = "returns a list of object"
  value       = data.fortios_system_automationaction.this.email_to
}

output "gcp_function" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.gcp_function
}

output "gcp_function_domain" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.gcp_function_domain
}

output "gcp_function_region" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.gcp_function_region
}

output "gcp_project" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.gcp_project
}

output "headers" {
  description = "returns a list of object"
  value       = data.fortios_system_automationaction.this.headers
}

output "http_body" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.http_body
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.id
}

output "message" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.message
}

output "method" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.method
}

output "minimum_interval" {
  description = "returns a number"
  value       = data.fortios_system_automationaction.this.minimum_interval
}

output "port" {
  description = "returns a number"
  value       = data.fortios_system_automationaction.this.port
}

output "protocol" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.protocol
}

output "replacement_message" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.replacement_message
}

output "required" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.required
}

output "script" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.script
}

output "sdn_connector" {
  description = "returns a list of object"
  value       = data.fortios_system_automationaction.this.sdn_connector
}

output "security_tag" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.security_tag
}

output "tls_certificate" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.tls_certificate
}

output "uri" {
  description = "returns a string"
  value       = data.fortios_system_automationaction.this.uri
}

output "this" {
  value = fortios_system_automationaction.this
}
```

[top](#index)