# panos_panorama_gcp_account

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_gcp_account" {
  source = "./modules/panos/r/panos_panorama_gcp_account"

  # credential_file - (required) is a type of string
  credential_file = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
  # service_account_credential_type - (optional) is a type of string
  service_account_credential_type = null
}
```

[top](#index)

### Variables

```terraform
variable "credential_file" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "service_account_credential_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_gcp_account" "this" {
  credential_file                 = var.credential_file
  description                     = var.description
  name                            = var.name
  project_id                      = var.project_id
  service_account_credential_type = var.service_account_credential_type
}
```

[top](#index)

### Outputs

```terraform
output "credential_file_enc" {
  description = "returns a string"
  value       = panos_panorama_gcp_account.this.credential_file_enc
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = panos_panorama_gcp_account.this.id
}

output "this" {
  value = panos_panorama_gcp_account.this
}
```

[top](#index)