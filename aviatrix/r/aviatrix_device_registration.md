# aviatrix_device_registration

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_device_registration" {
  source = "./modules/aviatrix/r/aviatrix_device_registration"

  # address_1 - (optional) is a type of string
  address_1 = null
  # address_2 - (optional) is a type of string
  address_2 = null
  # city - (optional) is a type of string
  city = null
  # country - (optional) is a type of string
  country = null
  # description - (optional) is a type of string
  description = null
  # host_os - (optional) is a type of string
  host_os = null
  # key_file - (optional) is a type of string
  key_file = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # public_ip - (required) is a type of string
  public_ip = null
  # ssh_port - (optional) is a type of number
  ssh_port = null
  # state - (optional) is a type of string
  state = null
  # username - (required) is a type of string
  username = null
  # zip_code - (optional) is a type of string
  zip_code = null
}
```

[top](#index)

### Variables

```terraform
variable "address_1" {
  description = "(optional) - Address line 1."
  type        = string
  default     = null
}

variable "address_2" {
  description = "(optional) - Address line 2."
  type        = string
  default     = null
}

variable "city" {
  description = "(optional) - City"
  type        = string
  default     = null
}

variable "country" {
  description = "(optional) - ISO two-letter country code."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description."
  type        = string
  default     = null
}

variable "host_os" {
  description = "(optional) - Device host OS. Default value is 'ios'. Only valid value is 'ios'."
  type        = string
  default     = null
}

variable "key_file" {
  description = "(optional) - Path to private key file."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the device."
  type        = string
}

variable "password" {
  description = "(optional) - Password to connect to the device. This attribute can also be set via environment variable 'AVIATRIX_DEVICE_PASSWORD'. If both are set the value in the config file will be used."
  type        = string
  default     = null
}

variable "public_ip" {
  description = "(required) - Public IP address of the device."
  type        = string
}

variable "ssh_port" {
  description = "(optional) - SSH port to use to connect to the device. Defaults to 22 if not set."
  type        = number
  default     = null
}

variable "state" {
  description = "(optional) - State"
  type        = string
  default     = null
}

variable "username" {
  description = "(required) - Username to use to connect to the device."
  type        = string
}

variable "zip_code" {
  description = "(optional) - Zip code."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_device_registration" "this" {
  address_1   = var.address_1
  address_2   = var.address_2
  city        = var.city
  country     = var.country
  description = var.description
  host_os     = var.host_os
  key_file    = var.key_file
  name        = var.name
  password    = var.password
  public_ip   = var.public_ip
  ssh_port    = var.ssh_port
  state       = var.state
  username    = var.username
  zip_code    = var.zip_code
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_device_registration.this.id
}

output "this" {
  value = aviatrix_device_registration.this
}
```

[top](#index)