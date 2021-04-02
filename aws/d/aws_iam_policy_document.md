# aws_iam_policy_document

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
module "aws_iam_policy_document" {
  source = "./modules/aws/d/aws_iam_policy_document"

  # override_json - (optional) is a type of string
  override_json = null
  # override_policy_documents - (optional) is a type of list of string
  override_policy_documents = []
  # policy_id - (optional) is a type of string
  policy_id = null
  # source_json - (optional) is a type of string
  source_json = null
  # source_policy_documents - (optional) is a type of list of string
  source_policy_documents = []
  # version - (optional) is a type of string
  version = null

  statement = [{
    actions = []
    condition = [{
      test     = null
      values   = []
      variable = null
    }]
    effect      = null
    not_actions = []
    not_principals = [{
      identifiers = []
      type        = null
    }]
    not_resources = []
    principals = [{
      identifiers = []
      type        = null
    }]
    resources = []
    sid       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "override_json" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_policy_documents" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "policy_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_json" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_policy_documents" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "statement" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      actions = set(string)
      condition = set(object(
        {
          test     = string
          values   = list(string)
          variable = string
        }
      ))
      effect      = string
      not_actions = set(string)
      not_principals = set(object(
        {
          identifiers = set(string)
          type        = string
        }
      ))
      not_resources = set(string)
      principals = set(object(
        {
          identifiers = set(string)
          type        = string
        }
      ))
      resources = set(string)
      sid       = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_iam_policy_document" "this" {
  override_json             = var.override_json
  override_policy_documents = var.override_policy_documents
  policy_id                 = var.policy_id
  source_json               = var.source_json
  source_policy_documents   = var.source_policy_documents
  version                   = var.version

  dynamic "statement" {
    for_each = var.statement
    content {
      actions       = statement.value["actions"]
      effect        = statement.value["effect"]
      not_actions   = statement.value["not_actions"]
      not_resources = statement.value["not_resources"]
      resources     = statement.value["resources"]
      sid           = statement.value["sid"]

      dynamic "condition" {
        for_each = statement.value.condition
        content {
          test     = condition.value["test"]
          values   = condition.value["values"]
          variable = condition.value["variable"]
        }
      }

      dynamic "not_principals" {
        for_each = statement.value.not_principals
        content {
          identifiers = not_principals.value["identifiers"]
          type        = not_principals.value["type"]
        }
      }

      dynamic "principals" {
        for_each = statement.value.principals
        content {
          identifiers = principals.value["identifiers"]
          type        = principals.value["type"]
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
  value       = data.aws_iam_policy_document.this.id
}

output "json" {
  description = "returns a string"
  value       = data.aws_iam_policy_document.this.json
}

output "this" {
  value = aws_iam_policy_document.this
}
```

[top](#index)