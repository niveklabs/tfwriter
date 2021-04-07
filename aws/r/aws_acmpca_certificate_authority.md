# aws_acmpca_certificate_authority

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
module "aws_acmpca_certificate_authority" {
  source = "./modules/aws/r/aws_acmpca_certificate_authority"

  # enabled - (optional) is a type of bool
  enabled = null
  # permanent_deletion_time_in_days - (optional) is a type of number
  permanent_deletion_time_in_days = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null

  certificate_authority_configuration = [{
    key_algorithm     = null
    signing_algorithm = null
    subject = [{
      common_name                  = null
      country                      = null
      distinguished_name_qualifier = null
      generation_qualifier         = null
      given_name                   = null
      initials                     = null
      locality                     = null
      organization                 = null
      organizational_unit          = null
      pseudonym                    = null
      state                        = null
      surname                      = null
      title                        = null
    }]
  }]

  revocation_configuration = [{
    crl_configuration = [{
      custom_cname       = null
      enabled            = null
      expiration_in_days = null
      s3_bucket_name     = null
    }]
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "permanent_deletion_time_in_days" {
  description = "(optional)"
  type        = number
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

variable "certificate_authority_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      key_algorithm     = string
      signing_algorithm = string
      subject = list(object(
        {
          common_name                  = string
          country                      = string
          distinguished_name_qualifier = string
          generation_qualifier         = string
          given_name                   = string
          initials                     = string
          locality                     = string
          organization                 = string
          organizational_unit          = string
          pseudonym                    = string
          state                        = string
          surname                      = string
          title                        = string
        }
      ))
    }
  ))
}

variable "revocation_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      crl_configuration = list(object(
        {
          custom_cname       = string
          enabled            = bool
          expiration_in_days = number
          s3_bucket_name     = string
        }
      ))
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_acmpca_certificate_authority" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # permanent_deletion_time_in_days - (optional) is a type of number
  permanent_deletion_time_in_days = var.permanent_deletion_time_in_days
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (optional) is a type of string
  type = var.type

  dynamic "certificate_authority_configuration" {
    for_each = var.certificate_authority_configuration
    content {
      # key_algorithm - (required) is a type of string
      key_algorithm = certificate_authority_configuration.value["key_algorithm"]
      # signing_algorithm - (required) is a type of string
      signing_algorithm = certificate_authority_configuration.value["signing_algorithm"]

      dynamic "subject" {
        for_each = certificate_authority_configuration.value.subject
        content {
          # common_name - (optional) is a type of string
          common_name = subject.value["common_name"]
          # country - (optional) is a type of string
          country = subject.value["country"]
          # distinguished_name_qualifier - (optional) is a type of string
          distinguished_name_qualifier = subject.value["distinguished_name_qualifier"]
          # generation_qualifier - (optional) is a type of string
          generation_qualifier = subject.value["generation_qualifier"]
          # given_name - (optional) is a type of string
          given_name = subject.value["given_name"]
          # initials - (optional) is a type of string
          initials = subject.value["initials"]
          # locality - (optional) is a type of string
          locality = subject.value["locality"]
          # organization - (optional) is a type of string
          organization = subject.value["organization"]
          # organizational_unit - (optional) is a type of string
          organizational_unit = subject.value["organizational_unit"]
          # pseudonym - (optional) is a type of string
          pseudonym = subject.value["pseudonym"]
          # state - (optional) is a type of string
          state = subject.value["state"]
          # surname - (optional) is a type of string
          surname = subject.value["surname"]
          # title - (optional) is a type of string
          title = subject.value["title"]
        }
      }

    }
  }

  dynamic "revocation_configuration" {
    for_each = var.revocation_configuration
    content {

      dynamic "crl_configuration" {
        for_each = revocation_configuration.value.crl_configuration
        content {
          # custom_cname - (optional) is a type of string
          custom_cname = crl_configuration.value["custom_cname"]
          # enabled - (optional) is a type of bool
          enabled = crl_configuration.value["enabled"]
          # expiration_in_days - (required) is a type of number
          expiration_in_days = crl_configuration.value["expiration_in_days"]
          # s3_bucket_name - (optional) is a type of string
          s3_bucket_name = crl_configuration.value["s3_bucket_name"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_acmpca_certificate_authority.this.arn
}

output "certificate" {
  description = "returns a string"
  value       = aws_acmpca_certificate_authority.this.certificate
}

output "certificate_chain" {
  description = "returns a string"
  value       = aws_acmpca_certificate_authority.this.certificate_chain
}

output "certificate_signing_request" {
  description = "returns a string"
  value       = aws_acmpca_certificate_authority.this.certificate_signing_request
}

output "id" {
  description = "returns a string"
  value       = aws_acmpca_certificate_authority.this.id
}

output "not_after" {
  description = "returns a string"
  value       = aws_acmpca_certificate_authority.this.not_after
}

output "not_before" {
  description = "returns a string"
  value       = aws_acmpca_certificate_authority.this.not_before
}

output "serial" {
  description = "returns a string"
  value       = aws_acmpca_certificate_authority.this.serial
}

output "status" {
  description = "returns a string"
  value       = aws_acmpca_certificate_authority.this.status
}

output "this" {
  value = aws_acmpca_certificate_authority.this
}
```

[top](#index)