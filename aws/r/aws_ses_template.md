# aws_ses_template

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
module "aws_ses_template" {
  source = "./modules/aws/r/aws_ses_template"

  # html - (optional) is a type of string
  html = null
  # name - (required) is a type of string
  name = null
  # subject - (optional) is a type of string
  subject = null
  # text - (optional) is a type of string
  text = null
}
```

[top](#index)

### Variables

```hcl
variable "html" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "subject" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "text" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_ses_template" "this" {
  html    = var.html
  name    = var.name
  subject = var.subject
  text    = var.text
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_ses_template.this.id
}

output "this" {
  value = aws_ses_template.this
}
```

[top](#index)