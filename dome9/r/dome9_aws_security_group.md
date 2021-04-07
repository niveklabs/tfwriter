# dome9_aws_security_group

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.21.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_aws_security_group" {
  source = "./modules/dome9/r/dome9_aws_security_group"

  # aws_region_id - (optional) is a type of string
  aws_region_id = null
  # description - (optional) is a type of string
  description = null
  # dome9_cloud_account_id - (required) is a type of string
  dome9_cloud_account_id = null
  # dome9_security_group_name - (required) is a type of string
  dome9_security_group_name = null
  # is_protected - (optional) is a type of bool
  is_protected = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # vpc_name - (optional) is a type of string
  vpc_name = null

  services = [{
    inbound = [{
      description   = null
      name          = null
      open_for_all  = null
      port          = null
      protocol_type = null
      scope = [{
        data = {}
        type = null
      }]
    }]
    outbound = [{
      description   = null
      name          = null
      open_for_all  = null
      port          = null
      protocol_type = null
      scope = [{
        data = {}
        type = null
      }]
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "aws_region_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dome9_cloud_account_id" {
  description = "(required)"
  type        = string
}

variable "dome9_security_group_name" {
  description = "(required)"
  type        = string
}

variable "is_protected" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "services" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      inbound = set(object(
        {
          description   = string
          name          = string
          open_for_all  = bool
          port          = string
          protocol_type = string
          scope = set(object(
            {
              data = map(string)
              type = string
            }
          ))
        }
      ))
      outbound = set(object(
        {
          description   = string
          name          = string
          open_for_all  = bool
          port          = string
          protocol_type = string
          scope = set(object(
            {
              data = map(string)
              type = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "dome9_aws_security_group" "this" {
  # aws_region_id - (optional) is a type of string
  aws_region_id = var.aws_region_id
  # description - (optional) is a type of string
  description = var.description
  # dome9_cloud_account_id - (required) is a type of string
  dome9_cloud_account_id = var.dome9_cloud_account_id
  # dome9_security_group_name - (required) is a type of string
  dome9_security_group_name = var.dome9_security_group_name
  # is_protected - (optional) is a type of bool
  is_protected = var.is_protected
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
  # vpc_name - (optional) is a type of string
  vpc_name = var.vpc_name

  dynamic "services" {
    for_each = var.services
    content {

      dynamic "inbound" {
        for_each = services.value.inbound
        content {
          # description - (optional) is a type of string
          description = inbound.value["description"]
          # name - (optional) is a type of string
          name = inbound.value["name"]
          # open_for_all - (optional) is a type of bool
          open_for_all = inbound.value["open_for_all"]
          # port - (optional) is a type of string
          port = inbound.value["port"]
          # protocol_type - (optional) is a type of string
          protocol_type = inbound.value["protocol_type"]

          dynamic "scope" {
            for_each = inbound.value.scope
            content {
              # data - (required) is a type of map of string
              data = scope.value["data"]
              # type - (required) is a type of string
              type = scope.value["type"]
            }
          }

        }
      }

      dynamic "outbound" {
        for_each = services.value.outbound
        content {
          # description - (optional) is a type of string
          description = outbound.value["description"]
          # name - (optional) is a type of string
          name = outbound.value["name"]
          # open_for_all - (optional) is a type of bool
          open_for_all = outbound.value["open_for_all"]
          # port - (optional) is a type of string
          port = outbound.value["port"]
          # protocol_type - (optional) is a type of string
          protocol_type = outbound.value["protocol_type"]

          dynamic "scope" {
            for_each = outbound.value.scope
            content {
              # data - (optional) is a type of map of string
              data = scope.value["data"]
              # type - (optional) is a type of string
              type = scope.value["type"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_account_name" {
  description = "returns a string"
  value       = dome9_aws_security_group.this.cloud_account_name
}

output "external_id" {
  description = "returns a string"
  value       = dome9_aws_security_group.this.external_id
}

output "id" {
  description = "returns a string"
  value       = dome9_aws_security_group.this.id
}

output "is_protected" {
  description = "returns a bool"
  value       = dome9_aws_security_group.this.is_protected
}

output "vpc_id" {
  description = "returns a string"
  value       = dome9_aws_security_group.this.vpc_id
}

output "vpc_name" {
  description = "returns a string"
  value       = dome9_aws_security_group.this.vpc_name
}

output "this" {
  value = dome9_aws_security_group.this
}
```

[top](#index)