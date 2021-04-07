# prismacloud_cloud_account

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/prismacloud/d/prismacloud_cloud_account"

  # account_id - (optional) is a type of string
  account_id = null
  # cloud_type - (required) is a type of string
  cloud_type = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional) - The cloud account ID"
  type        = string
  default     = null
}

variable "cloud_type" {
  description = "(required) - The cloud type"
  type        = string
}

variable "name" {
  description = "(optional) - The cloud account name"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "prismacloud_cloud_account" "this" {
  # account_id - (optional) is a type of string
  account_id = var.account_id
  # cloud_type - (required) is a type of string
  cloud_type = var.cloud_type
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = data.prismacloud_cloud_account.this.account_id
}

output "alibaba_cloud" {
  description = "returns a list of object"
  value       = data.prismacloud_cloud_account.this.alibaba_cloud
}

output "aws" {
  description = "returns a list of object"
  value       = data.prismacloud_cloud_account.this.aws
}

output "azure" {
  description = "returns a list of object"
  value       = data.prismacloud_cloud_account.this.azure
}

output "gcp" {
  description = "returns a list of object"
  value       = data.prismacloud_cloud_account.this.gcp
}

output "id" {
  description = "returns a string"
  value       = data.prismacloud_cloud_account.this.id
}

output "name" {
  description = "returns a string"
  value       = data.prismacloud_cloud_account.this.name
}

output "this" {
  value = prismacloud_cloud_account.this
}
```

[top](#index)