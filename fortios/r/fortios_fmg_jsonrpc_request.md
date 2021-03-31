# fortios_fmg_jsonrpc_request

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
module "fortios_fmg_jsonrpc_request" {
  source = "./modules/fortios/r/fortios_fmg_jsonrpc_request"

  # comment - (optional) is a type of string
  comment = null
  # json_content - (required) is a type of string
  json_content = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "json_content" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_jsonrpc_request" "this" {
  comment      = var.comment
  json_content = var.json_content
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_jsonrpc_request.this.id
}

output "response" {
  description = "returns a string"
  value       = fortios_fmg_jsonrpc_request.this.response
}

output "this" {
  value = fortios_fmg_jsonrpc_request.this
}
```

[top](#index)