# ad_user

[back](../ad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ad = ">= 0.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ad_user" {
  source = "./modules/ad/r/ad_user"

  # cannot_change_password - (optional) is a type of bool
  cannot_change_password = null
  # city - (optional) is a type of string
  city = null
  # company - (optional) is a type of string
  company = null
  # container - (optional) is a type of string
  container = null
  # country - (optional) is a type of string
  country = null
  # custom_attributes - (optional) is a type of string
  custom_attributes = null
  # department - (optional) is a type of string
  department = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # division - (optional) is a type of string
  division = null
  # email_address - (optional) is a type of string
  email_address = null
  # employee_id - (optional) is a type of string
  employee_id = null
  # employee_number - (optional) is a type of string
  employee_number = null
  # enabled - (optional) is a type of bool
  enabled = null
  # fax - (optional) is a type of string
  fax = null
  # given_name - (optional) is a type of string
  given_name = null
  # home_directory - (optional) is a type of string
  home_directory = null
  # home_drive - (optional) is a type of string
  home_drive = null
  # home_page - (optional) is a type of string
  home_page = null
  # home_phone - (optional) is a type of string
  home_phone = null
  # initial_password - (optional) is a type of string
  initial_password = null
  # initials - (optional) is a type of string
  initials = null
  # mobile_phone - (optional) is a type of string
  mobile_phone = null
  # office - (optional) is a type of string
  office = null
  # office_phone - (optional) is a type of string
  office_phone = null
  # organization - (optional) is a type of string
  organization = null
  # other_name - (optional) is a type of string
  other_name = null
  # password_never_expires - (optional) is a type of bool
  password_never_expires = null
  # po_box - (optional) is a type of string
  po_box = null
  # postal_code - (optional) is a type of string
  postal_code = null
  # principal_name - (required) is a type of string
  principal_name = null
  # sam_account_name - (required) is a type of string
  sam_account_name = null
  # smart_card_logon_required - (optional) is a type of bool
  smart_card_logon_required = null
  # state - (optional) is a type of string
  state = null
  # street_address - (optional) is a type of string
  street_address = null
  # surname - (optional) is a type of string
  surname = null
  # title - (optional) is a type of string
  title = null
  # trusted_for_delegation - (optional) is a type of bool
  trusted_for_delegation = null
}
```

[top](#index)

### Variables

```terraform
variable "cannot_change_password" {
  description = "(optional) - If set to true, the user will not be allowed to change their password."
  type        = bool
  default     = null
}

variable "city" {
  description = "(optional) - Specifies the user's town or city. This parameter sets the City property of a user object."
  type        = string
  default     = null
}

variable "company" {
  description = "(optional) - Specifies the user's company. This parameter sets the Company property of a user object."
  type        = string
  default     = null
}

variable "container" {
  description = "(optional) - A DN of the container object that will be holding the user."
  type        = string
  default     = null
}

variable "country" {
  description = "(optional) - Specifies the country by setting the country code (refer to ISO 3166)"
  type        = string
  default     = null
}

variable "custom_attributes" {
  description = "(optional) - JSON encoded map that represents key/value pairs for custom attributes. Please note that `terraform import` will not import these attributes."
  type        = string
  default     = null
}

variable "department" {
  description = "(optional) - Specifies the user's department. This parameter sets the Department property of a user object."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Specifies a description of the object. This parameter sets the value of the Description property for the user object."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - The Display Name of an Active Directory user."
  type        = string
}

variable "division" {
  description = "(optional) - Specifies the user's division. This parameter sets the Division property of a user object."
  type        = string
  default     = null
}

variable "email_address" {
  description = "(optional) - Specifies the user's e-mail address. This parameter sets the EmailAddress property of a user object."
  type        = string
  default     = null
}

variable "employee_id" {
  description = "(optional) - Specifies the user's employee ID. This parameter sets the EmployeeID property of a user object."
  type        = string
  default     = null
}

variable "employee_number" {
  description = "(optional) - Specifies the user's employee number. This parameter sets the EmployeeNumber property of a user object."
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - If set to false, the user will be disabled."
  type        = bool
  default     = null
}

variable "fax" {
  description = "(optional) - Specifies the user's fax phone number. This parameter sets the Fax property of a user object."
  type        = string
  default     = null
}

variable "given_name" {
  description = "(optional) - Specifies the user's given name. This parameter sets the GivenName property of a user object."
  type        = string
  default     = null
}

variable "home_directory" {
  description = "(optional) - Specifies a user's home directory. This parameter sets the HomeDirectory property of a user object."
  type        = string
  default     = null
}

variable "home_drive" {
  description = "(optional) - Specifies a drive that is associated with the UNC path defined by the HomeDirectory property. The drive letter is specified as <DriveLetter>: where <DriveLetter> indicates the letter of the drive to associate. The <DriveLetter> must be a single, uppercase letter and the colon is required. This parameter sets the HomeDrive property of the user object."
  type        = string
  default     = null
}

variable "home_page" {
  description = "(optional) - Specifies the URL of the home page of the object. This parameter sets the homePage property of a user object."
  type        = string
  default     = null
}

variable "home_phone" {
  description = "(optional) - Specifies the user's home telephone number. This parameter sets the HomePhone property of a user object."
  type        = string
  default     = null
}

variable "initial_password" {
  description = "(optional) - The user's initial password. This will be set on creation but will *not* be enforced in subsequent plans."
  type        = string
  default     = null
}

variable "initials" {
  description = "(optional) - Specifies the initials that represent part of a user's name. Maximum 6 char."
  type        = string
  default     = null
}

variable "mobile_phone" {
  description = "(optional) - Specifies the user's mobile phone number. This parameter sets the MobilePhone property of a user object."
  type        = string
  default     = null
}

variable "office" {
  description = "(optional) - Specifies the location of the user's office or place of business. This parameter sets the Office property of a user object."
  type        = string
  default     = null
}

variable "office_phone" {
  description = "(optional) - Specifies the user's office telephone number. This parameter sets the OfficePhone property of a user object."
  type        = string
  default     = null
}

variable "organization" {
  description = "(optional) - Specifies the user's organization. This parameter sets the Organization property of a user object."
  type        = string
  default     = null
}

variable "other_name" {
  description = "(optional) - Specifies a name in addition to a user's given name and surname, such as the user's middle name."
  type        = string
  default     = null
}

variable "password_never_expires" {
  description = "(optional) - If set to true, the password for this user will not expire."
  type        = bool
  default     = null
}

variable "po_box" {
  description = "(optional) - Specifies the user's post office box number. This parameter sets the POBox property of a user object."
  type        = string
  default     = null
}

variable "postal_code" {
  description = "(optional) - Specifies the user's postal code or zip code. This parameter sets the PostalCode property of a user object."
  type        = string
  default     = null
}

variable "principal_name" {
  description = "(required) - The Principal Name of an Active Directory user."
  type        = string
}

variable "sam_account_name" {
  description = "(required) - The pre-win2k user logon name."
  type        = string
}

variable "smart_card_logon_required" {
  description = "(optional) - If set to true, a smart card is required to logon. This parameter sets the SmartCardLoginRequired property for a user object."
  type        = bool
  default     = null
}

variable "state" {
  description = "(optional) - Specifies the user's or Organizational Unit's state or province. This parameter sets the State property of a user object."
  type        = string
  default     = null
}

variable "street_address" {
  description = "(optional) - Specifies the user's street address. This parameter sets the StreetAddress property of a user object."
  type        = string
  default     = null
}

variable "surname" {
  description = "(optional) - Specifies the user's last name or surname. This parameter sets the Surname property of a user object."
  type        = string
  default     = null
}

variable "title" {
  description = "(optional) - Specifies the user's title. This parameter sets the Title property of a user object"
  type        = string
  default     = null
}

variable "trusted_for_delegation" {
  description = "(optional) - If set to true, the user account is trusted for Kerberos delegation. A service that runs under an account that is trusted for Kerberos delegation can assume the identity of a client requesting the service. This parameter sets the TrustedForDelegation property of an account object."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ad_user" "this" {
  # cannot_change_password - (optional) is a type of bool
  cannot_change_password = var.cannot_change_password
  # city - (optional) is a type of string
  city = var.city
  # company - (optional) is a type of string
  company = var.company
  # container - (optional) is a type of string
  container = var.container
  # country - (optional) is a type of string
  country = var.country
  # custom_attributes - (optional) is a type of string
  custom_attributes = var.custom_attributes
  # department - (optional) is a type of string
  department = var.department
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # division - (optional) is a type of string
  division = var.division
  # email_address - (optional) is a type of string
  email_address = var.email_address
  # employee_id - (optional) is a type of string
  employee_id = var.employee_id
  # employee_number - (optional) is a type of string
  employee_number = var.employee_number
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # fax - (optional) is a type of string
  fax = var.fax
  # given_name - (optional) is a type of string
  given_name = var.given_name
  # home_directory - (optional) is a type of string
  home_directory = var.home_directory
  # home_drive - (optional) is a type of string
  home_drive = var.home_drive
  # home_page - (optional) is a type of string
  home_page = var.home_page
  # home_phone - (optional) is a type of string
  home_phone = var.home_phone
  # initial_password - (optional) is a type of string
  initial_password = var.initial_password
  # initials - (optional) is a type of string
  initials = var.initials
  # mobile_phone - (optional) is a type of string
  mobile_phone = var.mobile_phone
  # office - (optional) is a type of string
  office = var.office
  # office_phone - (optional) is a type of string
  office_phone = var.office_phone
  # organization - (optional) is a type of string
  organization = var.organization
  # other_name - (optional) is a type of string
  other_name = var.other_name
  # password_never_expires - (optional) is a type of bool
  password_never_expires = var.password_never_expires
  # po_box - (optional) is a type of string
  po_box = var.po_box
  # postal_code - (optional) is a type of string
  postal_code = var.postal_code
  # principal_name - (required) is a type of string
  principal_name = var.principal_name
  # sam_account_name - (required) is a type of string
  sam_account_name = var.sam_account_name
  # smart_card_logon_required - (optional) is a type of bool
  smart_card_logon_required = var.smart_card_logon_required
  # state - (optional) is a type of string
  state = var.state
  # street_address - (optional) is a type of string
  street_address = var.street_address
  # surname - (optional) is a type of string
  surname = var.surname
  # title - (optional) is a type of string
  title = var.title
  # trusted_for_delegation - (optional) is a type of bool
  trusted_for_delegation = var.trusted_for_delegation
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ad_user.this.id
}

output "this" {
  value = ad_user.this
}
```

[top](#index)