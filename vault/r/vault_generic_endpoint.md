# vault_generic_endpoint

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_generic_endpoint" {
  source = "./modules/vault/r/vault_generic_endpoint"

  # data_json - (required) is a type of string
  data_json = null
  # disable_delete - (optional) is a type of bool
  disable_delete = null
  # disable_read - (optional) is a type of bool
  disable_read = null
  # ignore_absent_fields - (optional) is a type of bool
  ignore_absent_fields = null
  # path - (required) is a type of string
  path = null
  # write_fields - (optional) is a type of list of string
  write_fields = []
}
```

[top](#index)

### Variables

```terraform
variable "data_json" {
  description = "(required) - JSON-encoded data to write."
  type        = string
}

variable "disable_delete" {
  description = "(optional) - Don't attempt to delete the path from Vault if true"
  type        = bool
  default     = null
}

variable "disable_read" {
  description = "(optional) - Don't attempt to read the path from Vault if true; drift won't be detected"
  type        = bool
  default     = null
}

variable "ignore_absent_fields" {
  description = "(optional) - When reading, disregard fields not present in data_json"
  type        = bool
  default     = null
}

variable "path" {
  description = "(required) - Full path where to the endpoint that will be written"
  type        = string
}

variable "write_fields" {
  description = "(optional) - Top-level fields returned by write to persist in state"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_generic_endpoint" "this" {
  # data_json - (required) is a type of string
  data_json = var.data_json
  # disable_delete - (optional) is a type of bool
  disable_delete = var.disable_delete
  # disable_read - (optional) is a type of bool
  disable_read = var.disable_read
  # ignore_absent_fields - (optional) is a type of bool
  ignore_absent_fields = var.ignore_absent_fields
  # path - (required) is a type of string
  path = var.path
  # write_fields - (optional) is a type of list of string
  write_fields = var.write_fields
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_generic_endpoint.this.id
}

output "write_data" {
  description = "returns a map of string"
  value       = vault_generic_endpoint.this.write_data
}

output "write_data_json" {
  description = "returns a string"
  value       = vault_generic_endpoint.this.write_data_json
}

output "this" {
  value = vault_generic_endpoint.this
}
```

[top](#index)