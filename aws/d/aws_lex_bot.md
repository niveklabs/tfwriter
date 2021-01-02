# aws_lex_bot

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_lex_bot" {
  source = "./modules/aws/d/aws_lex_bot"

  # name - (required) is a type of string
  name = null
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_lex_bot" "this" {
  name    = var.name
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_lex_bot.this.arn
}

output "checksum" {
  description = "returns a string"
  value       = data.aws_lex_bot.this.checksum
}

output "child_directed" {
  description = "returns a bool"
  value       = data.aws_lex_bot.this.child_directed
}

output "created_date" {
  description = "returns a string"
  value       = data.aws_lex_bot.this.created_date
}

output "description" {
  description = "returns a string"
  value       = data.aws_lex_bot.this.description
}

output "detect_sentiment" {
  description = "returns a bool"
  value       = data.aws_lex_bot.this.detect_sentiment
}

output "enable_model_improvements" {
  description = "returns a bool"
  value       = data.aws_lex_bot.this.enable_model_improvements
}

output "failure_reason" {
  description = "returns a string"
  value       = data.aws_lex_bot.this.failure_reason
}

output "id" {
  description = "returns a string"
  value       = data.aws_lex_bot.this.id
}

output "idle_session_ttl_in_seconds" {
  description = "returns a number"
  value       = data.aws_lex_bot.this.idle_session_ttl_in_seconds
}

output "last_updated_date" {
  description = "returns a string"
  value       = data.aws_lex_bot.this.last_updated_date
}

output "locale" {
  description = "returns a string"
  value       = data.aws_lex_bot.this.locale
}

output "nlu_intent_confidence_threshold" {
  description = "returns a number"
  value       = data.aws_lex_bot.this.nlu_intent_confidence_threshold
}

output "status" {
  description = "returns a string"
  value       = data.aws_lex_bot.this.status
}

output "voice_id" {
  description = "returns a string"
  value       = data.aws_lex_bot.this.voice_id
}

output "this" {
  value = aws_lex_bot.this
}
```

[top](#index)