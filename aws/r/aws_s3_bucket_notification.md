# aws_s3_bucket_notification

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
module "aws_s3_bucket_notification" {
  source = "./modules/aws/r/aws_s3_bucket_notification"

  # bucket - (required) is a type of string
  bucket = null

  lambda_function = [{
    events              = []
    filter_prefix       = null
    filter_suffix       = null
    id                  = null
    lambda_function_arn = null
  }]

  queue = [{
    events        = []
    filter_prefix = null
    filter_suffix = null
    id            = null
    queue_arn     = null
  }]

  topic = [{
    events        = []
    filter_prefix = null
    filter_suffix = null
    id            = null
    topic_arn     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "lambda_function" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      events              = set(string)
      filter_prefix       = string
      filter_suffix       = string
      id                  = string
      lambda_function_arn = string
    }
  ))
  default = []
}

variable "queue" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      events        = set(string)
      filter_prefix = string
      filter_suffix = string
      id            = string
      queue_arn     = string
    }
  ))
  default = []
}

variable "topic" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      events        = set(string)
      filter_prefix = string
      filter_suffix = string
      id            = string
      topic_arn     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_s3_bucket_notification" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket

  dynamic "lambda_function" {
    for_each = var.lambda_function
    content {
      # events - (required) is a type of set of string
      events = lambda_function.value["events"]
      # filter_prefix - (optional) is a type of string
      filter_prefix = lambda_function.value["filter_prefix"]
      # filter_suffix - (optional) is a type of string
      filter_suffix = lambda_function.value["filter_suffix"]
      # id - (optional) is a type of string
      id = lambda_function.value["id"]
      # lambda_function_arn - (optional) is a type of string
      lambda_function_arn = lambda_function.value["lambda_function_arn"]
    }
  }

  dynamic "queue" {
    for_each = var.queue
    content {
      # events - (required) is a type of set of string
      events = queue.value["events"]
      # filter_prefix - (optional) is a type of string
      filter_prefix = queue.value["filter_prefix"]
      # filter_suffix - (optional) is a type of string
      filter_suffix = queue.value["filter_suffix"]
      # id - (optional) is a type of string
      id = queue.value["id"]
      # queue_arn - (required) is a type of string
      queue_arn = queue.value["queue_arn"]
    }
  }

  dynamic "topic" {
    for_each = var.topic
    content {
      # events - (required) is a type of set of string
      events = topic.value["events"]
      # filter_prefix - (optional) is a type of string
      filter_prefix = topic.value["filter_prefix"]
      # filter_suffix - (optional) is a type of string
      filter_suffix = topic.value["filter_suffix"]
      # id - (optional) is a type of string
      id = topic.value["id"]
      # topic_arn - (required) is a type of string
      topic_arn = topic.value["topic_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_s3_bucket_notification.this.id
}

output "this" {
  value = aws_s3_bucket_notification.this
}
```

[top](#index)