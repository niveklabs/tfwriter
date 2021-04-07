# checkpoint_management_user

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_user" {
  source = "./modules/checkpoint/r/checkpoint_management_user"

  # allowed_locations - (optional) is a type of map of string
  allowed_locations = {}
  # authentication_method - (optional) is a type of string
  authentication_method = null
  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # connect_daily - (optional) is a type of bool
  connect_daily = null
  # connect_on_days - (optional) is a type of set of string
  connect_on_days = []
  # email - (optional) is a type of string
  email = null
  # encryption - (optional) is a type of map of string
  encryption = {}
  # expiration_date - (optional) is a type of string
  expiration_date = null
  # from_hour - (optional) is a type of string
  from_hour = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # phone_number - (optional) is a type of string
  phone_number = null
  # radius_server - (optional) is a type of string
  radius_server = null
  # tacacs_server - (optional) is a type of string
  tacacs_server = null
  # tags - (optional) is a type of set of string
  tags = []
  # template - (optional) is a type of string
  template = null
  # to_hour - (optional) is a type of string
  to_hour = null
}
```

[top](#index)

### Variables

```terraform
variable "allowed_locations" {
  description = "(optional) - User allowed locations."
  type        = map(string)
  default     = null
}

variable "authentication_method" {
  description = "(optional) - Authentication method."
  type        = string
  default     = null
}

variable "color" {
  description = "(optional) - Color of the object. Should be one of existing colors."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "connect_daily" {
  description = "(optional) - Connect every day."
  type        = bool
  default     = null
}

variable "connect_on_days" {
  description = "(optional) - Days users allow to connect."
  type        = set(string)
  default     = null
}

variable "email" {
  description = "(optional) - User email."
  type        = string
  default     = null
}

variable "encryption" {
  description = "(optional) - User encryption."
  type        = map(string)
  default     = null
}

variable "expiration_date" {
  description = "(optional) - Expiration date in format: yyyy-MM-dd."
  type        = string
  default     = null
}

variable "from_hour" {
  description = "(optional) - Allow users connect from hour."
  type        = string
  default     = null
}

variable "ignore_errors" {
  description = "(optional) - Apply changes ignoring errors. You won't be able to publish such a changes. If ignore-warnings flag was omitted - warnings will also be ignored."
  type        = bool
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - Apply changes ignoring warnings."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "password" {
  description = "(optional) - Checkpoint password authentication method identified by the name or UID. Must be set when \"authentication-method\" was selected to be \"Check Point Password\"."
  type        = string
  default     = null
}

variable "phone_number" {
  description = "(optional) - User phone number."
  type        = string
  default     = null
}

variable "radius_server" {
  description = "(optional) - RADIUS server object identified by the name or UID. Must be set when \"authentication-method\" was selected to be \"RADIUS\"."
  type        = string
  default     = null
}

variable "tacacs_server" {
  description = "(optional) - TACACS server object identified by the name or UID. Must be set when \"authentication-method\" was selected to be \"TACACS\"."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "template" {
  description = "(optional) - User template name or UID."
  type        = string
  default     = null
}

variable "to_hour" {
  description = "(optional) - Allow users connect until hour."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_user" "this" {
  # allowed_locations - (optional) is a type of map of string
  allowed_locations = var.allowed_locations
  # authentication_method - (optional) is a type of string
  authentication_method = var.authentication_method
  # color - (optional) is a type of string
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # connect_daily - (optional) is a type of bool
  connect_daily = var.connect_daily
  # connect_on_days - (optional) is a type of set of string
  connect_on_days = var.connect_on_days
  # email - (optional) is a type of string
  email = var.email
  # encryption - (optional) is a type of map of string
  encryption = var.encryption
  # expiration_date - (optional) is a type of string
  expiration_date = var.expiration_date
  # from_hour - (optional) is a type of string
  from_hour = var.from_hour
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # name - (required) is a type of string
  name = var.name
  # password - (optional) is a type of string
  password = var.password
  # phone_number - (optional) is a type of string
  phone_number = var.phone_number
  # radius_server - (optional) is a type of string
  radius_server = var.radius_server
  # tacacs_server - (optional) is a type of string
  tacacs_server = var.tacacs_server
  # tags - (optional) is a type of set of string
  tags = var.tags
  # template - (optional) is a type of string
  template = var.template
  # to_hour - (optional) is a type of string
  to_hour = var.to_hour
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_user.this.id
}

output "this" {
  value = checkpoint_management_user.this
}
```

[top](#index)