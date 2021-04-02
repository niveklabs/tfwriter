# aws_glue_script

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_glue_script" {
  source = "./modules/aws/d/aws_glue_script"

  # language - (optional) is a type of string
  language = null

  dag_edge = [{
    source           = null
    target           = null
    target_parameter = null
  }]

  dag_node = [{
    args = [{
      name  = null
      param = null
      value = null
    }]
    id          = null
    line_number = null
    node_type   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "language" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dag_edge" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      source           = string
      target           = string
      target_parameter = string
    }
  ))
}

variable "dag_node" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      args = list(object(
        {
          name  = string
          param = bool
          value = string
        }
      ))
      id          = string
      line_number = number
      node_type   = string
    }
  ))
}
```

[top](#index)

### Datasource

```terraform
data "aws_glue_script" "this" {
  language = var.language

  dynamic "dag_edge" {
    for_each = var.dag_edge
    content {
      source           = dag_edge.value["source"]
      target           = dag_edge.value["target"]
      target_parameter = dag_edge.value["target_parameter"]
    }
  }

  dynamic "dag_node" {
    for_each = var.dag_node
    content {
      id          = dag_node.value["id"]
      line_number = dag_node.value["line_number"]
      node_type   = dag_node.value["node_type"]

      dynamic "args" {
        for_each = dag_node.value.args
        content {
          name  = args.value["name"]
          param = args.value["param"]
          value = args.value["value"]
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
  value       = data.aws_glue_script.this.id
}

output "python_script" {
  description = "returns a string"
  value       = data.aws_glue_script.this.python_script
}

output "scala_code" {
  description = "returns a string"
  value       = data.aws_glue_script.this.scala_code
}

output "this" {
  value = aws_glue_script.this
}
```

[top](#index)