# tfe_oauth_client

[back](../tfe.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tfe = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tfe_oauth_client" {
  source = "./modules/tfe/r/tfe_oauth_client"

  # api_url - (required) is a type of string
  api_url = null
  # http_url - (required) is a type of string
  http_url = null
  # oauth_token - (required) is a type of string
  oauth_token = null
  # organization - (required) is a type of string
  organization = null
  # private_key - (optional) is a type of string
  private_key = null
  # service_provider - (required) is a type of string
  service_provider = null
}
```

[top](#index)

### Variables

```terraform
variable "api_url" {
  description = "(required)"
  type        = string
}

variable "http_url" {
  description = "(required)"
  type        = string
}

variable "oauth_token" {
  description = "(required)"
  type        = string
}

variable "organization" {
  description = "(required)"
  type        = string
}

variable "private_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_provider" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tfe_oauth_client" "this" {
  api_url          = var.api_url
  http_url         = var.http_url
  oauth_token      = var.oauth_token
  organization     = var.organization
  private_key      = var.private_key
  service_provider = var.service_provider
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_oauth_client.this.id
}

output "oauth_token_id" {
  description = "returns a string"
  value       = tfe_oauth_client.this.oauth_token_id
}

output "this" {
  value = tfe_oauth_client.this
}
```

[top](#index)