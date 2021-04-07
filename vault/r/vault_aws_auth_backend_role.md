# vault_aws_auth_backend_role

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_aws_auth_backend_role" {
  source = "./modules/vault/r/vault_aws_auth_backend_role"

  # allow_instance_migration - (optional) is a type of bool
  allow_instance_migration = null
  # auth_type - (optional) is a type of string
  auth_type = null
  # backend - (optional) is a type of string
  backend = null
  # bound_account_id - (optional) is a type of string
  bound_account_id = null
  # bound_account_ids - (optional) is a type of set of string
  bound_account_ids = []
  # bound_ami_id - (optional) is a type of string
  bound_ami_id = null
  # bound_ami_ids - (optional) is a type of set of string
  bound_ami_ids = []
  # bound_ec2_instance_id - (optional) is a type of set of string
  bound_ec2_instance_id = []
  # bound_ec2_instance_ids - (optional) is a type of set of string
  bound_ec2_instance_ids = []
  # bound_iam_instance_profile_arn - (optional) is a type of string
  bound_iam_instance_profile_arn = null
  # bound_iam_instance_profile_arns - (optional) is a type of set of string
  bound_iam_instance_profile_arns = []
  # bound_iam_principal_arn - (optional) is a type of string
  bound_iam_principal_arn = null
  # bound_iam_principal_arns - (optional) is a type of set of string
  bound_iam_principal_arns = []
  # bound_iam_role_arn - (optional) is a type of string
  bound_iam_role_arn = null
  # bound_iam_role_arns - (optional) is a type of set of string
  bound_iam_role_arns = []
  # bound_region - (optional) is a type of string
  bound_region = null
  # bound_regions - (optional) is a type of set of string
  bound_regions = []
  # bound_subnet_id - (optional) is a type of string
  bound_subnet_id = null
  # bound_subnet_ids - (optional) is a type of set of string
  bound_subnet_ids = []
  # bound_vpc_id - (optional) is a type of string
  bound_vpc_id = null
  # bound_vpc_ids - (optional) is a type of set of string
  bound_vpc_ids = []
  # disallow_reauthentication - (optional) is a type of bool
  disallow_reauthentication = null
  # inferred_aws_region - (optional) is a type of string
  inferred_aws_region = null
  # inferred_entity_type - (optional) is a type of string
  inferred_entity_type = null
  # max_ttl - (optional) is a type of number
  max_ttl = null
  # period - (optional) is a type of number
  period = null
  # policies - (optional) is a type of set of string
  policies = []
  # resolve_aws_unique_ids - (optional) is a type of bool
  resolve_aws_unique_ids = null
  # role - (required) is a type of string
  role = null
  # role_tag - (optional) is a type of string
  role_tag = null
  # token_bound_cidrs - (optional) is a type of set of string
  token_bound_cidrs = []
  # token_explicit_max_ttl - (optional) is a type of number
  token_explicit_max_ttl = null
  # token_max_ttl - (optional) is a type of number
  token_max_ttl = null
  # token_no_default_policy - (optional) is a type of bool
  token_no_default_policy = null
  # token_num_uses - (optional) is a type of number
  token_num_uses = null
  # token_period - (optional) is a type of number
  token_period = null
  # token_policies - (optional) is a type of set of string
  token_policies = []
  # token_ttl - (optional) is a type of number
  token_ttl = null
  # token_type - (optional) is a type of string
  token_type = null
  # ttl - (optional) is a type of number
  ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_instance_migration" {
  description = "(optional) - When true, allows migration of the underlying instance where the client resides. Use with caution."
  type        = bool
  default     = null
}

variable "auth_type" {
  description = "(optional) - The auth type permitted for this role."
  type        = string
  default     = null
}

variable "backend" {
  description = "(optional) - Unique name of the auth backend to configure."
  type        = string
  default     = null
}

variable "bound_account_id" {
  description = "(optional) - Only EC2 instances with this account ID in their identity document will be permitted to log in."
  type        = string
  default     = null
}

variable "bound_account_ids" {
  description = "(optional) - Only EC2 instances with this account ID in their identity document will be permitted to log in."
  type        = set(string)
  default     = null
}

variable "bound_ami_id" {
  description = "(optional) - Only EC2 instances using this AMI ID will be permitted to log in."
  type        = string
  default     = null
}

variable "bound_ami_ids" {
  description = "(optional) - Only EC2 instances using this AMI ID will be permitted to log in."
  type        = set(string)
  default     = null
}

variable "bound_ec2_instance_id" {
  description = "(optional) - Only EC2 instances that match this instance ID will be permitted to log in."
  type        = set(string)
  default     = null
}

