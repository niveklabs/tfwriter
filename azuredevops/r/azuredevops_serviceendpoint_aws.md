# azuredevops_serviceendpoint_aws

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuredevops = ">= 0.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_serviceendpoint_aws" {
  source = "./modules/azuredevops/r/azuredevops_serviceendpoint_aws"

  # access_key_id - (required) is a type of string
  access_key_id = null
  # authorization - (optional) is a type of map of string
  authorization = {}
  # description - (optional) is a type of string
  description = null
  # external_id - (optional) is a type of string
  external_id = null
  # project_id - (required) is a type of string
  project_id = null
  # role_session_name - (optional) is a type of string
  role_session_name = null
  # role_to_assume - (optional) is a type of string
  role_to_assume = null
  # secret_access_key - (required) is a type of string
  secret_access_key = null
  # service_endpoint_name - (required) is a type of string
  service_endpoint_name = null
  # session_token - (optional) is a type of string
  session_token = null
}
```

[top](#index)

### Variables

```terraform
variable "access_key_id" {
  description = "(required) - The AWS access key ID for signing programmatic requests."
  type        = string
}

variable "authorization" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_id" {
  description = "(optional) - A unique identifier that is used by third parties when assuming roles in their customers' accounts, aka cross-account role access."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "role_session_name" {
  description = "(optional) - Optional identifier for the assumed role session."
  type        = string
  default     = null
}

variable "role_to_assume" {
  description = "(optional) - The Amazon Resource Name (ARN) of the role to assume."
  type        = string
  default     = null
}

variable "secret_access_key" {
  description = "(required) - The AWS secret access key for signing programmatic requests."
  type        = string
}

variable "service_endpoint_name" {
  description = "(required)"
  type        = string
}

variable "session_token" {
  description = "(optional) - The AWS session token for signing programmatic requests."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_serviceendpoint_aws" "this" {
  access_key_id         = var.access_key_id
  authorization         = var.authorization
  description           = var.description
  external_id           = var.external_id
  project_id            = var.project_id
  role_session_name     = var.role_session_name
  role_to_assume        = var.role_to_assume
  secret_access_key     = var.secret_access_key
  service_endpoint_name = var.service_endpoint_name
  session_token         = var.session_token
}
```

[top](#index)

### Outputs

```terraform
output "authorization" {
  description = "returns a map of string"
  value       = azuredevops_serviceendpoint_aws.this.authorization
}

output "id" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_aws.this.id
}

output "secret_access_key_hash" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_aws.this.secret_access_key_hash
  sensitive   = true
}

output "session_token_hash" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_aws.this.session_token_hash
  sensitive   = true
}

output "this" {
  value = azuredevops_serviceendpoint_aws.this
}
```

[top](#index)