# tencentcloud_scf_namespaces

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
module "tencentcloud_scf_namespaces" {
  source = "./modules/tencentcloud/d/tencentcloud_scf_namespaces"

  # description - (optional) is a type of string
  description = null
  # namespace - (optional) is a type of string
  namespace = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the SCF namespace to be queried."
  type        = string
  default     = null
}

variable "namespace" {
  description = "(optional) - Name of the SCF namespace to be queried."
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
data "tencentcloud_scf_namespaces" "this" {
  description        = var.description
  namespace          = var.namespace
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_scf_namespaces.this.id
}

output "namespaces" {
  description = "returns a list of object"
  value       = data.tencentcloud_scf_namespaces.this.namespaces
}

output "this" {
  value = tencentcloud_scf_namespaces.this
}
```

[top](#index)