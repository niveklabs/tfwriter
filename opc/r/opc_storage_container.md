# opc_storage_container

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_storage_container" {
  source = "./modules/opc/r/opc_storage_container"

  # allowed_origins - (optional) is a type of list of string
  allowed_origins = []
  # exposed_headers - (optional) is a type of list of string
  exposed_headers = []
  # max_age - (optional) is a type of number
  max_age = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # primary_key - (optional) is a type of string
  primary_key = null
  # quota_bytes - (optional) is a type of number
  quota_bytes = null
  # quota_count - (optional) is a type of number
  quota_count = null
  # read_acls - (optional) is a type of list of string
  read_acls = []
  # secondary_key - (optional) is a type of string
  secondary_key = null
  # write_acls - (optional) is a type of list of string
  write_acls = []
}
```

[top](#index)

### Variables

```terraform
variable "allowed_origins" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "exposed_headers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "max_age" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "primary_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "quota_bytes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "quota_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "read_acls" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "secondary_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "write_acls" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "opc_storage_container" "this" {
  allowed_origins = var.allowed_origins
  exposed_headers = var.exposed_headers
  max_age         = var.max_age
  metadata        = var.metadata
  name            = var.name
  primary_key     = var.primary_key
  quota_bytes     = var.quota_bytes
  quota_count     = var.quota_count
  read_acls       = var.read_acls
  secondary_key   = var.secondary_key
  write_acls      = var.write_acls
}
```

[top](#index)

### Outputs

```terraform
output "allowed_origins" {
  description = "returns a list of string"
  value       = opc_storage_container.this.allowed_origins
}

output "exposed_headers" {
  description = "returns a list of string"
  value       = opc_storage_container.this.exposed_headers
}

output "id" {
  description = "returns a string"
  value       = opc_storage_container.this.id
}

output "read_acls" {
  description = "returns a list of string"
  value       = opc_storage_container.this.read_acls
}

output "write_acls" {
  description = "returns a list of string"
  value       = opc_storage_container.this.write_acls
}

output "this" {
  value = opc_storage_container.this
}
```

[top](#index)