# datadog_logs_archive

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_logs_archive" {
  source = "./modules/datadog/r/datadog_logs_archive"

  # azure - (optional) is a type of map of string
  azure = {}
  # gcs - (optional) is a type of map of string
  gcs = {}
  # include_tags - (optional) is a type of bool
  include_tags = null
  # name - (required) is a type of string
  name = null
  # query - (required) is a type of string
  query = null
  # rehydration_tags - (optional) is a type of list of string
  rehydration_tags = []
  # s3 - (optional) is a type of map of string
  s3 = {}

  azure_archive = [{
    client_id       = null
    container       = null
    path            = null
    storage_account = null
    tenant_id       = null
  }]

  gcs_archive = [{
    bucket       = null
    client_email = null
    path         = null
    project_id   = null
  }]

  s3_archive = [{
    account_id = null
    bucket     = null
    path       = null
    role_name  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "azure" {
  description = "(optional) - Definition of an azure archive. **Deprecated.** Define `azure_archive` list with one element instead."
  type        = map(string)
  default     = null
}

variable "gcs" {
  description = "(optional) - Definition of a GCS archive. **Deprecated.** Define `gcs_archive` list with one element instead."
  type        = map(string)
  default     = null
}

variable "include_tags" {
  description = "(optional) - To store the tags in the archive, set the value `true`. If it is set to `false`, the tags will be dropped when the logs are sent to the archive."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Your archive name."
  type        = string
}

variable "query" {
  description = "(required) - The archive query/filter. Logs matching this query are included in the archive."
  type        = string
}

variable "rehydration_tags" {
  description = "(optional) - An array of tags to add to rehydrated logs from an archive."
  type        = list(string)
  default     = null
}

variable "s3" {
  description = "(optional) - Definition of an s3 archive. **Deprecated.** Define `s3_archive` list with one element instead."
  type        = map(string)
  default     = null
}

variable "azure_archive" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_id       = string
      container       = string
      path            = string
      storage_account = string
      tenant_id       = string
    }
  ))
  default = []
}

variable "gcs_archive" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket       = string
      client_email = string
      path         = string
      project_id   = string
    }
  ))
  default = []
}

variable "s3_archive" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account_id = string
      bucket     = string
      path       = string
      role_name  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "datadog_logs_archive" "this" {
  # azure - (optional) is a type of map of string
  azure = var.azure
  # gcs - (optional) is a type of map of string
  gcs = var.gcs
  # include_tags - (optional) is a type of bool
  include_tags = var.include_tags
  # name - (required) is a type of string
  name = var.name
  # query - (required) is a type of string
  query = var.query
  # rehydration_tags - (optional) is a type of list of string
  rehydration_tags = var.rehydration_tags
  # s3 - (optional) is a type of map of string
  s3 = var.s3

  dynamic "azure_archive" {
    for_each = var.azure_archive
    content {
      # client_id - (required) is a type of string
      client_id = azure_archive.value["client_id"]
      # container - (required) is a type of string
      container = azure_archive.value["container"]
      # path - (optional) is a type of string
      path = azure_archive.value["path"]
      # storage_account - (required) is a type of string
      storage_account = azure_archive.value["storage_account"]
      # tenant_id - (required) is a type of string
      tenant_id = azure_archive.value["tenant_id"]
    }
  }

  dynamic "gcs_archive" {
    for_each = var.gcs_archive
    content {
      # bucket - (required) is a type of string
      bucket = gcs_archive.value["bucket"]
      # client_email - (required) is a type of string
      client_email = gcs_archive.value["client_email"]
      # path - (required) is a type of string
      path = gcs_archive.value["path"]
      # project_id - (required) is a type of string
      project_id = gcs_archive.value["project_id"]
    }
  }

  dynamic "s3_archive" {
    for_each = var.s3_archive
    content {
      # account_id - (required) is a type of string
      account_id = s3_archive.value["account_id"]
      # bucket - (required) is a type of string
      bucket = s3_archive.value["bucket"]
      # path - (required) is a type of string
      path = s3_archive.value["path"]
      # role_name - (required) is a type of string
      role_name = s3_archive.value["role_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_logs_archive.this.id
}

output "this" {
  value = datadog_logs_archive.this
}
```

[top](#index)