# mongodbatlas_third_party_integration

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/mongodbatlas/r/mongodbatlas_third_party_integration"

  # account_id - (optional) is a type of string
  account_id = null
  # api_key - (optional) is a type of string
  api_key = null
  # api_token - (optional) is a type of string
  api_token = null
  # channel_name - (optional) is a type of string
  channel_name = null
  # flow_name - (optional) is a type of string
  flow_name = null
  # license_key - (optional) is a type of string
  license_key = null
  # org_name - (optional) is a type of string
  org_name = null
  # project_id - (required) is a type of string
  project_id = null
  # read_token - (optional) is a type of string
  read_token = null
  # region - (optional) is a type of string
  region = null
  # routing_key - (optional) is a type of string
  routing_key = null
  # secret - (optional) is a type of string
  secret = null
  # service_key - (optional) is a type of string
  service_key = null
  # team_name - (optional) is a type of string
  team_name = null
  # type - (required) is a type of string
  type = null
  # url - (optional) is a type of string
  url = null
  # write_token - (optional) is a type of string
  write_token = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "api_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "api_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "channel_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flow_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "license_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "org_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "read_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "routing_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "team_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "write_token" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_third_party_integration" "this" {
  # account_id - (optional) is a type of string
  account_id = var.account_id
  # api_key - (optional) is a type of string
  api_key = var.api_key
  # api_token - (optional) is a type of string
  api_token = var.api_token
  # channel_name - (optional) is a type of string
  channel_name = var.channel_name
  # flow_name - (optional) is a type of string
  flow_name = var.flow_name
  # license_key - (optional) is a type of string
  license_key = var.license_key
  # org_name - (optional) is a type of string
  org_name = var.org_name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # read_token - (optional) is a type of string
  read_token = var.read_token
  # region - (optional) is a type of string
  region = var.region
  # routing_key - (optional) is a type of string
  routing_key = var.routing_key
  # secret - (optional) is a type of string
  secret = var.secret
  # service_key - (optional) is a type of string
  service_key = var.service_key
  # team_name - (optional) is a type of string
  team_name = var.team_name
  # type - (required) is a type of string
  type = var.type
  # url - (optional) is a type of string
  url = var.url
  # write_token - (optional) is a type of string
  write_token = var.write_token
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mongodbatlas_third_party_integration.this.id
}

output "this" {
  value = mongodbatlas_third_party_integration.this
}
```

[top](#index)