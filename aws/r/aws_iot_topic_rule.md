# aws_iot_topic_rule

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
module "aws_iot_topic_rule" {
  source = "./modules/aws/r/aws_iot_topic_rule"

  # description - (optional) is a type of string
  description = null
  # enabled - (required) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # sql - (required) is a type of string
  sql = null
  # sql_version - (required) is a type of string
  sql_version = null
  # tags - (optional) is a type of map of string
  tags = {}

  cloudwatch_alarm = [{
    alarm_name   = null
    role_arn     = null
    state_reason = null
    state_value  = null
  }]

  cloudwatch_metric = [{
    metric_name      = null
    metric_namespace = null
    metric_timestamp = null
    metric_unit      = null
    metric_value     = null
    role_arn         = null
  }]

  dynamodb = [{
    hash_key_field  = null
    hash_key_type   = null
    hash_key_value  = null
    operation       = null
    payload_field   = null
    range_key_field = null
    range_key_type  = null
    range_key_value = null
    role_arn        = null
    table_name      = null
  }]

  dynamodbv2 = [{
    put_item = [{
      table_name = null
    }]
    role_arn = null
  }]

  elasticsearch = [{
    endpoint = null
    id       = null
    index    = null
    role_arn = null
    type     = null
  }]

  error_action = [{
    cloudwatch_alarm = [{
      alarm_name   = null
      role_arn     = null
      state_reason = null
      state_value  = null
    }]
    cloudwatch_metric = [{
      metric_name      = null
      metric_namespace = null
      metric_timestamp = null
      metric_unit      = null
      metric_value     = null
      role_arn         = null
    }]
    dynamodb = [{
      hash_key_field  = null
      hash_key_type   = null
      hash_key_value  = null
      operation       = null
      payload_field   = null
      range_key_field = null
      range_key_type  = null
      range_key_value = null
      role_arn        = null
      table_name      = null
    }]
    dynamodbv2 = [{
      put_item = [{
        table_name = null
      }]
      role_arn = null
    }]
    elasticsearch = [{
      endpoint = null
      id       = null
      index    = null
      role_arn = null
      type     = null
    }]
    firehose = [{
      delivery_stream_name = null
      role_arn             = null
      separator            = null
    }]
    iot_analytics = [{
      channel_name = null
      role_arn     = null
    }]
    iot_events = [{
      input_name = null
      message_id = null
      role_arn   = null
    }]
    kinesis = [{
      partition_key = null
      role_arn      = null
      stream_name   = null
    }]
    lambda = [{
      function_arn = null
    }]
    republish = [{
      qos      = null
      role_arn = null
      topic    = null
    }]
    s3 = [{
      bucket_name = null
      key         = null
      role_arn    = null
    }]
    sns = [{
      message_format = null
      role_arn       = null
      target_arn     = null
    }]
    sqs = [{
      queue_url  = null
      role_arn   = null
      use_base64 = null
    }]
    step_functions = [{
      execution_name_prefix = null
      role_arn              = null
      state_machine_name    = null
    }]
  }]

  firehose = [{
    delivery_stream_name = null
    role_arn             = null
    separator            = null
  }]

  iot_analytics = [{
    channel_name = null
    role_arn     = null
  }]

  iot_events = [{
    input_name = null
    message_id = null
    role_arn   = null
  }]

  kinesis = [{
    partition_key = null
    role_arn      = null
    stream_name   = null
  }]

  lambda = [{
    function_arn = null
  }]

  republish = [{
    qos      = null
    role_arn = null
    topic    = null
  }]

  s3 = [{
    bucket_name = null
    key         = null
    role_arn    = null
  }]

  sns = [{
    message_format = null
    role_arn       = null
    target_arn     = null
  }]

  sqs = [{
    queue_url  = null
    role_arn   = null
    use_base64 = null
  }]

  step_functions = [{
    execution_name_prefix = null
    role_arn              = null
    state_machine_name    = null
  }]
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

variable "enabled" {
  description = "(required)"
  type        = bool
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "sql" {
  description = "(required)"
  type        = string
}

variable "sql_version" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "cloudwatch_alarm" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      alarm_name   = string
      role_arn     = string
      state_reason = string
      state_value  = string
    }
  ))
  default = []
}

variable "cloudwatch_metric" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      metric_name      = string
      metric_namespace = string
      metric_timestamp = string
      metric_unit      = string
      metric_value     = string
      role_arn         = string
    }
  ))
  default = []
}

