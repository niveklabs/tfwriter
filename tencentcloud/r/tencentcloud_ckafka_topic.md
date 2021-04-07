# tencentcloud_ckafka_topic

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_ckafka_topic" {
  source = "./modules/tencentcloud/r/tencentcloud_ckafka_topic"

  # clean_up_policy - (optional) is a type of string
  clean_up_policy = null
  # enable_white_list - (optional) is a type of bool
  enable_white_list = null
  # instance_id - (required) is a type of string
  instance_id = null
  # ip_white_list - (optional) is a type of list of string
  ip_white_list = []
  # max_message_bytes - (optional) is a type of number
  max_message_bytes = null
  # note - (optional) is a type of string
  note = null
  # partition_num - (required) is a type of number
  partition_num = null
  # replica_num - (required) is a type of number
  replica_num = null
  # retention - (optional) is a type of number
  retention = null
  # segment - (optional) is a type of number
  segment = null
  # sync_replica_min_num - (optional) is a type of number
  sync_replica_min_num = null
  # topic_name - (required) is a type of string
  topic_name = null
  # unclean_leader_election_enable - (optional) is a type of bool
  unclean_leader_election_enable = null
}
```

[top](#index)

### Variables

```terraform
variable "clean_up_policy" {
  description = "(optional) - Clear log policy, log clear mode, default is `delete`. `delete`: logs are deleted according to the storage time. `compact`: logs are compressed according to the key. `compact, delete`: logs are compressed according to the key and will be deleted according to the storage time."
  type        = string
  default     = null
}

variable "enable_white_list" {
  description = "(optional) - Whether to open the ip whitelist, `true`: open, `false`: close."
  type        = bool
  default     = null
}

variable "instance_id" {
  description = "(required) - Ckafka instance ID."
  type        = string
}

variable "ip_white_list" {
  description = "(optional) - Ip whitelist, quota limit, required when enableWhileList=true."
  type        = list(string)
  default     = null
}

variable "max_message_bytes" {
  description = "(optional) - Max message bytes."
  type        = number
  default     = null
}

variable "note" {
  description = "(optional) - The subject note is a string of no more than 64 characters. It must start with a letter, and the remaining part can contain letters, numbers and dashes (-)."
  type        = string
  default     = null
}

variable "partition_num" {
  description = "(required) - The number of partition."
  type        = number
}

variable "replica_num" {
  description = "(required) - The number of replica, the maximum is 3."
  type        = number
}

variable "retention" {
  description = "(optional) - Message can be selected. Retention time, unit is ms, the current minimum value is 60000ms."
  type        = number
  default     = null
}

variable "segment" {
  description = "(optional) - Segment scrolling time, in ms, the current minimum is 3600000ms."
  type        = number
  default     = null
}

variable "sync_replica_min_num" {
  description = "(optional) - Min number of sync replicas, Default is `1`."
  type        = number
  default     = null
}

variable "topic_name" {
  description = "(required) - Name of the CKafka topic. It must start with a letter, the rest can contain letters, numbers and dashes(-). The length range is from 1 to 64."
  type        = string
}

variable "unclean_leader_election_enable" {
  description = "(optional) - Whether to allow unsynchronized replicas to be selected as leader, default is `false`, `true: `allowed, `false`: not allowed."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_ckafka_topic" "this" {
  # clean_up_policy - (optional) is a type of string
  clean_up_policy = var.clean_up_policy
  # enable_white_list - (optional) is a type of bool
  enable_white_list = var.enable_white_list
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # ip_white_list - (optional) is a type of list of string
  ip_white_list = var.ip_white_list
  # max_message_bytes - (optional) is a type of number
  max_message_bytes = var.max_message_bytes
  # note - (optional) is a type of string
  note = var.note
  # partition_num - (required) is a type of number
  partition_num = var.partition_num
  # replica_num - (required) is a type of number
  replica_num = var.replica_num
  # retention - (optional) is a type of number
  retention = var.retention
  # segment - (optional) is a type of number
  segment = var.segment
  # sync_replica_min_num - (optional) is a type of number
  sync_replica_min_num = var.sync_replica_min_num
  # topic_name - (required) is a type of string
  topic_name = var.topic_name
  # unclean_leader_election_enable - (optional) is a type of bool
  unclean_leader_election_enable = var.unclean_leader_election_enable
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_ckafka_topic.this.create_time
}

output "forward_cos_bucket" {
  description = "returns a string"
  value       = tencentcloud_ckafka_topic.this.forward_cos_bucket
}

output "forward_interval" {
  description = "returns a number"
  value       = tencentcloud_ckafka_topic.this.forward_interval
}

output "forward_status" {
  description = "returns a number"
  value       = tencentcloud_ckafka_topic.this.forward_status
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_ckafka_topic.this.id
}

output "message_storage_location" {
  description = "returns a string"
  value       = tencentcloud_ckafka_topic.this.message_storage_location
}

output "segment_bytes" {
  description = "returns a number"
  value       = tencentcloud_ckafka_topic.this.segment_bytes
}

output "this" {
  value = tencentcloud_ckafka_topic.this
}
```

[top](#index)