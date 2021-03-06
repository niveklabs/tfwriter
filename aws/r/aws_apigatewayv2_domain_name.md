# aws_apigatewayv2_domain_name

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
module "aws_apigatewayv2_domain_name" {
  source = "./modules/aws/r/aws_apigatewayv2_domain_name"

  # domain_name - (required) is a type of string
  domain_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  domain_name_configuration = [{
    certificate_arn    = null
    endpoint_type      = null
    hosted_zone_id     = null
    security_policy    = null
    target_domain_name = null
  }]

  mutual_tls_authentication = [{
    truststore_uri     = null
    truststore_version = null
  }]

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "domain_name_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      certificate_arn    = string
      endpoint_type      = string
      hosted_zone_id     = string
      security_policy    = string
      target_domain_name = string
    }
  ))
}

variable "mutual_tls_authentication" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      truststore_uri     = string
      truststore_version = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_apigatewayv2_domain_name" "this" {
  # domain_name - (required) is a type of string
  domain_name = var.domain_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "domain_name_configuration" {
    for_each = var.domain_name_configuration
    content {
      # certificate_arn - (required) is a type of string
      certificate_arn = domain_name_configuration.value["certificate_arn"]
      # endpoint_type - (required) is a type of string
      endpoint_type = domain_name_configuration.value["endpoint_type"]
      # security_policy - (required) is a type of string
      security_policy = domain_name_configuration.value["security_policy"]
    }
  }

  dynamic "mutual_tls_authentication" {
    for_each = var.mutual_tls_authentication
    content {
      # truststore_uri - (required) is a type of string
      truststore_uri = mutual_tls_authentication.value["truststore_uri"]
      # truststore_version - (optional) is a type of string
      truststore_version = mutual_tls_authentication.value["truststore_version"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_mapping_selection_expression" {
  description = "returns a string"
  value       = aws_apigatewayv2_domain_name.this.api_mapping_selection_expression
}

output "arn" {
  description = "returns a string"
  value       = aws_apigatewayv2_domain_name.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_domain_name.this.id
}

output "this" {
  value = aws_apigatewayv2_domain_name.this
}
```

[top](#index)