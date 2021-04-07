# prismacloud_cloud_account

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_cloud_account" {
  source = "./modules/prismacloud/r/prismacloud_cloud_account"


  alibaba_cloud = [{
    account_id = null
    enabled    = null
    group_ids  = []
    name       = null
    ram_arn    = null
  }]

  aws = [{
    account_id      = null
    account_type    = null
    enabled         = null
    external_id     = null
    group_ids       = []
    name            = null
    protection_mode = null
    role_arn        = null
  }]

  azure = [{
    account_id           = null
    account_type         = null
    client_id            = null
    enabled              = null
    group_ids            = []
    key                  = null
    monitor_flow_logs    = null
    name                 = null
    protection_mode      = null
    service_principal_id = null
    tenant_id            = null
  }]

  gcp = [{
    account_id               = null
    account_type             = null
    compression_enabled      = null
    credentials_json         = null
    dataflow_enabled_project = null
    enabled                  = null
    flow_log_storage_bucket  = null
    group_ids                = []
    name                     = null
    protection_mode          = null
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
variable "alibaba_cloud" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account_id = string
      enabled    = bool
      group_ids  = list(string)
      name       = string
      ram_arn    = string
    }
  ))
  default = []
}

variable "aws" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account_id      = string
      account_type    = string
      enabled         = bool
      external_id     = string
      group_ids       = list(string)
      name            = string
      protection_mode = string
      role_arn        = string
    }
  ))
  default = []
}

variable "azure" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account_id           = string
      account_type         = string
      client_id            = string
      enabled              = bool
      group_ids            = list(string)
      key                  = string
      monitor_flow_logs    = bool
      name                 = string
      protection_mode      = string
      service_principal_id = string
      tenant_id            = string
    }
  ))
  default = []
}

variable "gcp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account_id               = string
      account_type             = string
      compression_enabled      = bool
      credentials_json         = string
      dataflow_enabled_project = string
      enabled                  = bool
      flow_log_storage_bucket  = string
      group_ids                = list(string)
      name                     = string
      protection_mode          = string
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
resource "prismacloud_cloud_account" "this" {

  dynamic "alibaba_cloud" {
    for_each = var.alibaba_cloud
    content {
      # account_id - (required) is a type of string
      account_id = alibaba_cloud.value["account_id"]
      # enabled - (optional) is a type of bool
      enabled = alibaba_cloud.value["enabled"]
      # group_ids - (required) is a type of list of string
      group_ids = alibaba_cloud.value["group_ids"]
      # name - (required) is a type of string
      name = alibaba_cloud.value["name"]
      # ram_arn - (required) is a type of string
      ram_arn = alibaba_cloud.value["ram_arn"]
    }
  }

  dynamic "aws" {
    for_each = var.aws
    content {
      # account_id - (required) is a type of string
      account_id = aws.value["account_id"]
      # account_type - (optional) is a type of string
      account_type = aws.value["account_type"]
      # enabled - (optional) is a type of bool
      enabled = aws.value["enabled"]
      # external_id - (required) is a type of string
      external_id = aws.value["external_id"]
      # group_ids - (required) is a type of list of string
      group_ids = aws.value["group_ids"]
      # name - (required) is a type of string
      name = aws.value["name"]
      # protection_mode - (optional) is a type of string
      protection_mode = aws.value["protection_mode"]
      # role_arn - (required) is a type of string
      role_arn = aws.value["role_arn"]
    }
  }

  dynamic "azure" {
    for_each = var.azure
    content {
      # account_id - (required) is a type of string
      account_id = azure.value["account_id"]
      # account_type - (optional) is a type of string
      account_type = azure.value["account_type"]
      # client_id - (required) is a type of string
      client_id = azure.value["client_id"]
      # enabled - (optional) is a type of bool
      enabled = azure.value["enabled"]
      # group_ids - (required) is a type of list of string
      group_ids = azure.value["group_ids"]
      # key - (required) is a type of string
      key = azure.value["key"]
      # monitor_flow_logs - (optional) is a type of bool
      monitor_flow_logs = azure.value["monitor_flow_logs"]
      # name - (required) is a type of string
      name = azure.value["name"]
      # protection_mode - (optional) is a type of string
      protection_mode = azure.value["protection_mode"]
      # service_principal_id - (required) is a type of string
      service_principal_id = azure.value["service_principal_id"]
      # tenant_id - (required) is a type of string
      tenant_id = azure.value["tenant_id"]
    }
  }

  dynamic "gcp" {
    for_each = var.gcp
    content {
      # account_id - (required) is a type of string
      account_id = gcp.value["account_id"]
      # account_type - (optional) is a type of string
      account_type = gcp.value["account_type"]
      # compression_enabled - (optional) is a type of bool
      compression_enabled = gcp.value["compression_enabled"]
      # credentials_json - (required) is a type of string
      credentials_json = gcp.value["credentials_json"]
      # dataflow_enabled_project - (optional) is a type of string
      dataflow_enabled_project = gcp.value["dataflow_enabled_project"]
      # enabled - (optional) is a type of bool
      enabled = gcp.value["enabled"]
      # flow_log_storage_bucket - (optional) is a type of string
      flow_log_storage_bucket = gcp.value["flow_log_storage_bucket"]
      # group_ids - (required) is a type of list of string
      group_ids = gcp.value["group_ids"]
      # name - (required) is a type of string
      name = gcp.value["name"]
      # protection_mode - (optional) is a type of string
      protection_mode = gcp.value["protection_mode"]
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
output "id" {
  description = "returns a string"
  value       = prismacloud_cloud_account.this.id
}

output "this" {
  value = prismacloud_cloud_account.this
}
```

[top](#index)