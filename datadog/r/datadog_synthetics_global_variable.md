# datadog_synthetics_global_variable

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_synthetics_global_variable" {
  source = "./modules/datadog/r/datadog_synthetics_global_variable"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # parse_test_id - (optional) is a type of string
  parse_test_id = null
  # secure - (optional) is a type of bool
  secure = null
  # tags - (optional) is a type of list of string
  tags = []
  # value - (required) is a type of string
  value = null

  parse_test_options = [{
    field = null
    parser = [{
      type  = null
      value = null
    }]
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the global variable."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Synthetics global variable name."
  type        = string
}

variable "parse_test_id" {
  description = "(optional) - Id of the Synthetics test to use for a variable from test."
  type        = string
  default     = null
}

variable "secure" {
  description = "(optional) - Sets the variable as secure. Defaults to `false`."
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional) - A list of tags to associate with your synthetics global variable."
  type        = list(string)
  default     = null
}

variable "value" {
  description = "(required) - The value of the global variable."
  type        = string
}

variable "parse_test_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      field = string
      parser = list(object(
        {
          type  = string
          value = string
        }
      ))
      type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "datadog_synthetics_global_variable" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # parse_test_id - (optional) is a type of string
  parse_test_id = var.parse_test_id
  # secure - (optional) is a type of bool
  secure = var.secure
  # tags - (optional) is a type of list of string
  tags = var.tags
  # value - (required) is a type of string
  value = var.value

  dynamic "parse_test_options" {
    for_each = var.parse_test_options
    content {
      # field - (optional) is a type of string
      field = parse_test_options.value["field"]
      # type - (required) is a type of string
      type = parse_test_options.value["type"]

      dynamic "parser" {
        for_each = parse_test_options.value.parser
        content {
          # type - (required) is a type of string
          type = parser.value["type"]
          # value - (optional) is a type of string
          value = parser.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_synthetics_global_variable.this.id
}

output "this" {
  value = datadog_synthetics_global_variable.this
}
```

[top](#index)