# sumologic_personal_folder

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_personal_folder" {
  source = "./modules/sumologic/d/sumologic_personal_folder"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "sumologic_personal_folder" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.sumologic_personal_folder.this.description
}

output "id" {
  description = "returns a string"
  value       = data.sumologic_personal_folder.this.id
}

output "name" {
  description = "returns a string"
  value       = data.sumologic_personal_folder.this.name
}

output "this" {
  value = sumologic_personal_folder.this
}
```

[top](#index)