# azuread_user

[back](../azuread.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuread = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuread_user" {
  source = "./modules/azuread/r/azuread_user"

  # account_enabled - (optional) is a type of bool
  account_enabled = null
  # city - (optional) is a type of string
  city = null
  # company_name - (optional) is a type of string
  company_name = null
  # country - (optional) is a type of string
  country = null
  # department - (optional) is a type of string
  department = null
  # display_name - (required) is a type of string
  display_name = null
  # force_password_change - (optional) is a type of bool
  force_password_change = null
  # given_name - (optional) is a type of string
  given_name = null
  # immutable_id - (optional) is a type of string
  immutable_id = null
  # job_title - (optional) is a type of string
  job_title = null
  # mail_nickname - (optional) is a type of string
  mail_nickname = null
  # mobile - (optional) is a type of string
  mobile = null
  # password - (required) is a type of string
  password = null
  # physical_delivery_office_name - (optional) is a type of string
  physical_delivery_office_name = null
  # postal_code - (optional) is a type of string
  postal_code = null
  # state - (optional) is a type of string
  state = null
  # street_address - (optional) is a type of string
  street_address = null
  # surname - (optional) is a type of string
  surname = null
  # usage_location - (optional) is a type of string
  usage_location = null
  # user_principal_name - (required) is a type of string
  user_principal_name = null
}
```

[top](#index)

### Variables

```terraform
variable "account_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "city" {
  description = "(optional) - The city/region in which the user is located; for example, “US” or “UK”."
  type        = string
  default     = null
}

variable "company_name" {
  description = "(optional) - The company name which the user is associated. This property can be useful for describing the company that an external user comes from."
  type        = string
  default     = null
}

variable "country" {
  description = "(optional) - The country/region in which the user is located; for example, “US” or “UK”."
  type        = string
  default     = null
}

variable "department" {
  description = "(optional) - The name for the department in which the user works."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "force_password_change" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "given_name" {
  description = "(optional) - The given name (first name) of the user."
  type        = string
  default     = null
}

variable "immutable_id" {
  description = "(optional) - This must be specified if you are using a federated domain for the user's userPrincipalName (UPN) property when creating a new user account. It is used to associate an on-premises Active Directory user account with their Azure AD user object."
  type        = string
  default     = null
}

variable "job_title" {
  description = "(optional) - The user’s job title."
  type        = string
  default     = null
}

variable "mail_nickname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mobile" {
  description = "(optional) - The primary cellular telephone number for the user."
  type        = string
  default     = null
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "physical_delivery_office_name" {
  description = "(optional) - The office location in the user's place of business."
  type        = string
  default     = null
}

variable "postal_code" {
  description = "(optional) - The postal code for the user's postal address. The postal code is specific to the user's country/region. In the United States of America, this attribute contains the ZIP code."
  type        = string
  default     = null
}

variable "state" {
  description = "(optional) - The state or province in the user's address."
  type        = string
  default     = null
}

variable "street_address" {
  description = "(optional) - The street address of the user's place of business."
  type        = string
  default     = null
}

variable "surname" {
  description = "(optional) - The user's surname (family name or last name)."
  type        = string
  default     = null
}

variable "usage_location" {
  description = "(optional) - A two letter country code (ISO standard 3166). Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. Examples include: `NO`, `JP`, and `GB`. Not nullable."
  type        = string
  default     = null
}

variable "user_principal_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azuread_user" "this" {
  # account_enabled - (optional) is a type of bool
  account_enabled = var.account_enabled
  # city - (optional) is a type of string
  city = var.city
  # company_name - (optional) is a type of string
  company_name = var.company_name
  # country - (optional) is a type of string
  country = var.country
  # department - (optional) is a type of string
  department = var.department
  # display_name - (required) is a type of string
  display_name = var.display_name
  # force_password_change - (optional) is a type of bool
  force_password_change = var.force_password_change
  # given_name - (optional) is a type of string
  given_name = var.given_name
  # immutable_id - (optional) is a type of string
  immutable_id = var.immutable_id
  # job_title - (optional) is a type of string
  job_title = var.job_title
  # mail_nickname - (optional) is a type of string
  mail_nickname = var.mail_nickname
  # mobile - (optional) is a type of string
  mobile = var.mobile
  # password - (required) is a type of string
  password = var.password
  # physical_delivery_office_name - (optional) is a type of string
  physical_delivery_office_name = var.physical_delivery_office_name
  # postal_code - (optional) is a type of string
  postal_code = var.postal_code
  # state - (optional) is a type of string
  state = var.state
  # street_address - (optional) is a type of string
  street_address = var.street_address
  # surname - (optional) is a type of string
  surname = var.surname
  # usage_location - (optional) is a type of string
  usage_location = var.usage_location
  # user_principal_name - (required) is a type of string
  user_principal_name = var.user_principal_name
}
```

[top](#index)

### Outputs

```terraform
output "city" {
  description = "returns a string"
  value       = azuread_user.this.city
}

output "company_name" {
  description = "returns a string"
  value       = azuread_user.this.company_name
}

output "country" {
  description = "returns a string"
  value       = azuread_user.this.country
}

output "department" {
  description = "returns a string"
  value       = azuread_user.this.department
}

output "given_name" {
  description = "returns a string"
  value       = azuread_user.this.given_name
}

output "id" {
  description = "returns a string"
  value       = azuread_user.this.id
}

output "immutable_id" {
  description = "returns a string"
  value       = azuread_user.this.immutable_id
}

output "job_title" {
  description = "returns a string"
  value       = azuread_user.this.job_title
}

output "mail" {
  description = "returns a string"
  value       = azuread_user.this.mail
}

output "mail_nickname" {
  description = "returns a string"
  value       = azuread_user.this.mail_nickname
}

output "mobile" {
  description = "returns a string"
  value       = azuread_user.this.mobile
}

output "object_id" {
  description = "returns a string"
  value       = azuread_user.this.object_id
}

output "onpremises_sam_account_name" {
  description = "returns a string"
  value       = azuread_user.this.onpremises_sam_account_name
}

output "onpremises_user_principal_name" {
  description = "returns a string"
  value       = azuread_user.this.onpremises_user_principal_name
}

output "physical_delivery_office_name" {
  description = "returns a string"
  value       = azuread_user.this.physical_delivery_office_name
}

output "postal_code" {
  description = "returns a string"
  value       = azuread_user.this.postal_code
}

output "state" {
  description = "returns a string"
  value       = azuread_user.this.state
}

output "street_address" {
  description = "returns a string"
  value       = azuread_user.this.street_address
}

output "surname" {
  description = "returns a string"
  value       = azuread_user.this.surname
}

output "usage_location" {
  description = "returns a string"
  value       = azuread_user.this.usage_location
}

output "this" {
  value = azuread_user.this
}
```

[top](#index)