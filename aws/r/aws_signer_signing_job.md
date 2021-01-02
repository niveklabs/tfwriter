# aws_signer_signing_job

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
module "aws_signer_signing_job" {
  source = [{
    s3 = [{
      bucket  = null
      key     = null
      version = null
    }]
  }]

  # ignore_signing_job_failure - (optional) is a type of bool
  ignore_signing_job_failure = null
  # profile_name - (required) is a type of string
  profile_name = null

  destination = [{
    s3 = [{
      bucket = null
      prefix = null
    }]
  }]

}
```

[top](#index)

### Variables

```terraform
variable "ignore_signing_job_failure" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "profile_name" {
  description = "(required)"
  type        = string
}

variable "destination" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      s3 = list(object(
        {
          bucket = string
          prefix = string
        }
      ))
    }
  ))
}

variable "source" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      s3 = list(object(
        {
          bucket  = string
          key     = string
          version = string
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_signer_signing_job" "this" {
  ignore_signing_job_failure = var.ignore_signing_job_failure
  profile_name               = var.profile_name

  dynamic "destination" {
    for_each = var.destination
    content {

      dynamic "s3" {
        for_each = destination.value.s3
        content {
          bucket = s3.value["bucket"]
          prefix = s3.value["prefix"]
        }
      }

    }
  }

  dynamic "source" {
    for_each = var.source
    content {

      dynamic "s3" {
        for_each = source.value.s3
        content {
          bucket  = s3.value["bucket"]
          key     = s3.value["key"]
          version = s3.value["version"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "completed_at" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.completed_at
}

output "created_at" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.created_at
}

output "id" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.id
}

output "job_id" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.job_id
}

output "job_invoker" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.job_invoker
}

output "job_owner" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.job_owner
}

output "platform_display_name" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.platform_display_name
}

output "platform_id" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.platform_id
}

output "profile_version" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.profile_version
}

output "requested_by" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.requested_by
}

output "revocation_record" {
  description = "returns a list of object"
  value       = aws_signer_signing_job.this.revocation_record
}

output "signature_expires_at" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.signature_expires_at
}

output "signed_object" {
  description = "returns a list of object"
  value       = aws_signer_signing_job.this.signed_object
}

output "status" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.status
}

output "status_reason" {
  description = "returns a string"
  value       = aws_signer_signing_job.this.status_reason
}

output "this" {
  value = aws_signer_signing_job.this
}
```

[top](#index)