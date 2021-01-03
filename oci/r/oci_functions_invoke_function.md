# oci_functions_invoke_function

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_functions_invoke_function" {
  source = "./modules/oci/r/oci_functions_invoke_function"

  # base64_encode_content - (optional) is a type of bool
  base64_encode_content = null
  # fn_intent - (optional) is a type of string
  fn_intent = null
  # fn_invoke_type - (optional) is a type of string
  fn_invoke_type = null
  # function_id - (required) is a type of string
  function_id = null
  # input_body_source_path - (optional) is a type of string
  input_body_source_path = null
  # invoke_function_body - (optional) is a type of string
  invoke_function_body = null
  # invoke_function_body_base64_encoded - (optional) is a type of string
  invoke_function_body_base64_encoded = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "base64_encode_content" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "fn_intent" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fn_invoke_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "function_id" {
  description = "(required)"
  type        = string
}

variable "input_body_source_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "invoke_function_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "invoke_function_body_base64_encoded" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_functions_invoke_function" "this" {
  base64_encode_content               = var.base64_encode_content
  fn_intent                           = var.fn_intent
  fn_invoke_type                      = var.fn_invoke_type
  function_id                         = var.function_id
  input_body_source_path              = var.input_body_source_path
  invoke_function_body                = var.invoke_function_body
  invoke_function_body_base64_encoded = var.invoke_function_body_base64_encoded

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "content" {
  description = "returns a string"
  value       = oci_functions_invoke_function.this.content
}

output "fn_intent" {
  description = "returns a string"
  value       = oci_functions_invoke_function.this.fn_intent
}

output "fn_invoke_type" {
  description = "returns a string"
  value       = oci_functions_invoke_function.this.fn_invoke_type
}

output "id" {
  description = "returns a string"
  value       = oci_functions_invoke_function.this.id
}

output "invoke_endpoint" {
  description = "returns a string"
  value       = oci_functions_invoke_function.this.invoke_endpoint
}

output "invoke_function_body" {
  description = "returns a string"
  value       = oci_functions_invoke_function.this.invoke_function_body
}

output "invoke_function_body_base64_encoded" {
  description = "returns a string"
  value       = oci_functions_invoke_function.this.invoke_function_body_base64_encoded
}

output "this" {
  value = oci_functions_invoke_function.this
}
```

[top](#index)