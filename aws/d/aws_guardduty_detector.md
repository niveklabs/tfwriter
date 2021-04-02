# aws_guardduty_detector

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
module "aws_guardduty_detector" {
  source = "./modules/aws/d/aws_guardduty_detector"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "aws_guardduty_detector" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "finding_publishing_frequency" {
  description = "returns a string"
  value       = data.aws_guardduty_detector.this.finding_publishing_frequency
}

output "id" {
  description = "returns a string"
  value       = data.aws_guardduty_detector.this.id
}

output "service_role_arn" {
  description = "returns a string"
  value       = data.aws_guardduty_detector.this.service_role_arn
}

output "status" {
  description = "returns a string"
  value       = data.aws_guardduty_detector.this.status
}

output "this" {
  value = aws_guardduty_detector.this
}
```

[top](#index)