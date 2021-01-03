# bigip_do

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_do" {
  source = "./modules/bigip/r/bigip_do"

  # do_json - (required) is a type of string
  do_json = null
  # tenant_name - (optional) is a type of string
  tenant_name = null
  # timeout - (optional) is a type of number
  timeout = null
}
```

[top](#index)

### Variables

```terraform
variable "do_json" {
  description = "(required) - DO json"
  type        = string
}

variable "tenant_name" {
  description = "(optional) - unique identifier for DO resource"
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional) - DO json"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_do" "this" {
  do_json     = var.do_json
  tenant_name = var.tenant_name
  timeout     = var.timeout
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_do.this.id
}

output "this" {
  value = bigip_do.this
}
```

[top](#index)