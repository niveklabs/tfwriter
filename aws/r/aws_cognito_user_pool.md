# aws_cognito_user_pool

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
module "aws_cognito_user_pool" {
  source = "./modules/aws/r/aws_cognito_user_pool"

  # alias_attributes - (optional) is a type of set of string
  alias_attributes = []
  # auto_verified_attributes - (optional) is a type of set of string
  auto_verified_attributes = []
  # email_verification_message - (optional) is a type of string
  email_verification_message = null
  # email_verification_subject - (optional) is a type of string
  email_verification_subject = null
  # mfa_configuration - (optional) is a type of string
  mfa_configuration = null
  # name - (required) is a type of string
  name = null
  # sms_authentication_message - (optional) is a type of string
  sms_authentication_message = null
  # sms_verification_message - (optional) is a type of string
  sms_verification_message = null
  # tags - (optional) is a type of map of string
  tags = {}
  # username_attributes - (optional) is a type of list of string
  username_attributes = []

  account_recovery_setting = [{
    recovery_mechanism = [{
      name     = null
      priority = null
    }]
  }]

  admin_create_user_config = [{
    allow_admin_create_user_only = null
    invite_message_template = [{
      email_message = null
      email_subject = null
      sms_message   = null
    }]
  }]

  device_configuration = [{
    challenge_required_on_new_device      = null
    device_only_remembered_on_user_prompt = null
  }]

  email_configuration = [{
    configuration_set      = null
    email_sending_account  = null
    from_email_address     = null
    reply_to_email_address = null
    source_arn             = null
  }]

  lambda_config = [{
    create_auth_challenge          = null
    custom_message                 = null
    define_auth_challenge          = null
    post_authentication            = null
    post_confirmation              = null
    pre_authentication             = null
    pre_sign_up                    = null
    pre_token_generation           = null
    user_migration                 = null
    verify_auth_challenge_response = null
  }]

  password_policy = [{
    minimum_length                   = null
    require_lowercase                = null
    require_numbers                  = null
    require_symbols                  = null
    require_uppercase                = null
    temporary_password_validity_days = null
  }]

  schema = [{
    attribute_data_type      = null
    developer_only_attribute = null
    mutable                  = null
    name                     = null
    number_attribute_constraints = [{
      max_value = null
      min_value = null
    }]
    required = null
    string_attribute_constraints = [{
      max_length = null
      min_length = null
    }]
  }]

  sms_configuration = [{
    external_id    = null
    sns_caller_arn = null
  }]

  software_token_mfa_configuration = [{
    enabled = null
  }]

  user_pool_add_ons = [{
    advanced_security_mode = null
  }]

  username_configuration = [{
    case_sensitive = null
  }]

  verification_message_template = [{
    default_email_option  = null
    email_message         = null
    email_message_by_link = null
    email_subject         = null
    email_subject_by_link = null
    sms_message           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alias_attributes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "auto_verified_attributes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "email_verification_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email_verification_subject" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mfa_configuration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "sms_authentication_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sms_verification_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "username_attributes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "account_recovery_setting" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      recovery_mechanism = set(object(
        {
          name     = string
          priority = number
        }
      ))
    }
  ))
  default = []
}

variable "admin_create_user_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_admin_create_user_only = bool
      invite_message_template = list(object(
        {
          email_message = string
          email_subject = string
          sms_message   = string
        }
      ))
    }
  ))
  default = []
}

variable "device_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      challenge_required_on_new_device      = bool
      device_only_remembered_on_user_prompt = bool
    }
  ))
  default = []
}

variable "email_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      configuration_set      = string
      email_sending_account  = string
      from_email_address     = string
      reply_to_email_address = string
      source_arn             = string
    }
  ))
  default = []
}

variable "lambda_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      create_auth_challenge          = string
      custom_message                 = string
      define_auth_challenge          = string
      post_authentication            = string
      post_confirmation              = string
      pre_authentication             = string
      pre_sign_up                    = string
      pre_token_generation           = string
      user_migration                 = string
      verify_auth_challenge_response = string
    }
  ))
  default = []
}

variable "password_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      minimum_length                   = number
      require_lowercase                = bool
      require_numbers                  = bool
      require_symbols                  = bool
      require_uppercase                = bool
      temporary_password_validity_days = number
    }
  ))
  default = []
}

variable "schema" {
  description = "nested block: NestingSet, min items: 0, max items: 50"
  type = set(object(
    {
      attribute_data_type      = string
      developer_only_attribute = bool
      mutable                  = bool
      name                     = string
      number_attribute_constraints = list(object(
        {
          max_value = string
          min_value = string
        }
      ))
      required = bool
      string_attribute_constraints = list(object(
        {
          max_length = string
          min_length = string
        }
      ))
    }
  ))
  default = []
}

variable "sms_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      external_id    = string
      sns_caller_arn = string
    }
  ))
  default = []
}

variable "software_token_mfa_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
    }
  ))
  default = []
}

variable "user_pool_add_ons" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      advanced_security_mode = string
    }
  ))
  default = []
}

variable "username_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      case_sensitive = bool
    }
  ))
  default = []
}

