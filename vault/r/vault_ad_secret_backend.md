# vault_ad_secret_backend

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
module "vault_ad_secret_backend" {
  source = "./modules/vault/r/vault_ad_secret_backend"

  # anonymous_group_search - (optional) is a type of bool
  anonymous_group_search = null
  # backend - (optional) is a type of string
  backend = null
  # binddn - (required) is a type of string
  binddn = null
  # bindpass - (required) is a type of string
  bindpass = null
  # case_sensitive_names - (optional) is a type of bool
  case_sensitive_names = null
  # certificate - (optional) is a type of string
  certificate = null
  # client_tls_cert - (optional) is a type of string
  client_tls_cert = null
  # client_tls_key - (optional) is a type of string
  client_tls_key = null
  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = null
  # deny_null_bind - (optional) is a type of bool
  deny_null_bind = null
  # description - (optional) is a type of string
  description = null
  # discoverdn - (optional) is a type of bool
  discoverdn = null
  # formatter - (optional) is a type of string
  formatter = null
  # groupattr - (optional) is a type of string
  groupattr = null
  # groupdn - (optional) is a type of string
  groupdn = null
  # groupfilter - (optional) is a type of string
  groupfilter = null
  # insecure_tls - (optional) is a type of bool
  insecure_tls = null
  # last_rotation_tolerance - (optional) is a type of number
  last_rotation_tolerance = null
  # length - (optional) is a type of number
  length = null
  # local - (optional) is a type of bool
  local = null
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = null
  # max_ttl - (optional) is a type of number
  max_ttl = null
  # password_policy - (optional) is a type of string
  password_policy = null
  # request_timeout - (optional) is a type of number
  request_timeout = null
  # starttls - (optional) is a type of bool
  starttls = null
  # tls_max_version - (optional) is a type of string
  tls_max_version = null
  # tls_min_version - (optional) is a type of string
  tls_min_version = null
  # ttl - (optional) is a type of number
  ttl = null
  # upndomain - (optional) is a type of string
  upndomain = null
  # url - (optional) is a type of string
  url = null
  # use_pre111_group_cn_behavior - (optional) is a type of bool
  use_pre111_group_cn_behavior = null
  # use_token_groups - (optional) is a type of bool
  use_token_groups = null
  # userattr - (optional) is a type of string
  userattr = null
  # userdn - (optional) is a type of string
  userdn = null
}
```

[top](#index)

### Variables

```terraform
variable "anonymous_group_search" {
  description = "(optional) - Use anonymous binds when performing LDAP group searches (if true the initial credentials will still be used for the initial connection test)."
  type        = bool
  default     = null
}

variable "backend" {
  description = "(optional) - The mount path for a backend, for example, the path given in \"$ vault auth enable -path=my-ad ad\"."
  type        = string
  default     = null
}

variable "binddn" {
  description = "(required) - Distinguished name of object to bind when performing user and group search."
  type        = string
}

variable "bindpass" {
  description = "(required) - LDAP password for searching for the user DN."
  type        = string
}

variable "case_sensitive_names" {
  description = "(optional) - If true, case sensitivity will be used when comparing usernames and groups for matching policies."
  type        = bool
  default     = null
}

variable "certificate" {
  description = "(optional) - CA certificate to use when verifying LDAP server certificate, must be x509 PEM encoded."
  type        = string
  default     = null
}

variable "client_tls_cert" {
  description = "(optional) - Client certificate to provide to the LDAP server, must be x509 PEM encoded."
  type        = string
  default     = null
}

variable "client_tls_key" {
  description = "(optional) - Client certificate key to provide to the LDAP server, must be x509 PEM encoded."
  type        = string
  default     = null
}

variable "default_lease_ttl_seconds" {
  description = "(optional) - Default lease duration for secrets in seconds"
  type        = number
  default     = null
}

variable "deny_null_bind" {
  description = "(optional) - Denies an unauthenticated LDAP bind request if the user's password is empty; defaults to true"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - Human-friendly description of the mount for the backend."
  type        = string
  default     = null
}

variable "discoverdn" {
  description = "(optional) - Use anonymous bind to discover the bind DN of a user."
  type        = bool
  default     = null
}

variable "formatter" {
  description = "(optional) - Text to insert the password into, ex. \"customPrefix{{PASSWORD}}customSuffix\"."
  type        = string
  default     = null
}

variable "groupattr" {
  description = "(optional) - LDAP attribute to follow on objects returned by <groupfilter> in order to enumerate user group membership. Examples: \"cn\" or \"memberOf\", etc. Default: cn"
  type        = string
  default     = null
}

variable "groupdn" {
  description = "(optional) - LDAP search base to use for group membership search (eg: ou=Groups,dc=example,dc=org)"
  type        = string
  default     = null
}

variable "groupfilter" {
  description = "(optional) - Go template for querying group membership of user. The template can access the following context variables: UserDN, Username Example: (&(objectClass=group)(member:1.2.840.113556.1.4.1941:={{.UserDN}})) Default: (|(memberUid={{.Username}})(member={{.UserDN}})(uniqueMember={{.UserDN}}))"
  type        = string
  default     = null
}

variable "insecure_tls" {
  description = "(optional) - Skip LDAP server SSL Certificate verification - insecure and not recommended for production use."
  type        = bool
  default     = null
}

variable "last_rotation_tolerance" {
  description = "(optional) - The number of seconds after a Vault rotation where, if Active Directory shows a later rotation, it should be considered out-of-band."
  type        = number
  default     = null
}

variable "length" {
  description = "(optional) - The desired length of passwords that Vault generates."
  type        = number
  default     = null
}

