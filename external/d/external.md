# external

[back](../external.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    external = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "external" {
  source = "./modules/external/d/external"

  # program - (required) is a type of list of string
  program = []
  # query - (optional) is a type of map of string
  query = {}
  # working_dir - (optional) is a type of string
  working_dir = null
}
```

[top](#index)

### Variables

```terraform
variable "program" {
  description = "(required) - A list of strings, whose first element is the program to run and whose subsequent elements are optional command line arguments to the program. Terraform does not execute the program through a shell, so it is not necessary to escape shell metacharacters nor add quotes around arguments containing spaces."
  type        = list(string)
}

variable "query" {
  description = "(optional) - A map of string values to pass to the external program as the query arguments. If not supplied, the program will receive an empty object as its input."
  type        = map(string)
  default     = null
}

variable "working_dir" {
  description = "(optional) - Working directory of the program. If not supplied, the program will run in the current directory."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "external" "this" {
  program     = var.program
  query       = var.query
  working_dir = var.working_dir
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.external.this.id
}

output "result" {
  description = "returns a map of string"
  value       = data.external.this.result
}

output "this" {
  value = external.this
}
```

[top](#index)