variable "verification_message_template" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      default_email_option  = string
      email_message         = string
      email_message_by_link = string
      email_subject         = string
      email_subject_by_link = string
      sms_message           = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_cognito_user_pool" "this" {
  alias_attributes           = var.alias_attributes
  auto_verified_attributes   = var.auto_verified_attributes
  email_verification_message = var.email_verification_message
  email_verification_subject = var.email_verification_subject
  mfa_configuration          = var.mfa_configuration
  name                       = var.name
  sms_authentication_message = var.sms_authentication_message
  sms_verification_message   = var.sms_verification_message
  tags                       = var.tags
  username_attributes        = var.username_attributes

  dynamic "account_recovery_setting" {
    for_each = var.account_recovery_setting
    content {

      dynamic "recovery_mechanism" {
        for_each = account_recovery_setting.value.recovery_mechanism
        content {
          name     = recovery_mechanism.value["name"]
          priority = recovery_mechanism.value["priority"]
        }
      }

    }
  }

  dynamic "admin_create_user_config" {
    for_each = var.admin_create_user_config
    content {
      allow_admin_create_user_only = admin_create_user_config.value["allow_admin_create_user_only"]

      dynamic "invite_message_template" {
        for_each = admin_create_user_config.value.invite_message_template
        content {
          email_message = invite_message_template.value["email_message"]
          email_subject = invite_message_template.value["email_subject"]
          sms_message   = invite_message_template.value["sms_message"]
        }
      }

    }
  }

  dynamic "device_configuration" {
    for_each = var.device_configuration
    content {
      challenge_required_on_new_device      = device_configuration.value["challenge_required_on_new_device"]
      device_only_remembered_on_user_prompt = device_configuration.value["device_only_remembered_on_user_prompt"]
    }
  }

  dynamic "email_configuration" {
    for_each = var.email_configuration
    content {
      configuration_set      = email_configuration.value["configuration_set"]
      email_sending_account  = email_configuration.value["email_sending_account"]
      from_email_address     = email_configuration.value["from_email_address"]
      reply_to_email_address = email_configuration.value["reply_to_email_address"]
      source_arn             = email_configuration.value["source_arn"]
    }
  }

  dynamic "lambda_config" {
    for_each = var.lambda_config
    content {
      create_auth_challenge          = lambda_config.value["create_auth_challenge"]
      custom_message                 = lambda_config.value["custom_message"]
      define_auth_challenge          = lambda_config.value["define_auth_challenge"]
      post_authentication            = lambda_config.value["post_authentication"]
      post_confirmation              = lambda_config.value["post_confirmation"]
      pre_authentication             = lambda_config.value["pre_authentication"]
      pre_sign_up                    = lambda_config.value["pre_sign_up"]
      pre_token_generation           = lambda_config.value["pre_token_generation"]
      user_migration                 = lambda_config.value["user_migration"]
      verify_auth_challenge_response = lambda_config.value["verify_auth_challenge_response"]
    }
  }

  dynamic "password_policy" {
    for_each = var.password_policy
    content {
      minimum_length                   = password_policy.value["minimum_length"]
      require_lowercase                = password_policy.value["require_lowercase"]
      require_numbers                  = password_policy.value["require_numbers"]
      require_symbols                  = password_policy.value["require_symbols"]
      require_uppercase                = password_policy.value["require_uppercase"]
      temporary_password_validity_days = password_policy.value["temporary_password_validity_days"]
    }
  }

  dynamic "schema" {
    for_each = var.schema
    content {
      attribute_data_type      = schema.value["attribute_data_type"]
      developer_only_attribute = schema.value["developer_only_attribute"]
      mutable                  = schema.value["mutable"]
      name                     = schema.value["name"]
      required                 = schema.value["required"]

      dynamic "number_attribute_constraints" {
        for_each = schema.value.number_attribute_constraints
        content {
          max_value = number_attribute_constraints.value["max_value"]
          min_value = number_attribute_constraints.value["min_value"]
        }
      }

      dynamic "string_attribute_constraints" {
        for_each = schema.value.string_attribute_constraints
        content {
          max_length = string_attribute_constraints.value["max_length"]
          min_length = string_attribute_constraints.value["min_length"]
        }
      }

    }
  }

  dynamic "sms_configuration" {
    for_each = var.sms_configuration
    content {
      external_id    = sms_configuration.value["external_id"]
      sns_caller_arn = sms_configuration.value["sns_caller_arn"]
    }
  }

  dynamic "software_token_mfa_configuration" {
    for_each = var.software_token_mfa_configuration
    content {
      enabled = software_token_mfa_configuration.value["enabled"]
    }
  }

  dynamic "user_pool_add_ons" {
    for_each = var.user_pool_add_ons
    content {
      advanced_security_mode = user_pool_add_ons.value["advanced_security_mode"]
    }
  }

  dynamic "username_configuration" {
    for_each = var.username_configuration
    content {
      case_sensitive = username_configuration.value["case_sensitive"]
    }
  }

  dynamic "verification_message_template" {
    for_each = var.verification_message_template
    content {
      default_email_option  = verification_message_template.value["default_email_option"]
      email_message         = verification_message_template.value["email_message"]
      email_message_by_link = verification_message_template.value["email_message_by_link"]
      email_subject         = verification_message_template.value["email_subject"]
      email_subject_by_link = verification_message_template.value["email_subject_by_link"]
      sms_message           = verification_message_template.value["sms_message"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_cognito_user_pool.this.arn
}

output "creation_date" {
  description = "returns a string"
  value       = aws_cognito_user_pool.this.creation_date
}

output "email_verification_message" {
  description = "returns a string"
  value       = aws_cognito_user_pool.this.email_verification_message
}

output "email_verification_subject" {
  description = "returns a string"
  value       = aws_cognito_user_pool.this.email_verification_subject
}

output "endpoint" {
  description = "returns a string"
  value       = aws_cognito_user_pool.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = aws_cognito_user_pool.this.id
}

output "last_modified_date" {
  description = "returns a string"
  value       = aws_cognito_user_pool.this.last_modified_date
}

output "sms_verification_message" {
  description = "returns a string"
  value       = aws_cognito_user_pool.this.sms_verification_message
}

output "this" {
  value = aws_cognito_user_pool.this
}
```

[top](#index)