# aws_msk_cluster

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
module "aws_msk_cluster" {
  source = "./modules/aws/r/aws_msk_cluster"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # enhanced_monitoring - (optional) is a type of string
  enhanced_monitoring = null
  # kafka_version - (required) is a type of string
  kafka_version = null
  # number_of_broker_nodes - (required) is a type of number
  number_of_broker_nodes = null
  # tags - (optional) is a type of map of string
  tags = {}

  broker_node_group_info = [{
    az_distribution = null
    client_subnets  = []
    ebs_volume_size = null
    instance_type   = null
    security_groups = []
  }]

  client_authentication = [{
    sasl = [{
      scram = null
    }]
    tls = [{
      certificate_authority_arns = []
    }]
  }]

  configuration_info = [{
    arn      = null
    revision = null
  }]

  encryption_info = [{
    encryption_at_rest_kms_key_arn = null
    encryption_in_transit = [{
      client_broker = null
      in_cluster    = null
    }]
  }]

  logging_info = [{
    broker_logs = [{
      cloudwatch_logs = [{
        enabled   = null
        log_group = null
      }]
      firehose = [{
        delivery_stream = null
        enabled         = null
      }]
      s3 = [{
        bucket  = null
        enabled = null
        prefix  = null
      }]
    }]
  }]

  open_monitoring = [{
    prometheus = [{
      jmx_exporter = [{
        enabled_in_broker = null
      }]
      node_exporter = [{
        enabled_in_broker = null
      }]
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "enhanced_monitoring" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kafka_version" {
  description = "(required)"
  type        = string
}

variable "number_of_broker_nodes" {
  description = "(required)"
  type        = number
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "broker_node_group_info" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      az_distribution = string
      client_subnets  = list(string)
      ebs_volume_size = number
      instance_type   = string
      security_groups = list(string)
    }
  ))
}

variable "client_authentication" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      sasl = list(object(
        {
          scram = bool
        }
      ))
      tls = list(object(
        {
          certificate_authority_arns = set(string)
        }
      ))
    }
  ))
  default = []
}

variable "configuration_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      arn      = string
      revision = number
    }
  ))
  default = []
}

variable "encryption_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      encryption_at_rest_kms_key_arn = string
      encryption_in_transit = list(object(
        {
          client_broker = string
          in_cluster    = bool
        }
      ))
    }
  ))
  default = []
}

variable "logging_info" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      broker_logs = list(object(
        {
          cloudwatch_logs = list(object(
            {
              enabled   = bool
              log_group = string
            }
          ))
          firehose = list(object(
            {
              delivery_stream = string
              enabled         = bool
            }
          ))
          s3 = list(object(
            {
              bucket  = string
              enabled = bool
              prefix  = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "open_monitoring" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      prometheus = list(object(
        {
          jmx_exporter = list(object(
            {
              enabled_in_broker = bool
            }
          ))
          node_exporter = list(object(
            {
              enabled_in_broker = bool
            }
          ))
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_msk_cluster" "this" {
  cluster_name           = var.cluster_name
  enhanced_monitoring    = var.enhanced_monitoring
  kafka_version          = var.kafka_version
  number_of_broker_nodes = var.number_of_broker_nodes
  tags                   = var.tags

  dynamic "broker_node_group_info" {
    for_each = var.broker_node_group_info
    content {
      az_distribution = broker_node_group_info.value["az_distribution"]
      client_subnets  = broker_node_group_info.value["client_subnets"]
      ebs_volume_size = broker_node_group_info.value["ebs_volume_size"]
      instance_type   = broker_node_group_info.value["instance_type"]
      security_groups = broker_node_group_info.value["security_groups"]
    }
  }

  dynamic "client_authentication" {
    for_each = var.client_authentication
    content {

      dynamic "sasl" {
        for_each = client_authentication.value.sasl
        content {
          scram = sasl.value["scram"]
        }
      }

      dynamic "tls" {
        for_each = client_authentication.value.tls
        content {
          certificate_authority_arns = tls.value["certificate_authority_arns"]
        }
      }

    }
  }

  dynamic "configuration_info" {
    for_each = var.configuration_info
    content {
      arn      = configuration_info.value["arn"]
      revision = configuration_info.value["revision"]
    }
  }

  dynamic "encryption_info" {
    for_each = var.encryption_info
    content {
      encryption_at_rest_kms_key_arn = encryption_info.value["encryption_at_rest_kms_key_arn"]

      dynamic "encryption_in_transit" {
        for_each = encryption_info.value.encryption_in_transit
        content {
          client_broker = encryption_in_transit.value["client_broker"]
          in_cluster    = encryption_in_transit.value["in_cluster"]
        }
      }

    }
  }

  dynamic "logging_info" {
    for_each = var.logging_info
    content {

      dynamic "broker_logs" {
        for_each = logging_info.value.broker_logs
        content {

          dynamic "cloudwatch_logs" {
            for_each = broker_logs.value.cloudwatch_logs
            content {
              enabled   = cloudwatch_logs.value["enabled"]
              log_group = cloudwatch_logs.value["log_group"]
            }
          }

          dynamic "firehose" {
            for_each = broker_logs.value.firehose
            content {
              delivery_stream = firehose.value["delivery_stream"]
              enabled         = firehose.value["enabled"]
            }
          }

          dynamic "s3" {
            for_each = broker_logs.value.s3
            content {
              bucket  = s3.value["bucket"]
              enabled = s3.value["enabled"]
              prefix  = s3.value["prefix"]
            }
          }

        }
      }

    }
  }

  dynamic "open_monitoring" {
    for_each = var.open_monitoring
    content {

      dynamic "prometheus" {
        for_each = open_monitoring.value.prometheus
        content {

          dynamic "jmx_exporter" {
            for_each = prometheus.value.jmx_exporter
            content {
              enabled_in_broker = jmx_exporter.value["enabled_in_broker"]
            }
          }

          dynamic "node_exporter" {
            for_each = prometheus.value.node_exporter
            content {
              enabled_in_broker = node_exporter.value["enabled_in_broker"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_msk_cluster.this.arn
}

output "bootstrap_brokers" {
  description = "returns a string"
  value       = aws_msk_cluster.this.bootstrap_brokers
}

output "bootstrap_brokers_sasl_scram" {
  description = "returns a string"
  value       = aws_msk_cluster.this.bootstrap_brokers_sasl_scram
}

output "bootstrap_brokers_tls" {
  description = "returns a string"
  value       = aws_msk_cluster.this.bootstrap_brokers_tls
}

output "current_version" {
  description = "returns a string"
  value       = aws_msk_cluster.this.current_version
}

output "id" {
  description = "returns a string"
  value       = aws_msk_cluster.this.id
}

output "zookeeper_connect_string" {
  description = "returns a string"
  value       = aws_msk_cluster.this.zookeeper_connect_string
}

output "this" {
  value = aws_msk_cluster.this
}
```

[top](#index)