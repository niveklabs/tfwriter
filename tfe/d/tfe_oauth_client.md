# tfe_oauth_client

[back](../tfe.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tfe = ">= 0.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tfe_oauth_client" {
  source = "./modules/tfe/d/tfe_oauth_client"

  # oauth_client_id - (required) is a type of string
  oauth_client_id = null
}
```

[top](#index)

### Variables

```terraform
variable "oauth_client_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tfe_oauth_client" "this" {
  # oauth_client_id - (required) is a type of string
  oauth_client_id = var.oauth_client_id
}
```

[top](#index)

### Outputs

```terraform
output "api_url" {
  description = "returns a string"
  value       = data.tfe_oauth_client.this.api_url
}

output "http_url" {
  description = "returns a string"
  value       = data.tfe_oauth_client.this.http_url
}

output "id" {
  description = "returns a string"
  value       = data.tfe_oauth_client.this.id
}

output "oauth_token_id" {
  description = "returns a string"
  value       = data.tfe_oauth_client.this.oauth_token_id
}

output "this" {
  value = tfe_oauth_client.this
}
```

[top](#index)