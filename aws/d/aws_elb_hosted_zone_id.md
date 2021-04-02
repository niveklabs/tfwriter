# aws_elb_hosted_zone_id

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
module "aws_elb_hosted_zone_id" {
  source = "./modules/aws/d/aws_elb_hosted_zone_id"

  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_elb_hosted_zone_id" "this" {
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_elb_hosted_zone_id.this.id
}

output "this" {
  value = aws_elb_hosted_zone_id.this
}
```

[top](#index)