variable "bound_ec2_instance_ids" {
  description = "(optional) - Only EC2 instances that match this instance ID will be permitted to log in."
  type        = set(string)
  default     = null
}

variable "bound_iam_instance_profile_arn" {
  description = "(optional) - Only EC2 instances associated with an IAM instance profile ARN that matches this value will be permitted to log in."
  type        = string
  default     = null
}

variable "bound_iam_instance_profile_arns" {
  description = "(optional) - Only EC2 instances associated with an IAM instance profile ARN that matches this value will be permitted to log in."
  type        = set(string)
  default     = null
}

variable "bound_iam_principal_arn" {
  description = "(optional) - The IAM principal that must be authenticated using the iam auth method."
  type        = string
  default     = null
}

variable "bound_iam_principal_arns" {
  description = "(optional) - The IAM principal that must be authenticated using the iam auth method."
  type        = set(string)
  default     = null
}

variable "bound_iam_role_arn" {
  description = "(optional) - Only EC2 instances that match this IAM role ARN will be permitted to log in."
  type        = string
  default     = null
}

variable "bound_iam_role_arns" {
  description = "(optional) - Only EC2 instances that match this IAM role ARN will be permitted to log in."
  type        = set(string)
  default     = null
}

variable "bound_region" {
  description = "(optional) - Only EC2 instances in this region will be permitted to log in."
  type        = string
  default     = null
}

variable "bound_regions" {
  description = "(optional) - Only EC2 instances in this region will be permitted to log in."
  type        = set(string)
  default     = null
}

variable "bound_subnet_id" {
  description = "(optional) - Only EC2 instances associated with this subnet ID will be permitted to log in."
  type        = string
  default     = null
}

variable "bound_subnet_ids" {
  description = "(optional) - Only EC2 instances associated with this subnet ID will be permitted to log in."
  type        = set(string)
  default     = null
}

variable "bound_vpc_id" {
  description = "(optional) - Only EC2 instances associated with this VPC ID will be permitted to log in."
  type        = string
  default     = null
}

variable "bound_vpc_ids" {
  description = "(optional) - Only EC2 instances associated with this VPC ID will be permitted to log in."
  type        = set(string)
  default     = null
}

variable "disallow_reauthentication" {
  description = "(optional) - When true, only allows a single token to be granted per instance ID."
  type        = bool
  default     = null
}

variable "inferred_aws_region" {
  description = "(optional) - The region to search for the inferred entities in."
  type        = string
  default     = null
}

variable "inferred_entity_type" {
  description = "(optional) - The type of inferencing Vault should do."
  type        = string
  default     = null
}

variable "max_ttl" {
  description = "(optional) - The maximum allowed lifetime of tokens issued using this role, provided as the number of seconds."
  type        = number
  default     = null
}

variable "period" {
  description = "(optional) - If set, indicates that the token generated using this role should never expire. The token should be renewed within the duration specified by this value. At each renewal, the token's TTL will be set to the value of this field. The maximum allowed lifetime of token issued using this role. Specified as a number of seconds."
  type        = number
  default     = null
}

variable "policies" {
  description = "(optional) - Policies to be set on tokens issued using this role."
  type        = set(string)
  default     = null
}

variable "resolve_aws_unique_ids" {
  description = "(optional) - Whether or not Vault should resolve the bound_iam_principal_arn to an AWS Unique ID. When true, deleting a principal and recreating it with the same name won't automatically grant the new principal the same roles in Vault that the old principal had."
  type        = bool
  default     = null
}

variable "role" {
  description = "(required) - Name of the role."
  type        = string
}

variable "role_tag" {
  description = "(optional) - The key of the tag on EC2 instance to use for role tags."
  type        = string
  default     = null
}

variable "token_bound_cidrs" {
  description = "(optional) - Specifies the blocks of IP addresses which are allowed to use the generated token"
  type        = set(string)
  default     = null
}

variable "token_explicit_max_ttl" {
  description = "(optional) - Generated Token's Explicit Maximum TTL in seconds"
  type        = number
  default     = null
}

variable "token_max_ttl" {
  description = "(optional) - The maximum lifetime of the generated token"
  type        = number
  default     = null
}

variable "token_no_default_policy" {
  description = "(optional) - If true, the 'default' policy will not automatically be added to generated tokens"
  type        = bool
  default     = null
}

variable "token_num_uses" {
  description = "(optional) - The maximum number of times a token may be used, a value of zero means unlimited"
  type        = number
  default     = null
}

variable "token_period" {
  description = "(optional) - Generated Token's Period"
  type        = number
  default     = null
}

