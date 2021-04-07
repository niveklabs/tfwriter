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
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # enable_json_parsing - (optional) is a type of bool
  enable_json_parsing = var.enable_json_parsing
  # kind - (required) is a type of string
  kind = var.kind
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # namespace_id - (optional) is a type of string
  namespace_id = var.namespace_id
  # output_flush_interval - (optional) is a type of number
  output_flush_interval = var.output_flush_interval
  # output_tags - (optional) is a type of map of string
  output_tags = var.output_tags

  dynamic "custom_target_config" {
    for_each = var.custom_target_config
    content {
      # certificate - (optional) is a type of string
      certificate = custom_target_config.value["certificate"]
      # client_cert - (optional) is a type of string
      client_cert = custom_target_config.value["client_cert"]
      # client_key - (optional) is a type of string
      client_key = custom_target_config.value["client_key"]
      # content - (required) is a type of string
      content = custom_target_config.value["content"]
    }
  }

  dynamic "elasticsearch_config" {
    for_each = var.elasticsearch_config
    content {
      # auth_password - (optional) is a type of string
      auth_password = elasticsearch_config.value["auth_password"]
      # auth_username - (optional) is a type of string
      auth_username = elasticsearch_config.value["auth_username"]
      # certificate - (optional) is a type of string
      certificate = elasticsearch_config.value["certificate"]
      # client_cert - (optional) is a type of string
      client_cert = elasticsearch_config.value["client_cert"]
      # client_key - (optional) is a type of string
      client_key = elasticsearch_config.value["client_key"]
      # client_key_pass - (optional) is a type of string
      client_key_pass = elasticsearch_config.value["client_key_pass"]
      # date_format - (optional) is a type of string
      date_format = elasticsearch_config.value["date_format"]
      # endpoint - (required) is a type of string
      endpoint = elasticsearch_config.value["endpoint"]
      # index_prefix - (optional) is a type of string
      index_prefix = elasticsearch_config.value["index_prefix"]
      # ssl_verify - (optional) is a type of bool
      ssl_verify = elasticsearch_config.value["ssl_verify"]
      # ssl_version - (optional) is a type of string
      ssl_version = elasticsearch_config.value["ssl_version"]
    }
  }

  dynamic "fluentd_config" {
    for_each = var.fluentd_config
    content {
      # certificate - (optional) is a type of string
      certificate = fluentd_config.value["certificate"]
      # compress - (optional) is a type of bool
      compress = fluentd_config.value["compress"]
      # enable_tls - (optional) is a type of bool
      enable_tls = fluentd_config.value["enable_tls"]

      dynamic "fluent_servers" {
        for_each = fluentd_config.value.fluent_servers
        content {
          # endpoint - (required) is a type of string
          endpoint = fluent_servers.value["endpoint"]
          # hostname - (optional) is a type of string
          hostname = fluent_servers.value["hostname"]
          # password - (optional) is a type of string
          password = fluent_servers.value["password"]
          # shared_key - (optional) is a type of string
          shared_key = fluent_servers.value["shared_key"]
          # standby - (optional) is a type of bool
          standby = fluent_servers.value["standby"]
          # username - (optional) is a type of string
          username = fluent_servers.value["username"]
          # weight - (optional) is a type of number
          weight = fluent_servers.value["weight"]
        }
      }

    }
  }

  dynamic "kafka_config" {
    for_each = var.kafka_config
    content {
      # broker_endpoints - (optional) is a type of list of string
      broker_endpoints = kafka_config.value["broker_endpoints"]
      # certificate - (optional) is a type of string
      certificate = kafka_config.value["certificate"]
      # client_cert - (optional) is a type of string
      client_cert = kafka_config.value["client_cert"]
      # client_key - (optional) is a type of string
      client_key = kafka_config.value["client_key"]
      # topic - (required) is a type of string
      topic = kafka_config.value["topic"]
      # zookeeper_endpoint - (optional) is a type of string
      zookeeper_endpoint = kafka_config.value["zookeeper_endpoint"]
    }
  }

  dynamic "splunk_config" {
    for_each = var.splunk_config
    content {
      # certificate - (optional) is a type of string
      certificate = splunk_config.value["certificate"]
      # client_cert - (optional) is a type of string
      client_cert = splunk_config.value["client_cert"]
      # client_key - (optional) is a type of string
      client_key = splunk_config.value["client_key"]
      # client_key_pass - (optional) is a type of string
      client_key_pass = splunk_config.value["client_key_pass"]
      # endpoint - (required) is a type of string
      endpoint = splunk_config.value["endpoint"]
      # index - (optional) is a type of string
      index = splunk_config.value["index"]
      # source - (optional) is a type of string
      source = splunk_config.value["source"]
      # ssl_verify - (optional) is a type of bool
      ssl_verify = splunk_config.value["ssl_verify"]
      # token - (required) is a type of string
      token = splunk_config.value["token"]
    }
  }

  dynamic "syslog_config" {
    for_each = var.syslog_config
    content {
      # certificate - (optional) is a type of string
      certificate = syslog_config.value["certificate"]
      # client_cert - (optional) is a type of string
      client_cert = syslog_config.value["client_cert"]
      # client_key - (optional) is a type of string
      client_key = syslog_config.value["client_key"]
      # enable_tls - (optional) is a type of bool
      enable_tls = syslog_config.value["enable_tls"]
      # endpoint - (required) is a type of string
      endpoint = syslog_config.value["endpoint"]
      # program - (optional) is a type of string
      program = syslog_config.value["program"]
      # protocol - (optional) is a type of string
      protocol = syslog_config.value["protocol"]
      # severity - (optional) is a type of string
      severity = syslog_config.value["severity"]
      # ssl_verify - (optional) is a type of bool
      ssl_verify = syslog_config.value["ssl_verify"]
      # token - (optional) is a type of string
      token = syslog_config.value["token"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
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