variable "dynamodb" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      hash_key_field  = string
      hash_key_type   = string
      hash_key_value  = string
      operation       = string
      payload_field   = string
      range_key_field = string
      range_key_type  = string
      range_key_value = string
      role_arn        = string
      table_name      = string
    }
  ))
  default = []
}

variable "dynamodbv2" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      put_item = list(object(
        {
          table_name = string
        }
      ))
      role_arn = string
    }
  ))
  default = []
}

variable "elasticsearch" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      endpoint = string
      id       = string
      index    = string
      role_arn = string
      type     = string
    }
  ))
  default = []
}

variable "error_action" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloudwatch_alarm = list(object(
        {
          alarm_name   = string
          role_arn     = string
          state_reason = string
          state_value  = string
        }
      ))
      cloudwatch_metric = list(object(
        {
          metric_name      = string
          metric_namespace = string
          metric_timestamp = string
          metric_unit      = string
          metric_value     = string
          role_arn         = string
        }
      ))
      dynamodb = list(object(
        {
          hash_key_field  = string
          hash_key_type   = string
          hash_key_value  = string
          operation       = string
          payload_field   = string
          range_key_field = string
          range_key_type  = string
          range_key_value = string
          role_arn        = string
          table_name      = string
        }
      ))
      dynamodbv2 = list(object(
        {
          put_item = list(object(
            {
              table_name = string
            }
          ))
          role_arn = string
        }
      ))
      elasticsearch = list(object(
        {
          endpoint = string
          id       = string
          index    = string
          role_arn = string
          type     = string
        }
      ))
      firehose = list(object(
        {
          delivery_stream_name = string
          role_arn             = string
          separator            = string
        }
      ))
      iot_analytics = list(object(
        {
          channel_name = string
          role_arn     = string
        }
      ))
      iot_events = list(object(
        {
          input_name = string
          message_id = string
          role_arn   = string
        }
      ))
      kinesis = list(object(
        {
          partition_key = string
          role_arn      = string
          stream_name   = string
        }
      ))
      lambda = list(object(
        {
          function_arn = string
        }
      ))
      republish = list(object(
        {
          qos      = number
          role_arn = string
          topic    = string
        }
      ))
      s3 = list(object(
        {
          bucket_name = string
          key         = string
          role_arn    = string
        }
      ))
      sns = list(object(
        {
          message_format = string
          role_arn       = string
          target_arn     = string
        }
      ))
      sqs = list(object(
        {
          queue_url  = string
          role_arn   = string
          use_base64 = bool
        }
      ))
      step_functions = list(object(
        {
          execution_name_prefix = string
          role_arn              = string
          state_machine_name    = string
        }
      ))
    }
  ))
  default = []
}

variable "firehose" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      delivery_stream_name = string
      role_arn             = string
      separator            = string
    }
  ))
  default = []
}

variable "iot_analytics" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      channel_name = string
      role_arn     = string
    }
  ))
  default = []
}

variable "iot_events" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      input_name = string
      message_id = string
      role_arn   = string
    }
  ))
  default = []
}

variable "kinesis" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      partition_key = string
      role_arn      = string
      stream_name   = string
    }
  ))
  default = []
}

variable "lambda" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      function_arn = string
    }
  ))
  default = []
}

variable "republish" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      qos      = number
      role_arn = string
      topic    = string
    }
  ))
  default = []
}

variable "s3" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bucket_name = string
      key         = string
      role_arn    = string
    }
  ))
  default = []
}

variable "sns" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      message_format = string
      role_arn       = string
      target_arn     = string
    }
  ))
  default = []
}

variable "sqs" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      queue_url  = string
      role_arn   = string
      use_base64 = bool
    }
  ))
  default = []
}

