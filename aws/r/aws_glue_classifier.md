# aws_glue_classifier

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
module "aws_glue_classifier" {
  source = "./modules/aws/r/aws_glue_classifier"

  # name - (required) is a type of string
  name = null

  csv_classifier = [{
    allow_single_column    = null
    contains_header        = null
    delimiter              = null
    disable_value_trimming = null
    header                 = []
    quote_symbol           = null
  }]

  grok_classifier = [{
    classification  = null
    custom_patterns = null
    grok_pattern    = null
  }]

  json_classifier = [{
    json_path = null
  }]

  xml_classifier = [{
    classification = null
    row_tag        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "csv_classifier" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_single_column    = bool
      contains_header        = string
      delimiter              = string
      disable_value_trimming = bool
      header                 = list(string)
      quote_symbol           = string
    }
  ))
  default = []
}

variable "grok_classifier" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      classification  = string
      custom_patterns = string
      grok_pattern    = string
    }
  ))
  default = []
}

variable "json_classifier" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      json_path = string
    }
  ))
  default = []
}

variable "xml_classifier" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      classification = string
      row_tag        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_glue_classifier" "this" {
  # name - (required) is a type of string
  name = var.name

  dynamic "csv_classifier" {
    for_each = var.csv_classifier
    content {
      # allow_single_column - (optional) is a type of bool
      allow_single_column = csv_classifier.value["allow_single_column"]
      # contains_header - (optional) is a type of string
      contains_header = csv_classifier.value["contains_header"]
      # delimiter - (optional) is a type of string
      delimiter = csv_classifier.value["delimiter"]
      # disable_value_trimming - (optional) is a type of bool
      disable_value_trimming = csv_classifier.value["disable_value_trimming"]
      # header - (optional) is a type of list of string
      header = csv_classifier.value["header"]
      # quote_symbol - (optional) is a type of string
      quote_symbol = csv_classifier.value["quote_symbol"]
    }
  }

  dynamic "grok_classifier" {
    for_each = var.grok_classifier
    content {
      # classification - (required) is a type of string
      classification = grok_classifier.value["classification"]
      # custom_patterns - (optional) is a type of string
      custom_patterns = grok_classifier.value["custom_patterns"]
      # grok_pattern - (required) is a type of string
      grok_pattern = grok_classifier.value["grok_pattern"]
    }
  }

  dynamic "json_classifier" {
    for_each = var.json_classifier
    content {
      # json_path - (required) is a type of string
      json_path = json_classifier.value["json_path"]
    }
  }

  dynamic "xml_classifier" {
    for_each = var.xml_classifier
    content {
      # classification - (required) is a type of string
      classification = xml_classifier.value["classification"]
      # row_tag - (required) is a type of string
      row_tag = xml_classifier.value["row_tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_glue_classifier.this.id
}

output "this" {
  value = aws_glue_classifier.this
}
```

[top](#index)