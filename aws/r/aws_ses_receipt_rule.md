# aws_ses_receipt_rule

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ses_receipt_rule" {
  source = "./modules/aws/r/aws_ses_receipt_rule"

  # after - (optional) is a type of string
  after = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # recipients - (optional) is a type of set of string
  recipients = []
  # rule_set_name - (required) is a type of string
  rule_set_name = null
  # scan_enabled - (optional) is a type of bool
  scan_enabled = null
  # tls_policy - (optional) is a type of string
  tls_policy = null

  add_header_action = [{
    header_name  = null
    header_value = null
    position     = null
  }]

  bounce_action = [{
    message         = null
    position        = null
    sender          = null
    smtp_reply_code = null
    status_code     = null
    topic_arn       = null
  }]

  lambda_action = [{
    function_arn    = null
    invocation_type = null
    position        = null
    topic_arn       = null
  }]

  s3_action = [{
    bucket_name       = null
    kms_key_arn       = null
    object_key_prefix = null
    position          = null
    topic_arn         = null
  }]

  sns_action = [{
    position  = null
    topic_arn = null
  }]

  stop_action = [{
    position  = null
    scope     = null
    topic_arn = null
  }]

  workmail_action = [{
    organization_arn = null
    position         = null
    topic_arn        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "after" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "recipients" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "rule_set_name" {
  description = "(required)"
  type        = string
}

variable "scan_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tls_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "add_header_action" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      header_name  = string
      header_value = string
      position     = number
    }
  ))
  default = []
}

variable "bounce_action" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      message         = string
      position        = number
      sender          = string
      smtp_reply_code = string
      status_code     = string
      topic_arn       = string
    }
  ))
  default = []
}

variable "lambda_action" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      function_arn    = string
      invocation_type = string
      position        = number
      topic_arn       = string
    }
  ))
  default = []
}

variable "s3_action" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bucket_name       = string
      kms_key_arn       = string
      object_key_prefix = string
      position          = number
      topic_arn         = string
    }
  ))
  default = []
}

variable "sns_action" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      position  = number
      topic_arn = string
    }
  ))
  default = []
}

variable "stop_action" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      position  = number
      scope     = string
      topic_arn = string
    }
  ))
  default = []
}

variable "workmail_action" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      organization_arn = string
      position         = number
      topic_arn        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_ses_receipt_rule" "this" {
  after         = var.after
  enabled       = var.enabled
  name          = var.name
  recipients    = var.recipients
  rule_set_name = var.rule_set_name
  scan_enabled  = var.scan_enabled
  tls_policy    = var.tls_policy

  dynamic "add_header_action" {
    for_each = var.add_header_action
    content {
      header_name  = add_header_action.value["header_name"]
      header_value = add_header_action.value["header_value"]
      position     = add_header_action.value["position"]
    }
  }

  dynamic "bounce_action" {
    for_each = var.bounce_action
    content {
      message         = bounce_action.value["message"]
      position        = bounce_action.value["position"]
      sender          = bounce_action.value["sender"]
      smtp_reply_code = bounce_action.value["smtp_reply_code"]
      status_code     = bounce_action.value["status_code"]
      topic_arn       = bounce_action.value["topic_arn"]
    }
  }

  dynamic "lambda_action" {
    for_each = var.lambda_action
    content {
      function_arn    = lambda_action.value["function_arn"]
      invocation_type = lambda_action.value["invocation_type"]
      position        = lambda_action.value["position"]
      topic_arn       = lambda_action.value["topic_arn"]
    }
  }

  dynamic "s3_action" {
    for_each = var.s3_action
    content {
      bucket_name       = s3_action.value["bucket_name"]
      kms_key_arn       = s3_action.value["kms_key_arn"]
      object_key_prefix = s3_action.value["object_key_prefix"]
      position          = s3_action.value["position"]
      topic_arn         = s3_action.value["topic_arn"]
    }
  }

  dynamic "sns_action" {
    for_each = var.sns_action
    content {
      position  = sns_action.value["position"]
      topic_arn = sns_action.value["topic_arn"]
    }
  }

  dynamic "stop_action" {
    for_each = var.stop_action
    content {
      position  = stop_action.value["position"]
      scope     = stop_action.value["scope"]
      topic_arn = stop_action.value["topic_arn"]
    }
  }

  dynamic "workmail_action" {
    for_each = var.workmail_action
    content {
      organization_arn = workmail_action.value["organization_arn"]
      position         = workmail_action.value["position"]
      topic_arn        = workmail_action.value["topic_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ses_receipt_rule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ses_receipt_rule.this.id
}

output "tls_policy" {
  description = "returns a string"
  value       = aws_ses_receipt_rule.this.tls_policy
}

output "this" {
  value = aws_ses_receipt_rule.this
}
```

[top](#index)