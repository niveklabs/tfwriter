# alicloud_log_etl

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_log_etl" {
  source = "./modules/alicloud/r/alicloud_log_etl"

  # access_key_id - (optional) is a type of string
  access_key_id = null
  # access_key_secret - (optional) is a type of string
  access_key_secret = null
  # create_time - (optional) is a type of number
  create_time = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # etl_name - (required) is a type of string
  etl_name = null
  # etl_type - (optional) is a type of string
  etl_type = null
  # from_time - (optional) is a type of number
  from_time = null
  # kms_encrypted_access_key_id - (optional) is a type of string
  kms_encrypted_access_key_id = null
  # kms_encrypted_access_key_secret - (optional) is a type of string
  kms_encrypted_access_key_secret = null
  # kms_encryption_access_key_id_context - (optional) is a type of map of string
  kms_encryption_access_key_id_context = {}
  # kms_encryption_access_key_secret_context - (optional) is a type of map of string
  kms_encryption_access_key_secret_context = {}
  # last_modified_time - (optional) is a type of number
  last_modified_time = null
  # logstore - (required) is a type of string
  logstore = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # project - (required) is a type of string
  project = null
  # role_arn - (optional) is a type of string
  role_arn = null
  # schedule - (optional) is a type of string
  schedule = null
  # script - (required) is a type of string
  script = null
  # status - (optional) is a type of string
  status = null
  # to_time - (optional) is a type of number
  to_time = null
  # version - (optional) is a type of number
  version = null

  etl_sinks = [{
    access_key_id                   = null
    access_key_secret               = null
    endpoint                        = null
    kms_encrypted_access_key_id     = null
    kms_encrypted_access_key_secret = null
    logstore                        = null
    name                            = null
    project                         = null
    role_arn                        = null
    type                            = null
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
variable "access_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "access_key_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "create_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "etl_name" {
  description = "(required)"
  type        = string
}

variable "etl_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "from_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "kms_encrypted_access_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_encrypted_access_key_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_encryption_access_key_id_context" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "kms_encryption_access_key_secret_context" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "last_modified_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "logstore" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "script" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "to_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "etl_sinks" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      access_key_id                   = string
      access_key_secret               = string
      endpoint                        = string
      kms_encrypted_access_key_id     = string
      kms_encrypted_access_key_secret = string
      logstore                        = string
      name                            = string
      project                         = string
      role_arn                        = string
      type                            = string
    }
  ))
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
resource "alicloud_log_etl" "this" {
  access_key_id                            = var.access_key_id
  access_key_secret                        = var.access_key_secret
  create_time                              = var.create_time
  description                              = var.description
  display_name                             = var.display_name
  etl_name                                 = var.etl_name
  etl_type                                 = var.etl_type
  from_time                                = var.from_time
  kms_encrypted_access_key_id              = var.kms_encrypted_access_key_id
  kms_encrypted_access_key_secret          = var.kms_encrypted_access_key_secret
  kms_encryption_access_key_id_context     = var.kms_encryption_access_key_id_context
  kms_encryption_access_key_secret_context = var.kms_encryption_access_key_secret_context
  last_modified_time                       = var.last_modified_time
  logstore                                 = var.logstore
  parameters                               = var.parameters
  project                                  = var.project
  role_arn                                 = var.role_arn
  schedule                                 = var.schedule
  script                                   = var.script
  status                                   = var.status
  to_time                                  = var.to_time
  version                                  = var.version

  dynamic "etl_sinks" {
    for_each = var.etl_sinks
    content {
      access_key_id                   = etl_sinks.value["access_key_id"]
      access_key_secret               = etl_sinks.value["access_key_secret"]
      endpoint                        = etl_sinks.value["endpoint"]
      kms_encrypted_access_key_id     = etl_sinks.value["kms_encrypted_access_key_id"]
      kms_encrypted_access_key_secret = etl_sinks.value["kms_encrypted_access_key_secret"]
      logstore                        = etl_sinks.value["logstore"]
      name                            = etl_sinks.value["name"]
      project                         = etl_sinks.value["project"]
      role_arn                        = etl_sinks.value["role_arn"]
      type                            = etl_sinks.value["type"]
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
output "create_time" {
  description = "returns a number"
  value       = alicloud_log_etl.this.create_time
}

output "from_time" {
  description = "returns a number"
  value       = alicloud_log_etl.this.from_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_log_etl.this.id
}

output "last_modified_time" {
  description = "returns a number"
  value       = alicloud_log_etl.this.last_modified_time
}

output "status" {
  description = "returns a string"
  value       = alicloud_log_etl.this.status
}

output "this" {
  value = alicloud_log_etl.this
}
```

[top](#index)