variable "step_functions" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      execution_name_prefix = string
      role_arn              = string
      state_machine_name    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_iot_topic_rule" "this" {
  # description - (optional) is a type of string
  description = var.description
  # enabled - (required) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # sql - (required) is a type of string
  sql = var.sql
  # sql_version - (required) is a type of string
  sql_version = var.sql_version
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "cloudwatch_alarm" {
    for_each = var.cloudwatch_alarm
    content {
      # alarm_name - (required) is a type of string
      alarm_name = cloudwatch_alarm.value["alarm_name"]
      # role_arn - (required) is a type of string
      role_arn = cloudwatch_alarm.value["role_arn"]
      # state_reason - (required) is a type of string
      state_reason = cloudwatch_alarm.value["state_reason"]
      # state_value - (required) is a type of string
      state_value = cloudwatch_alarm.value["state_value"]
    }
  }

  dynamic "cloudwatch_metric" {
    for_each = var.cloudwatch_metric
    content {
      # metric_name - (required) is a type of string
      metric_name = cloudwatch_metric.value["metric_name"]
      # metric_namespace - (required) is a type of string
      metric_namespace = cloudwatch_metric.value["metric_namespace"]
      # metric_timestamp - (optional) is a type of string
      metric_timestamp = cloudwatch_metric.value["metric_timestamp"]
      # metric_unit - (required) is a type of string
      metric_unit = cloudwatch_metric.value["metric_unit"]
      # metric_value - (required) is a type of string
      metric_value = cloudwatch_metric.value["metric_value"]
      # role_arn - (required) is a type of string
      role_arn = cloudwatch_metric.value["role_arn"]
    }
  }

  dynamic "dynamodb" {
    for_each = var.dynamodb
    content {
      # hash_key_field - (required) is a type of string
      hash_key_field = dynamodb.value["hash_key_field"]
      # hash_key_type - (optional) is a type of string
      hash_key_type = dynamodb.value["hash_key_type"]
      # hash_key_value - (required) is a type of string
      hash_key_value = dynamodb.value["hash_key_value"]
      # operation - (optional) is a type of string
      operation = dynamodb.value["operation"]
      # payload_field - (optional) is a type of string
      payload_field = dynamodb.value["payload_field"]
      # range_key_field - (optional) is a type of string
      range_key_field = dynamodb.value["range_key_field"]
      # range_key_type - (optional) is a type of string
      range_key_type = dynamodb.value["range_key_type"]
      # range_key_value - (optional) is a type of string
      range_key_value = dynamodb.value["range_key_value"]
      # role_arn - (required) is a type of string
      role_arn = dynamodb.value["role_arn"]
      # table_name - (required) is a type of string
      table_name = dynamodb.value["table_name"]
    }
  }

  dynamic "dynamodbv2" {
    for_each = var.dynamodbv2
    content {
      # role_arn - (required) is a type of string
      role_arn = dynamodbv2.value["role_arn"]

      dynamic "put_item" {
        for_each = dynamodbv2.value.put_item
        content {
          # table_name - (required) is a type of string
          table_name = put_item.value["table_name"]
        }
      }

    }
  }

  dynamic "elasticsearch" {
    for_each = var.elasticsearch
    content {
      # endpoint - (required) is a type of string
      endpoint = elasticsearch.value["endpoint"]
      # id - (required) is a type of string
      id = elasticsearch.value["id"]
      # index - (required) is a type of string
      index = elasticsearch.value["index"]
      # role_arn - (required) is a type of string
      role_arn = elasticsearch.value["role_arn"]
      # type - (required) is a type of string
      type = elasticsearch.value["type"]
    }
  }

  dynamic "error_action" {
    for_each = var.error_action
    content {

      dynamic "cloudwatch_alarm" {
        for_each = error_action.value.cloudwatch_alarm
        content {
          # alarm_name - (required) is a type of string
          alarm_name = cloudwatch_alarm.value["alarm_name"]
          # role_arn - (required) is a type of string
          role_arn = cloudwatch_alarm.value["role_arn"]
          # state_reason - (required) is a type of string
          state_reason = cloudwatch_alarm.value["state_reason"]
          # state_value - (required) is a type of string
          state_value = cloudwatch_alarm.value["state_value"]
        }
      }

      dynamic "cloudwatch_metric" {
        for_each = error_action.value.cloudwatch_metric
        content {
          # metric_name - (required) is a type of string
          metric_name = cloudwatch_metric.value["metric_name"]
          # metric_namespace - (required) is a type of string
          metric_namespace = cloudwatch_metric.value["metric_namespace"]
          # metric_timestamp - (optional) is a type of string
          metric_timestamp = cloudwatch_metric.value["metric_timestamp"]
          # metric_unit - (required) is a type of string
          metric_unit = cloudwatch_metric.value["metric_unit"]
          # metric_value - (required) is a type of string
          metric_value = cloudwatch_metric.value["metric_value"]
          # role_arn - (required) is a type of string
          role_arn = cloudwatch_metric.value["role_arn"]
        }
      }

      dynamic "dynamodb" {
        for_each = error_action.value.dynamodb
        content {
          # hash_key_field - (required) is a type of string
          hash_key_field = dynamodb.value["hash_key_field"]
          # hash_key_type - (optional) is a type of string
          hash_key_type = dynamodb.value["hash_key_type"]
          # hash_key_value - (required) is a type of string
          hash_key_value = dynamodb.value["hash_key_value"]
          # operation - (optional) is a type of string
          operation = dynamodb.value["operation"]
          # payload_field - (optional) is a type of string
          payload_field = dynamodb.value["payload_field"]
          # range_key_field - (optional) is a type of string
          range_key_field = dynamodb.value["range_key_field"]
          # range_key_type - (optional) is a type of string
          range_key_type = dynamodb.value["range_key_type"]
          # range_key_value - (optional) is a type of string
          range_key_value = dynamodb.value["range_key_value"]
          # role_arn - (required) is a type of string
          role_arn = dynamodb.value["role_arn"]
          # table_name - (required) is a type of string
          table_name = dynamodb.value["table_name"]
        }
      }

      dynamic "dynamodbv2" {
        for_each = error_action.value.dynamodbv2
        content {
          # role_arn - (required) is a type of string
          role_arn = dynamodbv2.value["role_arn"]

          dynamic "put_item" {
            for_each = dynamodbv2.value.put_item
            content {
              # table_name - (required) is a type of string
              table_name = put_item.value["table_name"]
            }
          }

        }
      }

      dynamic "elasticsearch" {
        for_each = error_action.value.elasticsearch
        content {
          # endpoint - (required) is a type of string
          endpoint = elasticsearch.value["endpoint"]
          # id - (required) is a type of string
          id = elasticsearch.value["id"]
          # index - (required) is a type of string
          index = elasticsearch.value["index"]
          # role_arn - (required) is a type of string
          role_arn = elasticsearch.value["role_arn"]
          # type - (required) is a type of string
          type = elasticsearch.value["type"]
        }
      }

      dynamic "firehose" {
        for_each = error_action.value.firehose
        content {
          # delivery_stream_name - (required) is a type of string
          delivery_stream_name = firehose.value["delivery_stream_name"]
          # role_arn - (required) is a type of string
          role_arn = firehose.value["role_arn"]
          # separator - (optional) is a type of string
          separator = firehose.value["separator"]
        }
      }

      dynamic "iot_analytics" {
        for_each = error_action.value.iot_analytics
        content {
          # channel_name - (required) is a type of string
          channel_name = iot_analytics.value["channel_name"]
          # role_arn - (required) is a type of string
          role_arn = iot_analytics.value["role_arn"]
        }
      }

      dynamic "iot_events" {
        for_each = error_action.value.iot_events
        content {
          # input_name - (required) is a type of string
          input_name = iot_events.value["input_name"]
          # message_id - (optional) is a type of string
          message_id = iot_events.value["message_id"]
          # role_arn - (required) is a type of string
          role_arn = iot_events.value["role_arn"]
        }
      }

      dynamic "kinesis" {
        for_each = error_action.value.kinesis
        content {
          # partition_key - (optional) is a type of string
          partition_key = kinesis.value["partition_key"]
          # role_arn - (required) is a type of string
          role_arn = kinesis.value["role_arn"]
          # stream_name - (required) is a type of string
          stream_name = kinesis.value["stream_name"]
        }
      }

      dynamic "lambda" {
        for_each = error_action.value.lambda
        content {
          # function_arn - (required) is a type of string
          function_arn = lambda.value["function_arn"]
        }
      }

      dynamic "republish" {
        for_each = error_action.value.republish
        content {
          # qos - (optional) is a type of number
          qos = republish.value["qos"]
          # role_arn - (required) is a type of string
          role_arn = republish.value["role_arn"]
          # topic - (required) is a type of string
          topic = republish.value["topic"]
        }
      }

      dynamic "s3" {
        for_each = error_action.value.s3
        content {
          # bucket_name - (required) is a type of string
          bucket_name = s3.value["bucket_name"]
          # key - (required) is a type of string
          key = s3.value["key"]
          # role_arn - (required) is a type of string
          role_arn = s3.value["role_arn"]
        }
      }

      dynamic "sns" {
        for_each = error_action.value.sns
        content {
          # message_format - (optional) is a type of string
          message_format = sns.value["message_format"]
          # role_arn - (required) is a type of string
          role_arn = sns.value["role_arn"]
          # target_arn - (required) is a type of string
          target_arn = sns.value["target_arn"]
        }
      }

      dynamic "sqs" {
        for_each = error_action.value.sqs
        content {
          # queue_url - (required) is a type of string
          queue_url = sqs.value["queue_url"]
          # role_arn - (required) is a type of string
          role_arn = sqs.value["role_arn"]
          # use_base64 - (required) is a type of bool
          use_base64 = sqs.value["use_base64"]
        }
      }

      dynamic "step_functions" {
        for_each = error_action.value.step_functions
        content {
          # execution_name_prefix - (optional) is a type of string
          execution_name_prefix = step_functions.value["execution_name_prefix"]
          # role_arn - (required) is a type of string
          role_arn = step_functions.value["role_arn"]
          # state_machine_name - (required) is a type of string
          state_machine_name = step_functions.value["state_machine_name"]
        }
      }

    }
  }

  dynamic "firehose" {
    for_each = var.firehose
    content {
      # delivery_stream_name - (required) is a type of string
      delivery_stream_name = firehose.value["delivery_stream_name"]
      # role_arn - (required) is a type of string
      role_arn = firehose.value["role_arn"]
      # separator - (optional) is a type of string
      separator = firehose.value["separator"]
    }
  }

  dynamic "iot_analytics" {
    for_each = var.iot_analytics
    content {
      # channel_name - (required) is a type of string
      channel_name = iot_analytics.value["channel_name"]
      # role_arn - (required) is a type of string
      role_arn = iot_analytics.value["role_arn"]
    }
  }

  dynamic "iot_events" {
    for_each = var.iot_events
    content {
      # input_name - (required) is a type of string
      input_name = iot_events.value["input_name"]
      # message_id - (optional) is a type of string
      message_id = iot_events.value["message_id"]
      # role_arn - (required) is a type of string
      role_arn = iot_events.value["role_arn"]
    }
  }

  dynamic "kinesis" {
    for_each = var.kinesis
    content {
      # partition_key - (optional) is a type of string
      partition_key = kinesis.value["partition_key"]
      # role_arn - (required) is a type of string
      role_arn = kinesis.value["role_arn"]
      # stream_name - (required) is a type of string
      stream_name = kinesis.value["stream_name"]
    }
  }

  dynamic "lambda" {
    for_each = var.lambda
    content {
      # function_arn - (required) is a type of string
      function_arn = lambda.value["function_arn"]
    }
  }

  dynamic "republish" {
    for_each = var.republish
    content {
      # qos - (optional) is a type of number
      qos = republish.value["qos"]
      # role_arn - (required) is a type of string
      role_arn = republish.value["role_arn"]
      # topic - (required) is a type of string
      topic = republish.value["topic"]
    }
  }

  dynamic "s3" {
    for_each = var.s3
    content {
      # bucket_name - (required) is a type of string
      bucket_name = s3.value["bucket_name"]
      # key - (required) is a type of string
      key = s3.value["key"]
      # role_arn - (required) is a type of string
      role_arn = s3.value["role_arn"]
    }
  }

  dynamic "sns" {
    for_each = var.sns
    content {
      # message_format - (optional) is a type of string
      message_format = sns.value["message_format"]
      # role_arn - (required) is a type of string
      role_arn = sns.value["role_arn"]
      # target_arn - (required) is a type of string
      target_arn = sns.value["target_arn"]
    }
  }

  dynamic "sqs" {
    for_each = var.sqs
    content {
      # queue_url - (required) is a type of string
      queue_url = sqs.value["queue_url"]
      # role_arn - (required) is a type of string
      role_arn = sqs.value["role_arn"]
      # use_base64 - (required) is a type of bool
      use_base64 = sqs.value["use_base64"]
    }
  }

  dynamic "step_functions" {
    for_each = var.step_functions
    content {
      # execution_name_prefix - (optional) is a type of string
      execution_name_prefix = step_functions.value["execution_name_prefix"]
      # role_arn - (required) is a type of string
      role_arn = step_functions.value["role_arn"]
      # state_machine_name - (required) is a type of string
      state_machine_name = step_functions.value["state_machine_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_iot_topic_rule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_iot_topic_rule.this.id
}

output "this" {
  value = aws_iot_topic_rule.this
}
```

[top](#index)