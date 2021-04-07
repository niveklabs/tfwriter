# tencentcloud_scf_functions

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
module "tencentcloud_scf_functions" {
  source = "./modules/tencentcloud/d/tencentcloud_scf_functions"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the SCF function to be queried."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the SCF function to be queried."
  type        = string
  default     = null
}

variable "namespace" {
  description = "(optional) - Namespace of the SCF function to be queried."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags of the SCF function to be queried, can use up to 10 tags."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_scf_functions" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # namespace - (optional) is a type of string
  namespace = var.namespace
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "functions" {
  description = "returns a list of object"
  value       = data.tencentcloud_scf_functions.this.functions
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_scf_functions.this.id
}

output "this" {
  value = tencentcloud_scf_functions.this
}
```

[top](#index)