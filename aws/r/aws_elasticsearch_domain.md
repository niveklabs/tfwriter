# aws_elasticsearch_domain

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
module "aws_elasticsearch_domain" {
  source = "./modules/aws/r/aws_elasticsearch_domain"

  # access_policies - (optional) is a type of string
  access_policies = null
  # advanced_options - (optional) is a type of map of string
  advanced_options = {}
  # domain_name - (required) is a type of string
  domain_name = null
  # elasticsearch_version - (optional) is a type of string
  elasticsearch_version = null
  # tags - (optional) is a type of map of string
  tags = {}

  advanced_security_options = [{
    enabled                        = null
    internal_user_database_enabled = null
    master_user_options = [{
      master_user_arn      = null
      master_user_name     = null
      master_user_password = null
    }]
  }]

  cluster_config = [{
    dedicated_master_count   = null
    dedicated_master_enabled = null
    dedicated_master_type    = null
    instance_count           = null
    instance_type            = null
    warm_count               = null
    warm_enabled             = null
    warm_type                = null
    zone_awareness_config = [{
      availability_zone_count = null
    }]
    zone_awareness_enabled = null
  }]

  cognito_options = [{
    enabled          = null
    identity_pool_id = null
    role_arn         = null
    user_pool_id     = null
  }]

  domain_endpoint_options = [{
    custom_endpoint                 = null
    custom_endpoint_certificate_arn = null
    custom_endpoint_enabled         = null
    enforce_https                   = null
    tls_security_policy             = null
  }]

  ebs_options = [{
    ebs_enabled = null
    iops        = null
    volume_size = null
    volume_type = null
  }]

  encrypt_at_rest = [{
    enabled    = null
    kms_key_id = null
  }]

  log_publishing_options = [{
    cloudwatch_log_group_arn = null
    enabled                  = null
    log_type                 = null
  }]

  node_to_node_encryption = [{
    enabled = null
  }]

  snapshot_options = [{
    automated_snapshot_start_hour = null
  }]

  timeouts = [{
    update = null
  }]

  vpc_options = [{
    availability_zones = []
    security_group_ids = []
    subnet_ids         = []
    vpc_id             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_policies" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "advanced_options" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "elasticsearch_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "advanced_security_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled                        = bool
      internal_user_database_enabled = bool
      master_user_options = list(object(
        {
          master_user_arn      = string
          master_user_name     = string
          master_user_password = string
        }
      ))
    }
  ))
  default = []
}

variable "cluster_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dedicated_master_count   = number
      dedicated_master_enabled = bool
      dedicated_master_type    = string
      instance_count           = number
      instance_type            = string
      warm_count               = number
      warm_enabled             = bool
      warm_type                = string
      zone_awareness_config = list(object(
        {
          availability_zone_count = number
        }
      ))
      zone_awareness_enabled = bool
    }
  ))
  default = []
}

variable "cognito_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled          = bool
      identity_pool_id = string
      role_arn         = string
      user_pool_id     = string
    }
  ))
  default = []
}

variable "domain_endpoint_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      custom_endpoint                 = string
      custom_endpoint_certificate_arn = string
      custom_endpoint_enabled         = bool
      enforce_https                   = bool
      tls_security_policy             = string
    }
  ))
  default = []
}

variable "ebs_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ebs_enabled = bool
      iops        = number
      volume_size = number
      volume_type = string
    }
  ))
  default = []
}

variable "encrypt_at_rest" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled    = bool
      kms_key_id = string
    }
  ))
  default = []
}

variable "log_publishing_options" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cloudwatch_log_group_arn = string
      enabled                  = bool
      log_type                 = string
    }
  ))
  default = []
}

variable "node_to_node_encryption" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
    }
  ))
  default = []
}

variable "snapshot_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      automated_snapshot_start_hour = number
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      update = string
    }
  ))
  default = []
}

