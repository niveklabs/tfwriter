# tencentcloud_tcr_namespaces

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_tcr_namespaces" {
  source = "./modules/tencentcloud/d/tencentcloud_tcr_namespaces"

  # instance_id - (required) is a type of string
  instance_id = null
  # namespace_name - (optional) is a type of string
  namespace_name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required) - ID of the instance that the namespace belongs to."
  type        = string
}

variable "namespace_name" {
  description = "(optional) - ID of the TCR namespace to query."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_tcr_namespaces" "this" {
  instance_id        = var.instance_id
  namespace_name     = var.namespace_name
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_tcr_namespaces.this.id
}

output "namespace_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_tcr_namespaces.this.namespace_list
}

output "this" {
  value = tencentcloud_tcr_namespaces.this
}
```

[top](#index)