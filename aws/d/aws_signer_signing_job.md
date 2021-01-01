# aws_signer_signing_job

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
module "aws_signer_signing_job" {
  source = "./modules/aws/d/aws_signer_signing_job"

  # job_id - (required) is a type of string
  job_id = null
}
```

[top](#index)

### Variables

```hcl
variable "job_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```hcl
data "aws_signer_signing_job" "this" {
  job_id = var.job_id
}
```

[top](#index)

### Outputs

```hcl
output "completed_at" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.completed_at
}

output "created_at" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.created_at
}

output "id" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.id
}

output "job_invoker" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.job_invoker
}

output "job_owner" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.job_owner
}

output "platform_display_name" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.platform_display_name
}

output "platform_id" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.platform_id
}

output "profile_name" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.profile_name
}

output "profile_version" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.profile_version
}

output "requested_by" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.requested_by
}

output "revocation_record" {
  description = "returns a list of object"
  value       = data.aws_signer_signing_job.this.revocation_record
}

output "signature_expires_at" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.signature_expires_at
}

output "signed_object" {
  description = "returns a list of object"
  value       = data.aws_signer_signing_job.this.signed_object
}

output "source" {
  description = "returns a list of object"
  value       = data.aws_signer_signing_job.this.source
}

output "status" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.status
}

output "status_reason" {
  description = "returns a string"
  value       = data.aws_signer_signing_job.this.status_reason
}

output "this" {
  value = aws_signer_signing_job.this
}
```

[top](#index)