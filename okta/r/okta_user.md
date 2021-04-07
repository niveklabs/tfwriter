# okta_user

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_user" {
  source = "./modules/okta/r/okta_user"

  # admin_roles - (optional) is a type of set of string
  admin_roles = []
  # city - (optional) is a type of string
  city = null
  # cost_center - (optional) is a type of string
  cost_center = null
  # country_code - (optional) is a type of string
  country_code = null
  # custom_profile_attributes - (optional) is a type of string
  custom_profile_attributes = null
  # department - (optional) is a type of string
  department = null
  # display_name - (optional) is a type of string
  display_name = null
  # division - (optional) is a type of string
  division = null
  # email - (required) is a type of string
  email = null
  # employee_number - (optional) is a type of string
  employee_number = null
  # first_name - (required) is a type of string
  first_name = null
  # group_memberships - (optional) is a type of set of string
  group_memberships = []
  # honorific_prefix - (optional) is a type of string
  honorific_prefix = null
  # honorific_suffix - (optional) is a type of string
  honorific_suffix = null
  # last_name - (required) is a type of string
  last_name = null
  # locale - (optional) is a type of string
  locale = null
  # login - (required) is a type of string
  login = null
  # manager - (optional) is a type of string
  manager = null
  # manager_id - (optional) is a type of string
  manager_id = null
  # middle_name - (optional) is a type of string
  middle_name = null
  # mobile_phone - (optional) is a type of string
  mobile_phone = null
  # nick_name - (optional) is a type of string
  nick_name = null
  # organization - (optional) is a type of string
  organization = null
  # password - (optional) is a type of string
  password = null
  # postal_address - (optional) is a type of string
  postal_address = null
  # preferred_language - (optional) is a type of string
  preferred_language = null
  # primary_phone - (optional) is a type of string
  primary_phone = null
  # profile_url - (optional) is a type of string
  profile_url = null
  # recovery_answer - (optional) is a type of string
  recovery_answer = null
  # recovery_question - (optional) is a type of string
  recovery_question = null
  # second_email - (optional) is a type of string
  second_email = null
  # state - (optional) is a type of string
  state = null
  # status - (optional) is a type of string
  status = null
  # street_address - (optional) is a type of string
  street_address = null
  # timezone - (optional) is a type of string
  timezone = null
  # title - (optional) is a type of string
  title = null
  # user_type - (optional) is a type of string
  user_type = null
  # zip_code - (optional) is a type of string
  zip_code = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_roles" {
  description = "(optional) - User Okta admin roles - ie. ['APP_ADMIN', 'USER_ADMIN']"
  type        = set(string)
  default     = null
}

variable "city" {
  description = "(optional) - User city"
  type        = string
  default     = null
}

variable "cost_center" {
  description = "(optional) - User cost center"
  type        = string
  default     = null
}

variable "country_code" {
  description = "(optional) - User country code"
  type        = string
  default     = null
}

variable "custom_profile_attributes" {
  description = "(optional) - JSON formatted custom attributes for a user. It must be JSON due to various types Okta allows."
  type        = string
  default     = null
}

variable "department" {
  description = "(optional) - User department"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - User display name, suitable to show end users"
  type        = string
  default     = null
}

variable "division" {
  description = "(optional) - User division"
  type        = string
  default     = null
}

variable "email" {
  description = "(required) - User primary email address"
  type        = string
}

variable "employee_number" {
  description = "(optional) - User employee number"
  type        = string
  default     = null
}

variable "first_name" {
  description = "(required) - User first name"
  type        = string
}

variable "group_memberships" {
  description = "(optional) - The groups that you want this user to be a part of. This can also be done via the group using the `users` property."
  type        = set(string)
  default     = null
}

variable "honorific_prefix" {
  description = "(optional) - User honorific prefix"
  type        = string
  default     = null
}

variable "honorific_suffix" {
  description = "(optional) - User honorific suffix"
  type        = string
  default     = null
}

variable "last_name" {
  description = "(required) - User last name"
  type        = string
}

variable "locale" {
  description = "(optional) - User default location"
  type        = string
  default     = null
}

variable "login" {
  description = "(required) - User Okta login"
  type        = string
}

variable "manager" {
  description = "(optional) - Manager of User"
  type        = string
  default     = null
}

variable "manager_id" {
  description = "(optional) - Manager ID of User"
  type        = string
  default     = null
}

variable "middle_name" {
  description = "(optional) - User middle name"
  type        = string
  default     = null
}

