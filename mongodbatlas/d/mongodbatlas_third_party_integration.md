# mongodbatlas_third_party_integration

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mongodbatlas = ">= 0.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_third_party_integration" {
  source = "./modules/mongodbatlas/d/mongodbatlas_third_party_integration"

  # project_id - (required) is a type of string
  project_id = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required) - Third-party service integration identifier"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_third_party_integration" "this" {
  # project_id - (required) is a type of string
  project_id = var.project_id
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.account_id
}

output "api_key" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.api_key
  sensitive   = true
}

output "api_token" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.api_token
  sensitive   = true
}

output "channel_name" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.channel_name
}

output "flow_name" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.flow_name
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.id
}

output "license_key" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.license_key
  sensitive   = true
}

output "org_name" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.org_name
}

output "read_token" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.read_token
  sensitive   = true
}

output "region" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.region
}

output "routing_key" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.routing_key
  sensitive   = true
}

output "secret" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.secret
  sensitive   = true
}

output "service_key" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.service_key
  sensitive   = true
}

output "team_name" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.team_name
}

output "url" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.url
}

output "write_token" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integration.this.write_token
  sensitive   = true
}

output "this" {
  value = mongodbatlas_third_party_integration.this
}
```

[top](#index)