variable "vpc_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      availability_zones = set(string)
      security_group_ids = set(string)
      subnet_ids         = set(string)
      vpc_id             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_elasticsearch_domain" "this" {
  # access_policies - (optional) is a type of string
  access_policies = var.access_policies
  # advanced_options - (optional) is a type of map of string
  advanced_options = var.advanced_options
  # domain_name - (required) is a type of string
  domain_name = var.domain_name
  # elasticsearch_version - (optional) is a type of string
  elasticsearch_version = var.elasticsearch_version
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "advanced_security_options" {
    for_each = var.advanced_security_options
    content {
      # enabled - (required) is a type of bool
      enabled = advanced_security_options.value["enabled"]
      # internal_user_database_enabled - (optional) is a type of bool
      internal_user_database_enabled = advanced_security_options.value["internal_user_database_enabled"]

      dynamic "master_user_options" {
        for_each = advanced_security_options.value.master_user_options
        content {
          # master_user_arn - (optional) is a type of string
          master_user_arn = master_user_options.value["master_user_arn"]
          # master_user_name - (optional) is a type of string
          master_user_name = master_user_options.value["master_user_name"]
          # master_user_password - (optional) is a type of string
          master_user_password = master_user_options.value["master_user_password"]
        }
      }

    }
  }

  dynamic "cluster_config" {
    for_each = var.cluster_config
    content {
      # dedicated_master_count - (optional) is a type of number
      dedicated_master_count = cluster_config.value["dedicated_master_count"]
      # dedicated_master_enabled - (optional) is a type of bool
      dedicated_master_enabled = cluster_config.value["dedicated_master_enabled"]
      # dedicated_master_type - (optional) is a type of string
      dedicated_master_type = cluster_config.value["dedicated_master_type"]
      # instance_count - (optional) is a type of number
      instance_count = cluster_config.value["instance_count"]
      # instance_type - (optional) is a type of string
      instance_type = cluster_config.value["instance_type"]
      # warm_count - (optional) is a type of number
      warm_count = cluster_config.value["warm_count"]
      # warm_enabled - (optional) is a type of bool
      warm_enabled = cluster_config.value["warm_enabled"]
      # warm_type - (optional) is a type of string
      warm_type = cluster_config.value["warm_type"]
      # zone_awareness_enabled - (optional) is a type of bool
      zone_awareness_enabled = cluster_config.value["zone_awareness_enabled"]

      dynamic "zone_awareness_config" {
        for_each = cluster_config.value.zone_awareness_config
        content {
          # availability_zone_count - (optional) is a type of number
          availability_zone_count = zone_awareness_config.value["availability_zone_count"]
        }
      }

    }
  }

  dynamic "cognito_options" {
    for_each = var.cognito_options
    content {
      # enabled - (optional) is a type of bool
      enabled = cognito_options.value["enabled"]
      # identity_pool_id - (required) is a type of string
      identity_pool_id = cognito_options.value["identity_pool_id"]
      # role_arn - (required) is a type of string
      role_arn = cognito_options.value["role_arn"]
      # user_pool_id - (required) is a type of string
      user_pool_id = cognito_options.value["user_pool_id"]
    }
  }

  dynamic "domain_endpoint_options" {
    for_each = var.domain_endpoint_options
    content {
      # custom_endpoint - (optional) is a type of string
      custom_endpoint = domain_endpoint_options.value["custom_endpoint"]
      # custom_endpoint_certificate_arn - (optional) is a type of string
      custom_endpoint_certificate_arn = domain_endpoint_options.value["custom_endpoint_certificate_arn"]
      # custom_endpoint_enabled - (optional) is a type of bool
      custom_endpoint_enabled = domain_endpoint_options.value["custom_endpoint_enabled"]
      # enforce_https - (optional) is a type of bool
      enforce_https = domain_endpoint_options.value["enforce_https"]
      # tls_security_policy - (optional) is a type of string
      tls_security_policy = domain_endpoint_options.value["tls_security_policy"]
    }
  }

  dynamic "ebs_options" {
    for_each = var.ebs_options
    content {
      # ebs_enabled - (required) is a type of bool
      ebs_enabled = ebs_options.value["ebs_enabled"]
      # iops - (optional) is a type of number
      iops = ebs_options.value["iops"]
      # volume_size - (optional) is a type of number
      volume_size = ebs_options.value["volume_size"]
      # volume_type - (optional) is a type of string
      volume_type = ebs_options.value["volume_type"]
    }
  }

  dynamic "encrypt_at_rest" {
    for_each = var.encrypt_at_rest
    content {
      # enabled - (required) is a type of bool
      enabled = encrypt_at_rest.value["enabled"]
      # kms_key_id - (optional) is a type of string
      kms_key_id = encrypt_at_rest.value["kms_key_id"]
    }
  }

  dynamic "log_publishing_options" {
    for_each = var.log_publishing_options
    content {
      # cloudwatch_log_group_arn - (required) is a type of string
      cloudwatch_log_group_arn = log_publishing_options.value["cloudwatch_log_group_arn"]
      # enabled - (optional) is a type of bool
      enabled = log_publishing_options.value["enabled"]
      # log_type - (required) is a type of string
      log_type = log_publishing_options.value["log_type"]
    }
  }

  dynamic "node_to_node_encryption" {
    for_each = var.node_to_node_encryption
    content {
      # enabled - (required) is a type of bool
      enabled = node_to_node_encryption.value["enabled"]
    }
  }

  dynamic "snapshot_options" {
    for_each = var.snapshot_options
    content {
      # automated_snapshot_start_hour - (required) is a type of number
      automated_snapshot_start_hour = snapshot_options.value["automated_snapshot_start_hour"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

  dynamic "vpc_options" {
    for_each = var.vpc_options
    content {
      # security_group_ids - (optional) is a type of set of string
      security_group_ids = vpc_options.value["security_group_ids"]
      # subnet_ids - (optional) is a type of set of string
      subnet_ids = vpc_options.value["subnet_ids"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access_policies" {
  description = "returns a string"
  value       = aws_elasticsearch_domain.this.access_policies
}

output "advanced_options" {
  description = "returns a map of string"
  value       = aws_elasticsearch_domain.this.advanced_options
}

output "arn" {
  description = "returns a string"
  value       = aws_elasticsearch_domain.this.arn
}

output "domain_id" {
  description = "returns a string"
  value       = aws_elasticsearch_domain.this.domain_id
}

output "endpoint" {
  description = "returns a string"
  value       = aws_elasticsearch_domain.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = aws_elasticsearch_domain.this.id
}

output "kibana_endpoint" {
  description = "returns a string"
  value       = aws_elasticsearch_domain.this.kibana_endpoint
}

output "this" {
  value = aws_elasticsearch_domain.this
}
```

[top](#index)