variable "mobile_phone" {
  description = "(optional) - User mobile phone number"
  type        = string
  default     = null
}

variable "nick_name" {
  description = "(optional) - User nickname"
  type        = string
  default     = null
}

variable "organization" {
  description = "(optional) - User organization"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional) - User Password"
  type        = string
  default     = null
}

variable "postal_address" {
  description = "(optional) - User mailing address"
  type        = string
  default     = null
}

variable "preferred_language" {
  description = "(optional) - User preferred language"
  type        = string
  default     = null
}

variable "primary_phone" {
  description = "(optional) - User primary phone number"
  type        = string
  default     = null
}

variable "profile_url" {
  description = "(optional) - User online profile (web page)"
  type        = string
  default     = null
}

variable "recovery_answer" {
  description = "(optional) - User Password Recovery Answer"
  type        = string
  default     = null
}

variable "recovery_question" {
  description = "(optional) - User Password Recovery Question"
  type        = string
  default     = null
}

variable "second_email" {
  description = "(optional) - User secondary email address, used for account recovery"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional) - User state or region"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional) - The status of the User in Okta - remove to set user back to active/provisioned"
  type        = string
  default     = null
}

variable "street_address" {
  description = "(optional) - User street address"
  type        = string
  default     = null
}

variable "timezone" {
  description = "(optional) - User default timezone"
  type        = string
  default     = null
}

variable "title" {
  description = "(optional) - User title"
  type        = string
  default     = null
}

variable "user_type" {
  description = "(optional) - User employee type"
  type        = string
  default     = null
}

variable "zip_code" {
  description = "(optional) - User zipcode or postal code"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_user" "this" {
  # admin_roles - (optional) is a type of set of string
  admin_roles = var.admin_roles
  # city - (optional) is a type of string
  city = var.city
  # cost_center - (optional) is a type of string
  cost_center = var.cost_center
  # country_code - (optional) is a type of string
  country_code = var.country_code
  # custom_profile_attributes - (optional) is a type of string
  custom_profile_attributes = var.custom_profile_attributes
  # department - (optional) is a type of string
  department = var.department
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # division - (optional) is a type of string
  division = var.division
  # email - (required) is a type of string
  email = var.email
  # employee_number - (optional) is a type of string
  employee_number = var.employee_number
  # first_name - (required) is a type of string
  first_name = var.first_name
  # group_memberships - (optional) is a type of set of string
  group_memberships = var.group_memberships
  # honorific_prefix - (optional) is a type of string
  honorific_prefix = var.honorific_prefix
  # honorific_suffix - (optional) is a type of string
  honorific_suffix = var.honorific_suffix
  # last_name - (required) is a type of string
  last_name = var.last_name
  # locale - (optional) is a type of string
  locale = var.locale
  # login - (required) is a type of string
  login = var.login
  # manager - (optional) is a type of string
  manager = var.manager
  # manager_id - (optional) is a type of string
  manager_id = var.manager_id
  # middle_name - (optional) is a type of string
  middle_name = var.middle_name
  # mobile_phone - (optional) is a type of string
  mobile_phone = var.mobile_phone
  # nick_name - (optional) is a type of string
  nick_name = var.nick_name
  # organization - (optional) is a type of string
  organization = var.organization
  # password - (optional) is a type of string
  password = var.password
  # postal_address - (optional) is a type of string
  postal_address = var.postal_address
  # preferred_language - (optional) is a type of string
  preferred_language = var.preferred_language
  # primary_phone - (optional) is a type of string
  primary_phone = var.primary_phone
  # profile_url - (optional) is a type of string
  profile_url = var.profile_url
  # recovery_answer - (optional) is a type of string
  recovery_answer = var.recovery_answer
  # recovery_question - (optional) is a type of string
  recovery_question = var.recovery_question
  # second_email - (optional) is a type of string
  second_email = var.second_email
  # state - (optional) is a type of string
  state = var.state
  # status - (optional) is a type of string
  status = var.status
  # street_address - (optional) is a type of string
  street_address = var.street_address
  # timezone - (optional) is a type of string
  timezone = var.timezone
  # title - (optional) is a type of string
  title = var.title
  # user_type - (optional) is a type of string
  user_type = var.user_type
  # zip_code - (optional) is a type of string
  zip_code = var.zip_code
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_user.this.id
}

output "raw_status" {
  description = "returns a string"
  value       = okta_user.this.raw_status
}

output "this" {
  value = okta_user.this
}
```

[top](#index)