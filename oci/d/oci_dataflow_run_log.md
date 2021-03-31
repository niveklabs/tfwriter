# oci_dataflow_run_log

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dataflow_run_log" {
  source = "./modules/oci/d/oci_dataflow_run_log"

  # base64_encode_content - (optional) is a type of bool
  base64_encode_content = null
  # name - (required) is a type of string
  name = null
  # run_id - (required) is a type of string
  run_id = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "run_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_dataflow_run_log" "this" {
  base64_encode_content = var.base64_encode_content
  name                  = var.name
  run_id                = var.run_id
}
```

[top](#index)

### Outputs

```terraform
output "content" {
  description = "returns a string"
  value       = data.oci_dataflow_run_log.this.content
}

output "content_type" {
  description = "returns a string"
  value       = data.oci_dataflow_run_log.this.content_type
}

output "id" {
  description = "returns a string"
  value       = data.oci_dataflow_run_log.this.id
}

output "this" {
  value = oci_dataflow_run_log.this
}
```

[top](#index)