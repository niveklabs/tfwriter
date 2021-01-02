# aws_sagemaker_endpoint_configuration

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
module "aws_sagemaker_endpoint_configuration" {
  source = "./modules/aws/r/aws_sagemaker_endpoint_configuration"

  # kms_key_arn - (optional) is a type of string
  kms_key_arn = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  data_capture_config = [{
    capture_content_type_header = [{
      csv_content_types  = []
      json_content_types = []
    }]
    capture_options = [{
      capture_mode = null
    }]
    destination_s3_uri          = null
    enable_capture              = null
    initial_sampling_percentage = null
    kms_key_id                  = null
  }]

  production_variants = [{
    accelerator_type       = null
    initial_instance_count = null
    initial_variant_weight = null
    instance_type          = null
    model_name             = null
    variant_name           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "kms_key_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "data_capture_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      capture_content_type_header = list(object(
        {
          csv_content_types  = set(string)
          json_content_types = set(string)
        }
      ))
      capture_options = list(object(
        {
          capture_mode = string
        }
      ))
      destination_s3_uri          = string
      enable_capture              = bool
      initial_sampling_percentage = number
      kms_key_id                  = string
    }
  ))
  default = []
}

variable "production_variants" {
  description = "nested mode: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      accelerator_type       = string
      initial_instance_count = number
      initial_variant_weight = number
      instance_type          = string
      model_name             = string
      variant_name           = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_sagemaker_endpoint_configuration" "this" {
  kms_key_arn = var.kms_key_arn
  name        = var.name
  tags        = var.tags

  dynamic "data_capture_config" {
    for_each = var.data_capture_config
    content {
      destination_s3_uri          = data_capture_config.value["destination_s3_uri"]
      enable_capture              = data_capture_config.value["enable_capture"]
      initial_sampling_percentage = data_capture_config.value["initial_sampling_percentage"]
      kms_key_id                  = data_capture_config.value["kms_key_id"]

      dynamic "capture_content_type_header" {
        for_each = data_capture_config.value.capture_content_type_header
        content {
          csv_content_types  = capture_content_type_header.value["csv_content_types"]
          json_content_types = capture_content_type_header.value["json_content_types"]
        }
      }

      dynamic "capture_options" {
        for_each = data_capture_config.value.capture_options
        content {
          capture_mode = capture_options.value["capture_mode"]
        }
      }

    }
  }

  dynamic "production_variants" {
    for_each = var.production_variants
    content {
      accelerator_type       = production_variants.value["accelerator_type"]
      initial_instance_count = production_variants.value["initial_instance_count"]
      initial_variant_weight = production_variants.value["initial_variant_weight"]
      instance_type          = production_variants.value["instance_type"]
      model_name             = production_variants.value["model_name"]
      variant_name           = production_variants.value["variant_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sagemaker_endpoint_configuration.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_endpoint_configuration.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_sagemaker_endpoint_configuration.this.name
}

output "this" {
  value = aws_sagemaker_endpoint_configuration.this
}
```

[top](#index)