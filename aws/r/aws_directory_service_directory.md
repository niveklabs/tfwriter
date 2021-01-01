# aws_directory_service_directory

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_directory_service_directory" {
  source = "./modules/aws/r/aws_directory_service_directory"

  # alias - (optional) is a type of string
  alias = null
  # description - (optional) is a type of string
  description = null
  # edition - (optional) is a type of string
  edition = null
  # enable_sso - (optional) is a type of bool
  enable_sso = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # short_name - (optional) is a type of string
  short_name = null
  # size - (optional) is a type of string
  size = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null

  connect_settings = [{
    availability_zones = []
    connect_ips        = []
    customer_dns_ips   = []
    customer_username  = null
    subnet_ids         = []
    vpc_id             = null
  }]

  vpc_settings = [{
    availability_zones = []
    subnet_ids         = []
    vpc_id             = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "edition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_sso" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "short_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "connect_settings" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      availability_zones = set(string)
      connect_ips        = set(string)
      customer_dns_ips   = set(string)
      customer_username  = string
      subnet_ids         = set(string)
      vpc_id             = string
    }
  ))
  default = []
}

variable "vpc_settings" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      availability_zones = set(string)
      subnet_ids         = set(string)
      vpc_id             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_directory_service_directory" "this" {
  alias       = var.alias
  description = var.description
  edition     = var.edition
  enable_sso  = var.enable_sso
  name        = var.name
  password    = var.password
  short_name  = var.short_name
  size        = var.size
  tags        = var.tags
  type        = var.type

  dynamic "connect_settings" {
    for_each = var.connect_settings
    content {
      customer_dns_ips  = connect_settings.value["customer_dns_ips"]
      customer_username = connect_settings.value["customer_username"]
      subnet_ids        = connect_settings.value["subnet_ids"]
      vpc_id            = connect_settings.value["vpc_id"]
    }
  }

  dynamic "vpc_settings" {
    for_each = var.vpc_settings
    content {
      subnet_ids = vpc_settings.value["subnet_ids"]
      vpc_id     = vpc_settings.value["vpc_id"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "access_url" {
  description = "returns a string"
  value       = aws_directory_service_directory.this.access_url
}

output "alias" {
  description = "returns a string"
  value       = aws_directory_service_directory.this.alias
}

output "dns_ip_addresses" {
  description = "returns a set of string"
  value       = aws_directory_service_directory.this.dns_ip_addresses
}

output "edition" {
  description = "returns a string"
  value       = aws_directory_service_directory.this.edition
}

output "id" {
  description = "returns a string"
  value       = aws_directory_service_directory.this.id
}

output "security_group_id" {
  description = "returns a string"
  value       = aws_directory_service_directory.this.security_group_id
}

output "short_name" {
  description = "returns a string"
  value       = aws_directory_service_directory.this.short_name
}

output "size" {
  description = "returns a string"
  value       = aws_directory_service_directory.this.size
}

output "this" {
  value = aws_directory_service_directory.this
}
```

[top](#index)