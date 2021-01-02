# aws_networkfirewall_logging_configuration

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_networkfirewall_logging_configuration" {
  source = "./modules/aws/r/aws_networkfirewall_logging_configuration"

  # firewall_arn - (required) is a type of string
  firewall_arn = null

  logging_configuration = [{
    log_destination_config = [{
      log_destination      = {}
      log_destination_type = null
      log_type             = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "firewall_arn" {
  description = "(required)"
  type        = string
}

variable "logging_configuration" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      log_destination_config = set(object(
        {
          log_destination      = map(string)
          log_destination_type = string
          log_type             = string
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_networkfirewall_logging_configuration" "this" {
  firewall_arn = var.firewall_arn

  dynamic "logging_configuration" {
    for_each = var.logging_configuration
    content {

      dynamic "log_destination_config" {
        for_each = logging_configuration.value.log_destination_config
        content {
          log_destination      = log_destination_config.value["log_destination"]
          log_destination_type = log_destination_config.value["log_destination_type"]
          log_type             = log_destination_config.value["log_type"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_networkfirewall_logging_configuration.this.id
}

output "this" {
  value = aws_networkfirewall_logging_configuration.this
}
```

[top](#index)