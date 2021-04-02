# aws_directory_service_directory

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_directory_service_directory" {
  source = "./modules/aws/d/aws_directory_service_directory"

  # directory_id - (required) is a type of string
  directory_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "directory_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_directory_service_directory" "this" {
  directory_id = var.directory_id
  tags         = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "access_url" {
  description = "returns a string"
  value       = data.aws_directory_service_directory.this.access_url
}

output "alias" {
  description = "returns a string"
  value       = data.aws_directory_service_directory.this.alias
}

output "connect_settings" {
  description = "returns a list of object"
  value       = data.aws_directory_service_directory.this.connect_settings
}

output "description" {
  description = "returns a string"
  value       = data.aws_directory_service_directory.this.description
}

output "dns_ip_addresses" {
  description = "returns a set of string"
  value       = data.aws_directory_service_directory.this.dns_ip_addresses
}

output "edition" {
  description = "returns a string"
  value       = data.aws_directory_service_directory.this.edition
}

output "enable_sso" {
  description = "returns a bool"
  value       = data.aws_directory_service_directory.this.enable_sso
}

output "id" {
  description = "returns a string"
  value       = data.aws_directory_service_directory.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_directory_service_directory.this.name
}

output "security_group_id" {
  description = "returns a string"
  value       = data.aws_directory_service_directory.this.security_group_id
}

output "short_name" {
  description = "returns a string"
  value       = data.aws_directory_service_directory.this.short_name
}

output "size" {
  description = "returns a string"
  value       = data.aws_directory_service_directory.this.size
}

output "type" {
  description = "returns a string"
  value       = data.aws_directory_service_directory.this.type
}

output "vpc_settings" {
  description = "returns a list of object"
  value       = data.aws_directory_service_directory.this.vpc_settings
}

output "this" {
  value = aws_directory_service_directory.this
}
```

[top](#index)