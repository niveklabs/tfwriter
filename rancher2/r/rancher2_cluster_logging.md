# rancher2_cluster_logging

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_cluster_logging" {
  source = "./modules/rancher2/r/rancher2_cluster_logging"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # cluster_id - (required) is a type of string
  cluster_id = null
  # enable_json_parsing - (optional) is a type of bool
  enable_json_parsing = null
  # kind - (required) is a type of string
  kind = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # namespace_id - (optional) is a type of string
  namespace_id = null
  # output_flush_interval - (optional) is a type of number
  output_flush_interval = null
  # output_tags - (optional) is a type of map of string
  output_tags = {}

  custom_target_config = [{
    certificate = null
    client_cert = null
    client_key  = null
    content     = null
  }]

  elasticsearch_config = [{
    auth_password   = null
    auth_username   = null
    certificate     = null
    client_cert     = null
    client_key      = null
    client_key_pass = null
    date_format     = null
    endpoint        = null
    index_prefix    = null
    ssl_verify      = null
    ssl_version     = null
  }]

  fluentd_config = [{
    certificate = null
    compress    = null
    enable_tls  = null
    fluent_servers = [{
      endpoint   = null
      hostname   = null
      password   = null
      shared_key = null
      standby    = null
      username   = null
      weight     = null
    }]
  }]

  kafka_config = [{
    broker_endpoints   = []
    certificate        = null
    client_cert        = null
    client_key         = null
    topic              = null
    zookeeper_endpoint = null
  }]

  splunk_config = [{
    certificate     = null
    client_cert     = null
    client_key      = null
    client_key_pass = null
    endpoint        = null
    index           = null
    source          = null
    ssl_verify      = null
    token           = null
  }]

  syslog_config = [{
    certificate = null
    client_cert = null
    client_key  = null
    enable_tls  = null
    endpoint    = null
    program     = null
    protocol    = null
    severity    = null
    ssl_verify  = null
    token       = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "enable_json_parsing" {
  description = "(optional) - Optional enable json log parsing"
  type        = bool
  default     = null
}

variable "kind" {
  description = "(required)"
  type        = string
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_flush_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "output_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "custom_target_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      certificate = string
      client_cert = string
      client_key  = string
      content     = string
    }
  ))
  default = []
}

variable "elasticsearch_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auth_password   = string
      auth_username   = string
      certificate     = string
      client_cert     = string
      client_key      = string
      client_key_pass = string
      date_format     = string
      endpoint        = string
      index_prefix    = string
      ssl_verify      = bool
      ssl_version     = string
    }
  ))
  default = []
}

variable "fluentd_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      certificate = string
      compress    = bool
      enable_tls  = bool
      fluent_servers = list(object(
        {
          endpoint   = string
          hostname   = string
          password   = string
          shared_key = string
          standby    = bool
          username   = string
          weight     = number
        }
      ))
    }
  ))
  default = []
}

variable "kafka_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      broker_endpoints   = list(string)
      certificate        = string
      client_cert        = string
      client_key         = string
      topic              = string
      zookeeper_endpoint = string
    }
  ))
  default = []
}

variable "splunk_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      certificate     = string
      client_cert     = string
      client_key      = string
      client_key_pass = string
      endpoint        = string
      index           = string
      source          = string
      ssl_verify      = bool
      token           = string
    }
  ))
  default = []
}

variable "syslog_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      certificate = string
      client_cert = string
      client_key  = string
      enable_tls  = bool
      endpoint    = string
      program     = string
      protocol    = string
      severity    = string
      ssl_verify  = bool
      token       = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_cluster_logging" "this" {
  annotations           = var.annotations
  cluster_id            = var.cluster_id
  enable_json_parsing   = var.enable_json_parsing
  kind                  = var.kind
  labels                = var.labels
  name                  = var.name
  namespace_id          = var.namespace_id
  output_flush_interval = var.output_flush_interval
  output_tags           = var.output_tags

  dynamic "custom_target_config" {
    for_each = var.custom_target_config
    content {
      certificate = custom_target_config.value["certificate"]
      client_cert = custom_target_config.value["client_cert"]
      client_key  = custom_target_config.value["client_key"]
      content     = custom_target_config.value["content"]
    }
  }

  dynamic "elasticsearch_config" {
    for_each = var.elasticsearch_config
    content {
      auth_password   = elasticsearch_config.value["auth_password"]
      auth_username   = elasticsearch_config.value["auth_username"]
      certificate     = elasticsearch_config.value["certificate"]
      client_cert     = elasticsearch_config.value["client_cert"]
      client_key      = elasticsearch_config.value["client_key"]
      client_key_pass = elasticsearch_config.value["client_key_pass"]
      date_format     = elasticsearch_config.value["date_format"]
      endpoint        = elasticsearch_config.value["endpoint"]
      index_prefix    = elasticsearch_config.value["index_prefix"]
      ssl_verify      = elasticsearch_config.value["ssl_verify"]
      ssl_version     = elasticsearch_config.value["ssl_version"]
    }
  }

  dynamic "fluentd_config" {
    for_each = var.fluentd_config
    content {
      certificate = fluentd_config.value["certificate"]
      compress    = fluentd_config.value["compress"]
      enable_tls  = fluentd_config.value["enable_tls"]

      dynamic "fluent_servers" {
        for_each = fluentd_config.value.fluent_servers
        content {
          endpoint   = fluent_servers.value["endpoint"]
          hostname   = fluent_servers.value["hostname"]
          password   = fluent_servers.value["password"]
          shared_key = fluent_servers.value["shared_key"]
          standby    = fluent_servers.value["standby"]
          username   = fluent_servers.value["username"]
          weight     = fluent_servers.value["weight"]
        }
      }

    }
  }

  dynamic "kafka_config" {
    for_each = var.kafka_config
    content {
      broker_endpoints   = kafka_config.value["broker_endpoints"]
      certificate        = kafka_config.value["certificate"]
      client_cert        = kafka_config.value["client_cert"]
      client_key         = kafka_config.value["client_key"]
      topic              = kafka_config.value["topic"]
      zookeeper_endpoint = kafka_config.value["zookeeper_endpoint"]
    }
  }

  dynamic "splunk_config" {
    for_each = var.splunk_config
    content {
      certificate     = splunk_config.value["certificate"]
      client_cert     = splunk_config.value["client_cert"]
      client_key      = splunk_config.value["client_key"]
      client_key_pass = splunk_config.value["client_key_pass"]
      endpoint        = splunk_config.value["endpoint"]
      index           = splunk_config.value["index"]
      source          = splunk_config.value["source"]
      ssl_verify      = splunk_config.value["ssl_verify"]
      token           = splunk_config.value["token"]
    }
  }

  dynamic "syslog_config" {
    for_each = var.syslog_config
    content {
      certificate = syslog_config.value["certificate"]
      client_cert = syslog_config.value["client_cert"]
      client_key  = syslog_config.value["client_key"]
      enable_tls  = syslog_config.value["enable_tls"]
      endpoint    = syslog_config.value["endpoint"]
      program     = syslog_config.value["program"]
      protocol    = syslog_config.value["protocol"]
      severity    = syslog_config.value["severity"]
      ssl_verify  = syslog_config.value["ssl_verify"]
      token       = syslog_config.value["token"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_cluster_logging.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_cluster_logging.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_cluster_logging.this.labels
}

output "output_tags" {
  description = "returns a map of string"
  value       = rancher2_cluster_logging.this.output_tags
}

output "this" {
  value = rancher2_cluster_logging.this
}
```

[top](#index)