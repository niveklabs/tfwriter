# aws_api_gateway_documentation_part

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_api_gateway_documentation_part" {
  source = "./modules/aws/r/aws_api_gateway_documentation_part"

  # properties - (required) is a type of string
  properties = null
  # rest_api_id - (required) is a type of string
  rest_api_id = null

  location = [{
    method      = null
    name        = null
    path        = null
    status_code = null
    type        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "properties" {
  description = "(required)"
  type        = string
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      method      = string
      name        = string
      path        = string
      status_code = string
      type        = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_documentation_part" "this" {
  # properties - (required) is a type of string
  properties = var.properties
  # rest_api_id - (required) is a type of string
  rest_api_id = var.rest_api_id

  dynamic "location" {
    for_each = var.location
    content {
      # method - (optional) is a type of string
      method = location.value["method"]
      # name - (optional) is a type of string
      name = location.value["name"]
      # path - (optional) is a type of string
      path = location.value["path"]
      # status_code - (optional) is a type of string
      status_code = location.value["status_code"]
      # type - (required) is a type of string
      type = location.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_documentation_part.this.id
}

output "this" {
  value = aws_api_gateway_documentation_part.this
}
```

[top](#index)