variable "token_policies" {
  description = "(optional) - Generated Token's Policies"
  type        = set(string)
  default     = null
}

variable "token_ttl" {
  description = "(optional) - The initial ttl of the token to generate in seconds"
  type        = number
  default     = null
}

variable "token_type" {
  description = "(optional) - The type of token to generate, service or batch"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional) - The TTL period of tokens issued using this role, provided as the number of seconds."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_aws_auth_backend_role" "this" {
  # allow_instance_migration - (optional) is a type of bool
  allow_instance_migration = var.allow_instance_migration
  # auth_type - (optional) is a type of string
  auth_type = var.auth_type
  # backend - (optional) is a type of string
  backend = var.backend
  # bound_account_id - (optional) is a type of string
  bound_account_id = var.bound_account_id
  # bound_account_ids - (optional) is a type of set of string
  bound_account_ids = var.bound_account_ids
  # bound_ami_id - (optional) is a type of string
  bound_ami_id = var.bound_ami_id
  # bound_ami_ids - (optional) is a type of set of string
  bound_ami_ids = var.bound_ami_ids
  # bound_ec2_instance_id - (optional) is a type of set of string
  bound_ec2_instance_id = var.bound_ec2_instance_id
  # bound_ec2_instance_ids - (optional) is a type of set of string
  bound_ec2_instance_ids = var.bound_ec2_instance_ids
  # bound_iam_instance_profile_arn - (optional) is a type of string
  bound_iam_instance_profile_arn = var.bound_iam_instance_profile_arn
  # bound_iam_instance_profile_arns - (optional) is a type of set of string
  bound_iam_instance_profile_arns = var.bound_iam_instance_profile_arns
  # bound_iam_principal_arn - (optional) is a type of string
  bound_iam_principal_arn = var.bound_iam_principal_arn
  # bound_iam_principal_arns - (optional) is a type of set of string
  bound_iam_principal_arns = var.bound_iam_principal_arns
  # bound_iam_role_arn - (optional) is a type of string
  bound_iam_role_arn = var.bound_iam_role_arn
  # bound_iam_role_arns - (optional) is a type of set of string
  bound_iam_role_arns = var.bound_iam_role_arns
  # bound_region - (optional) is a type of string
  bound_region = var.bound_region
  # bound_regions - (optional) is a type of set of string
  bound_regions = var.bound_regions
  # bound_subnet_id - (optional) is a type of string
  bound_subnet_id = var.bound_subnet_id
  # bound_subnet_ids - (optional) is a type of set of string
  bound_subnet_ids = var.bound_subnet_ids
  # bound_vpc_id - (optional) is a type of string
  bound_vpc_id = var.bound_vpc_id
  # bound_vpc_ids - (optional) is a type of set of string
  bound_vpc_ids = var.bound_vpc_ids
  # disallow_reauthentication - (optional) is a type of bool
  disallow_reauthentication = var.disallow_reauthentication
  # inferred_aws_region - (optional) is a type of string
  inferred_aws_region = var.inferred_aws_region
  # inferred_entity_type - (optional) is a type of string
  inferred_entity_type = var.inferred_entity_type
  # max_ttl - (optional) is a type of number
  max_ttl = var.max_ttl
  # period - (optional) is a type of number
  period = var.period
  # policies - (optional) is a type of set of string
  policies = var.policies
  # resolve_aws_unique_ids - (optional) is a type of bool
  resolve_aws_unique_ids = var.resolve_aws_unique_ids
  # role - (required) is a type of string
  role = var.role
  # role_tag - (optional) is a type of string
  role_tag = var.role_tag
  # token_bound_cidrs - (optional) is a type of set of string
  token_bound_cidrs = var.token_bound_cidrs
  # token_explicit_max_ttl - (optional) is a type of number
  token_explicit_max_ttl = var.token_explicit_max_ttl
  # token_max_ttl - (optional) is a type of number
  token_max_ttl = var.token_max_ttl
  # token_no_default_policy - (optional) is a type of bool
  token_no_default_policy = var.token_no_default_policy
  # token_num_uses - (optional) is a type of number
  token_num_uses = var.token_num_uses
  # token_period - (optional) is a type of number
  token_period = var.token_period
  # token_policies - (optional) is a type of set of string
  token_policies = var.token_policies
  # token_ttl - (optional) is a type of number
  token_ttl = var.token_ttl
  # token_type - (optional) is a type of string
  token_type = var.token_type
  # ttl - (optional) is a type of number
  ttl = var.ttl
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_aws_auth_backend_role.this.id
}

output "this" {
  value = vault_aws_auth_backend_role.this
}
```

[top](#index)