variable "local" {
  description = "(optional) - Mark the secrets engine as local-only. Local engines are not replicated or removed by replication.Tolerance duration to use when checking the last rotation time."
  type        = bool
  default     = null
}

variable "max_lease_ttl_seconds" {
  description = "(optional) - Maximum possible lease duration for secrets in seconds."
  type        = number
  default     = null
}

variable "max_ttl" {
  description = "(optional) - In seconds, the maximum password time-to-live."
  type        = number
  default     = null
}

variable "password_policy" {
  description = "(optional) - Name of the password policy to use to generate passwords."
  type        = string
  default     = null
}

variable "request_timeout" {
  description = "(optional) - Timeout, in seconds, for the connection when making requests against the server before returning back an error."
  type        = number
  default     = null
}

variable "starttls" {
  description = "(optional) - Issue a StartTLS command after establishing unencrypted connection."
  type        = bool
  default     = null
}

variable "tls_max_version" {
  description = "(optional) - Maximum TLS version to use. Accepted values are 'tls10', 'tls11', 'tls12' or 'tls13'. Defaults to 'tls12'"
  type        = string
  default     = null
}

variable "tls_min_version" {
  description = "(optional) - Minimum TLS version to use. Accepted values are 'tls10', 'tls11', 'tls12' or 'tls13'. Defaults to 'tls12'"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional) - In seconds, the default password time-to-live."
  type        = number
  default     = null
}

variable "upndomain" {
  description = "(optional) - Enables userPrincipalDomain login with [username]@UPNDomain."
  type        = string
  default     = null
}

variable "url" {
  description = "(optional) - LDAP URL to connect to (default: ldap://127.0.0.1). Multiple URLs can be specified by concatenating them with commas; they will be tried in-order."
  type        = string
  default     = null
}

variable "use_pre111_group_cn_behavior" {
  description = "(optional) - In Vault 1.1.1 a fix for handling group CN values of different cases unfortunately introduced a regression that could cause previously defined groups to not be found due to a change in the resulting name. If set true, the pre-1.1.1 behavior for matching group CNs will be used. This is only needed in some upgrade scenarios for backwards compatibility. It is enabled by default if the config is upgraded but disabled by default on new configurations."
  type        = bool
  default     = null
}

variable "use_token_groups" {
  description = "(optional) - If true, use the Active Directory tokenGroups constructed attribute of the user to find the group memberships. This will find all security groups including nested ones."
  type        = bool
  default     = null
}

variable "userattr" {
  description = "(optional) - Attribute used for users (default: cn)"
  type        = string
  default     = null
}

variable "userdn" {
  description = "(optional) - LDAP domain to use for users (eg: ou=People,dc=example,dc=org)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_ad_secret_backend" "this" {
  anonymous_group_search       = var.anonymous_group_search
  backend                      = var.backend
  binddn                       = var.binddn
  bindpass                     = var.bindpass
  case_sensitive_names         = var.case_sensitive_names
  certificate                  = var.certificate
  client_tls_cert              = var.client_tls_cert
  client_tls_key               = var.client_tls_key
  default_lease_ttl_seconds    = var.default_lease_ttl_seconds
  deny_null_bind               = var.deny_null_bind
  description                  = var.description
  discoverdn                   = var.discoverdn
  formatter                    = var.formatter
  groupattr                    = var.groupattr
  groupdn                      = var.groupdn
  groupfilter                  = var.groupfilter
  insecure_tls                 = var.insecure_tls
  last_rotation_tolerance      = var.last_rotation_tolerance
  length                       = var.length
  local                        = var.local
  max_lease_ttl_seconds        = var.max_lease_ttl_seconds
  max_ttl                      = var.max_ttl
  password_policy              = var.password_policy
  request_timeout              = var.request_timeout
  starttls                     = var.starttls
  tls_max_version              = var.tls_max_version
  tls_min_version              = var.tls_min_version
  ttl                          = var.ttl
  upndomain                    = var.upndomain
  url                          = var.url
  use_pre111_group_cn_behavior = var.use_pre111_group_cn_behavior
  use_token_groups             = var.use_token_groups
  userattr                     = var.userattr
  userdn                       = var.userdn
}
```

[top](#index)

### Outputs

```terraform
output "default_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_ad_secret_backend.this.default_lease_ttl_seconds
}

output "formatter" {
  description = "returns a string"
  value       = vault_ad_secret_backend.this.formatter
}

output "id" {
  description = "returns a string"
  value       = vault_ad_secret_backend.this.id
}

output "last_rotation_tolerance" {
  description = "returns a number"
  value       = vault_ad_secret_backend.this.last_rotation_tolerance
}

output "length" {
  description = "returns a number"
  value       = vault_ad_secret_backend.this.length
}

output "max_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_ad_secret_backend.this.max_lease_ttl_seconds
}

output "max_ttl" {
  description = "returns a number"
  value       = vault_ad_secret_backend.this.max_ttl
}

output "starttls" {
  description = "returns a bool"
  value       = vault_ad_secret_backend.this.starttls
}

output "tls_max_version" {
  description = "returns a string"
  value       = vault_ad_secret_backend.this.tls_max_version
}

output "tls_min_version" {
  description = "returns a string"
  value       = vault_ad_secret_backend.this.tls_min_version
}

output "ttl" {
  description = "returns a number"
  value       = vault_ad_secret_backend.this.ttl
}

output "upndomain" {
  description = "returns a string"
  value       = vault_ad_secret_backend.this.upndomain
}

output "use_pre111_group_cn_behavior" {
  description = "returns a bool"
  value       = vault_ad_secret_backend.this.use_pre111_group_cn_behavior
}

output "this" {
  value = vault_ad_secret_backend.this
}
```

[top](#index)