# fastly_service_v1

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_service_v1" {
  source = "./modules/fastly/r/fastly_service_v1"

  # activate - (optional) is a type of bool
  activate = null
  # comment - (optional) is a type of string
  comment = null
  # default_host - (optional) is a type of string
  default_host = null
  # default_ttl - (optional) is a type of number
  default_ttl = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # name - (required) is a type of string
  name = null
  # version_comment - (optional) is a type of string
  version_comment = null

  acl = [{
    acl_id        = null
    force_destroy = null
    name          = null
  }]

  backend = [{
    address               = null
    auto_loadbalance      = null
    between_bytes_timeout = null
    connect_timeout       = null
    error_threshold       = null
    first_byte_timeout    = null
    healthcheck           = null
    max_conn              = null
    max_tls_version       = null
    min_tls_version       = null
    name                  = null
    override_host         = null
    port                  = null
    request_condition     = null
    shield                = null
    ssl_ca_cert           = null
    ssl_cert_hostname     = null
    ssl_check_cert        = null
    ssl_ciphers           = null
    ssl_client_cert       = null
    ssl_client_key        = null
    ssl_hostname          = null
    ssl_sni_hostname      = null
    use_ssl               = null
    weight                = null
  }]

  bigquerylogging = [{
    dataset            = null
    email              = null
    format             = null
    name               = null
    placement          = null
    project_id         = null
    response_condition = null
    secret_key         = null
    table              = null
    template           = null
  }]

  blobstoragelogging = [{
    account_name       = null
    container          = null
    format             = null
    format_version     = null
    gzip_level         = null
    message_type       = null
    name               = null
    path               = null
    period             = null
    placement          = null
    public_key         = null
    response_condition = null
    sas_token          = null
    timestamp_format   = null
  }]

  cache_setting = [{
    action          = null
    cache_condition = null
    name            = null
    stale_ttl       = null
    ttl             = null
  }]

  condition = [{
    name      = null
    priority  = null
    statement = null
    type      = null
  }]

  dictionary = [{
    dictionary_id = null
    force_destroy = null
    name          = null
    write_only    = null
  }]

  director = [{
    backends = []
    capacity = null
    comment  = null
    name     = null
    quorum   = null
    retries  = null
    shield   = null
    type     = null
  }]

  domain = [{
    comment = null
    name    = null
  }]

  dynamicsnippet = [{
    name       = null
    priority   = null
    snippet_id = null
    type       = null
  }]

  gcslogging = [{
    bucket_name        = null
    email              = null
    format             = null
    gzip_level         = null
    message_type       = null
    name               = null
    path               = null
    period             = null
    placement          = null
    response_condition = null
    secret_key         = null
    timestamp_format   = null
  }]

  gzip = [{
    cache_condition = null
    content_types   = []
    extensions      = []
    name            = null
  }]

  header = [{
    action             = null
    cache_condition    = null
    destination        = null
    ignore_if_set      = null
    name               = null
    priority           = null
    regex              = null
    request_condition  = null
    response_condition = null
    source             = null
    substitution       = null
    type               = null
  }]

  healthcheck = [{
    check_interval    = null
    expected_response = null
    host              = null
    http_version      = null
    initial           = null
    method            = null
    name              = null
    path              = null
    threshold         = null
    timeout           = null
    window            = null
  }]

  httpslogging = [{
    content_type        = null
    format              = null
    format_version      = null
    header_name         = null
    header_value        = null
    json_format         = null
    message_type        = null
    method              = null
    name                = null
    placement           = null
    request_max_bytes   = null
    request_max_entries = null
    response_condition  = null
    tls_ca_cert         = null
    tls_client_cert     = null
    tls_client_key      = null
    tls_hostname        = null
    url                 = null
  }]

  logentries = [{
    format             = null
    format_version     = null
    name               = null
    placement          = null
    port               = null
    response_condition = null
    token              = null
    use_tls            = null
  }]

  logging_cloudfiles = [{
    access_key         = null
    bucket_name        = null
    format             = null
    format_version     = null
    gzip_level         = null
    message_type       = null
    name               = null
    path               = null
    period             = null
    placement          = null
    public_key         = null
    region             = null
    response_condition = null
    timestamp_format   = null
    user               = null
  }]

  logging_datadog = [{
    format             = null
    format_version     = null
    name               = null
    placement          = null
    region             = null
    response_condition = null
    token              = null
  }]

  logging_digitalocean = [{
    access_key         = null
    bucket_name        = null
    domain             = null
    format             = null
    format_version     = null
    gzip_level         = null
    message_type       = null
    name               = null
    path               = null
    period             = null
    placement          = null
    public_key         = null
    response_condition = null
    secret_key         = null
    timestamp_format   = null
  }]

  logging_elasticsearch = [{
    format              = null
    format_version      = null
    index               = null
    name                = null
    password            = null
    pipeline            = null
    placement           = null
    request_max_bytes   = null
    request_max_entries = null
    response_condition  = null
    tls_ca_cert         = null
    tls_client_cert     = null
    tls_client_key      = null
    tls_hostname        = null
    url                 = null
    user                = null
  }]

  logging_ftp = [{
    address            = null
    format             = null
    format_version     = null
    gzip_level         = null
    message_type       = null
    name               = null
    password           = null
    path               = null
    period             = null
    placement          = null
    port               = null
    public_key         = null
    response_condition = null
    timestamp_format   = null
    user               = null
  }]

  logging_googlepubsub = [{
    format             = null
    format_version     = null
    name               = null
    placement          = null
    project_id         = null
    response_condition = null
    secret_key         = null
    topic              = null
    user               = null
  }]

  logging_heroku = [{
    format             = null
    format_version     = null
    name               = null
    placement          = null
    response_condition = null
    token              = null
    url                = null
  }]

  logging_honeycomb = [{
    dataset            = null
    format             = null
    format_version     = null
    name               = null
    placement          = null
    response_condition = null
    token              = null
  }]

  logging_kafka = [{
    auth_method        = null
    brokers            = null
    compression_codec  = null
    format             = null
    format_version     = null
    name               = null
    parse_log_keyvals  = null
    password           = null
    placement          = null
    request_max_bytes  = null
    required_acks      = null
    response_condition = null
    tls_ca_cert        = null
    tls_client_cert    = null
    tls_client_key     = null
    tls_hostname       = null
    topic              = null
    use_tls            = null
    user               = null
  }]

  logging_kinesis = [{
    access_key         = null
    format             = null
    format_version     = null
    name               = null
    placement          = null
    region             = null
    response_condition = null
    secret_key         = null
    topic              = null
  }]

  logging_loggly = [{
    format             = null
    format_version     = null
    name               = null
    placement          = null
    response_condition = null
    token              = null
  }]

  logging_logshuttle = [{
    format             = null
    format_version     = null
    name               = null
    placement          = null
    response_condition = null
    token              = null
    url                = null
  }]

  logging_newrelic = [{
    format             = null
    format_version     = null
    name               = null
    placement          = null
    response_condition = null
    token              = null
  }]

  logging_openstack = [{
    access_key         = null
    bucket_name        = null
    format             = null
    format_version     = null
    gzip_level         = null
    message_type       = null
    name               = null
    path               = null
    period             = null
    placement          = null
    public_key         = null
    response_condition = null
    timestamp_format   = null
    url                = null
    user               = null
  }]

  logging_scalyr = [{
    format             = null
    format_version     = null
    name               = null
    placement          = null
    region             = null
    response_condition = null
    token              = null
  }]

  logging_sftp = [{
    address            = null
    format             = null
    format_version     = null
    gzip_level         = null
    message_type       = null
    name               = null
    password           = null
    path               = null
    period             = null
    placement          = null
    port               = null
    public_key         = null
    response_condition = null
    secret_key         = null
    ssh_known_hosts    = null
    timestamp_format   = null
    user               = null
  }]

  papertrail = [{
    address            = null
    format             = null
    format_version     = null
    name               = null
    placement          = null
    port               = null
    response_condition = null
  }]

  request_setting = [{
    action            = null
    bypass_busy_wait  = null
    default_host      = null
    force_miss        = null
    force_ssl         = null
    geo_headers       = null
    hash_keys         = null
    max_stale_age     = null
    name              = null
    request_condition = null
    timer_support     = null
    xff               = null
  }]

  response_object = [{
    cache_condition   = null
    content           = null
    content_type      = null
    name              = null
    request_condition = null
    response          = null
    status            = null
  }]

  s3logging = [{
    bucket_name                       = null
    domain                            = null
    format                            = null
    format_version                    = null
    gzip_level                        = null
    message_type                      = null
    name                              = null
    path                              = null
    period                            = null
    placement                         = null
    public_key                        = null
    redundancy                        = null
    response_condition                = null
    s3_access_key                     = null
    s3_secret_key                     = null
    server_side_encryption            = null
    server_side_encryption_kms_key_id = null
    timestamp_format                  = null
  }]

  snippet = [{
    content  = null
    name     = null
    priority = null
    type     = null
  }]

  splunk = [{
    format             = null
    format_version     = null
    name               = null
    placement          = null
    response_condition = null
    tls_ca_cert        = null
    tls_client_cert    = null
    tls_client_key     = null
    tls_hostname       = null
    token              = null
    url                = null
  }]

  sumologic = [{
    format             = null
    format_version     = null
    message_type       = null
    name               = null
    placement          = null
    response_condition = null
    url                = null
  }]

  syslog = [{
    address            = null
    format             = null
    format_version     = null
    message_type       = null
    name               = null
    placement          = null
    port               = null
    response_condition = null
    tls_ca_cert        = null
    tls_client_cert    = null
    tls_client_key     = null
    tls_hostname       = null
    token              = null
    use_tls            = null
  }]

  vcl = [{
    content = null
    main    = null
    name    = null
  }]

  waf = [{
    disabled           = null
    prefetch_condition = null
    response_object    = null
    waf_id             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "activate" {
  description = "(optional) - Conditionally prevents the Service from being activated. The apply step will continue to create a new draft version but will not activate it if this is set to `false`. Default `true`"
  type        = bool
  default     = null
}

variable "comment" {
  description = "(optional) - Description field for the service. Default `Managed by Terraform`"
  type        = string
  default     = null
}

variable "default_host" {
  description = "(optional) - The default hostname"
  type        = string
  default     = null
}

variable "default_ttl" {
  description = "(optional) - The default Time-to-live (TTL) for requests"
  type        = number
  default     = null
}

variable "force_destroy" {
  description = "(optional) - Services that are active cannot be destroyed. In order to destroy the Service, set `force_destroy` to `true`. Default `false`"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The unique name for the Service to create"
  type        = string
}

variable "version_comment" {
  description = "(optional) - Description field for the version"
  type        = string
  default     = null
}

variable "acl" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      acl_id        = string
      force_destroy = bool
      name          = string
    }
  ))
  default = []
}

variable "backend" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      address               = string
      auto_loadbalance      = bool
      between_bytes_timeout = number
      connect_timeout       = number
      error_threshold       = number
      first_byte_timeout    = number
      healthcheck           = string
      max_conn              = number
      max_tls_version       = string
      min_tls_version       = string
      name                  = string
      override_host         = string
      port                  = number
      request_condition     = string
      shield                = string
      ssl_ca_cert           = string
      ssl_cert_hostname     = string
      ssl_check_cert        = bool
      ssl_ciphers           = string
      ssl_client_cert       = string
      ssl_client_key        = string
      ssl_hostname          = string
      ssl_sni_hostname      = string
      use_ssl               = bool
      weight                = number
    }
  ))
}

variable "bigquerylogging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dataset            = string
      email              = string
      format             = string
      name               = string
      placement          = string
      project_id         = string
      response_condition = string
      secret_key         = string
      table              = string
      template           = string
    }
  ))
  default = []
}

variable "blobstoragelogging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      account_name       = string
      container          = string
      format             = string
      format_version     = number
      gzip_level         = number
      message_type       = string
      name               = string
      path               = string
      period             = number
      placement          = string
      public_key         = string
      response_condition = string
      sas_token          = string
      timestamp_format   = string
    }
  ))
  default = []
}

variable "cache_setting" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action          = string
      cache_condition = string
      name            = string
      stale_ttl       = number
      ttl             = number
    }
  ))
  default = []
}

variable "condition" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name      = string
      priority  = number
      statement = string
      type      = string
    }
  ))
  default = []
}

variable "dictionary" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dictionary_id = string
      force_destroy = bool
      name          = string
      write_only    = bool
    }
  ))
  default = []
}

variable "director" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      backends = set(string)
      capacity = number
      comment  = string
      name     = string
      quorum   = number
      retries  = number
      shield   = string
      type     = number
    }
  ))
  default = []
}

variable "domain" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      comment = string
      name    = string
    }
  ))
}

variable "dynamicsnippet" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name       = string
      priority   = number
      snippet_id = string
      type       = string
    }
  ))
  default = []
}

variable "gcslogging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bucket_name        = string
      email              = string
      format             = string
      gzip_level         = number
      message_type       = string
      name               = string
      path               = string
      period             = number
      placement          = string
      response_condition = string
      secret_key         = string
      timestamp_format   = string
    }
  ))
  default = []
}

variable "gzip" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cache_condition = string
      content_types   = set(string)
      extensions      = set(string)
      name            = string
    }
  ))
  default = []
}

variable "header" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action             = string
      cache_condition    = string
      destination        = string
      ignore_if_set      = bool
      name               = string
      priority           = number
      regex              = string
      request_condition  = string
      response_condition = string
      source             = string
      substitution       = string
      type               = string
    }
  ))
  default = []
}

variable "healthcheck" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      check_interval    = number
      expected_response = number
      host              = string
      http_version      = string
      initial           = number
      method            = string
      name              = string
      path              = string
      threshold         = number
      timeout           = number
      window            = number
    }
  ))
  default = []
}

variable "httpslogging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      content_type        = string
      format              = string
      format_version      = number
      header_name         = string
      header_value        = string
      json_format         = string
      message_type        = string
      method              = string
      name                = string
      placement           = string
      request_max_bytes   = number
      request_max_entries = number
      response_condition  = string
      tls_ca_cert         = string
      tls_client_cert     = string
      tls_client_key      = string
      tls_hostname        = string
      url                 = string
    }
  ))
  default = []
}

variable "logentries" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      format             = string
      format_version     = number
      name               = string
      placement          = string
      port               = number
      response_condition = string
      token              = string
      use_tls            = bool
    }
  ))
  default = []
}

variable "logging_cloudfiles" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key         = string
      bucket_name        = string
      format             = string
      format_version     = number
      gzip_level         = number
      message_type       = string
      name               = string
      path               = string
      period             = number
      placement          = string
      public_key         = string
      region             = string
      response_condition = string
      timestamp_format   = string
      user               = string
    }
  ))
  default = []
}

variable "logging_datadog" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      format             = string
      format_version     = number
      name               = string
      placement          = string
      region             = string
      response_condition = string
      token              = string
    }
  ))
  default = []
}

variable "logging_digitalocean" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key         = string
      bucket_name        = string
      domain             = string
      format             = string
      format_version     = number
      gzip_level         = number
      message_type       = string
      name               = string
      path               = string
      period             = number
      placement          = string
      public_key         = string
      response_condition = string
      secret_key         = string
      timestamp_format   = string
    }
  ))
  default = []
}

variable "logging_elasticsearch" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      format              = string
      format_version      = number
      index               = string
      name                = string
      password            = string
      pipeline            = string
      placement           = string
      request_max_bytes   = number
      request_max_entries = number
      response_condition  = string
      tls_ca_cert         = string
      tls_client_cert     = string
      tls_client_key      = string
      tls_hostname        = string
      url                 = string
      user                = string
    }
  ))
  default = []
}

variable "logging_ftp" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address            = string
      format             = string
      format_version     = number
      gzip_level         = number
      message_type       = string
      name               = string
      password           = string
      path               = string
      period             = number
      placement          = string
      port               = number
      public_key         = string
      response_condition = string
      timestamp_format   = string
      user               = string
    }
  ))
  default = []
}

variable "logging_googlepubsub" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      format             = string
      format_version     = number
      name               = string
      placement          = string
      project_id         = string
      response_condition = string
      secret_key         = string
      topic              = string
      user               = string
    }
  ))
  default = []
}

variable "logging_heroku" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      format             = string
      format_version     = number
      name               = string
      placement          = string
      response_condition = string
      token              = string
      url                = string
    }
  ))
  default = []
}

variable "logging_honeycomb" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dataset            = string
      format             = string
      format_version     = number
      name               = string
      placement          = string
      response_condition = string
      token              = string
    }
  ))
  default = []
}

variable "logging_kafka" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      auth_method        = string
      brokers            = string
      compression_codec  = string
      format             = string
      format_version     = number
      name               = string
      parse_log_keyvals  = bool
      password           = string
      placement          = string
      request_max_bytes  = number
      required_acks      = string
      response_condition = string
      tls_ca_cert        = string
      tls_client_cert    = string
      tls_client_key     = string
      tls_hostname       = string
      topic              = string
      use_tls            = bool
      user               = string
    }
  ))
  default = []
}

variable "logging_kinesis" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key         = string
      format             = string
      format_version     = number
      name               = string
      placement          = string
      region             = string
      response_condition = string
      secret_key         = string
      topic              = string
    }
  ))
  default = []
}

variable "logging_loggly" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      format             = string
      format_version     = number
      name               = string
      placement          = string
      response_condition = string
      token              = string
    }
  ))
  default = []
}

variable "logging_logshuttle" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      format             = string
      format_version     = number
      name               = string
      placement          = string
      response_condition = string
      token              = string
      url                = string
    }
  ))
  default = []
}

variable "logging_newrelic" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      format             = string
      format_version     = number
      name               = string
      placement          = string
      response_condition = string
      token              = string
    }
  ))
  default = []
}

variable "logging_openstack" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_key         = string
      bucket_name        = string
      format             = string
      format_version     = number
      gzip_level         = number
      message_type       = string
      name               = string
      path               = string
      period             = number
      placement          = string
      public_key         = string
      response_condition = string
      timestamp_format   = string
      url                = string
      user               = string
    }
  ))
  default = []
}

variable "logging_scalyr" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      format             = string
      format_version     = number
      name               = string
      placement          = string
      region             = string
      response_condition = string
      token              = string
    }
  ))
  default = []
}

variable "logging_sftp" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address            = string
      format             = string
      format_version     = number
      gzip_level         = number
      message_type       = string
      name               = string
      password           = string
      path               = string
      period             = number
      placement          = string
      port               = number
      public_key         = string
      response_condition = string
      secret_key         = string
      ssh_known_hosts    = string
      timestamp_format   = string
      user               = string
    }
  ))
  default = []
}

variable "papertrail" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address            = string
      format             = string
      format_version     = number
      name               = string
      placement          = string
      port               = number
      response_condition = string
    }
  ))
  default = []
}

variable "request_setting" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action            = string
      bypass_busy_wait  = bool
      default_host      = string
      force_miss        = bool
      force_ssl         = bool
      geo_headers       = bool
      hash_keys         = string
      max_stale_age     = number
      name              = string
      request_condition = string
      timer_support     = bool
      xff               = string
    }
  ))
  default = []
}

variable "response_object" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cache_condition   = string
      content           = string
      content_type      = string
      name              = string
      request_condition = string
      response          = string
      status            = number
    }
  ))
  default = []
}

variable "s3logging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bucket_name                       = string
      domain                            = string
      format                            = string
      format_version                    = number
      gzip_level                        = number
      message_type                      = string
      name                              = string
      path                              = string
      period                            = number
      placement                         = string
      public_key                        = string
      redundancy                        = string
      response_condition                = string
      s3_access_key                     = string
      s3_secret_key                     = string
      server_side_encryption            = string
      server_side_encryption_kms_key_id = string
      timestamp_format                  = string
    }
  ))
  default = []
}

variable "snippet" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      content  = string
      name     = string
      priority = number
      type     = string
    }
  ))
  default = []
}

variable "splunk" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      format             = string
      format_version     = number
      name               = string
      placement          = string
      response_condition = string
      tls_ca_cert        = string
      tls_client_cert    = string
      tls_client_key     = string
      tls_hostname       = string
      token              = string
      url                = string
    }
  ))
  default = []
}

variable "sumologic" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      format             = string
      format_version     = number
      message_type       = string
      name               = string
      placement          = string
      response_condition = string
      url                = string
    }
  ))
  default = []
}

variable "syslog" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address            = string
      format             = string
      format_version     = number
      message_type       = string
      name               = string
      placement          = string
      port               = number
      response_condition = string
      tls_ca_cert        = string
      tls_client_cert    = string
      tls_client_key     = string
      tls_hostname       = string
      token              = string
      use_tls            = bool
    }
  ))
  default = []
}

variable "vcl" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      content = string
      main    = bool
      name    = string
    }
  ))
  default = []
}

variable "waf" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disabled           = bool
      prefetch_condition = string
      response_object    = string
      waf_id             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fastly_service_v1" "this" {
  # activate - (optional) is a type of bool
  activate = var.activate
  # comment - (optional) is a type of string
  comment = var.comment
  # default_host - (optional) is a type of string
  default_host = var.default_host
  # default_ttl - (optional) is a type of number
  default_ttl = var.default_ttl
  # force_destroy - (optional) is a type of bool
  force_destroy = var.force_destroy
  # name - (required) is a type of string
  name = var.name
  # version_comment - (optional) is a type of string
  version_comment = var.version_comment

  dynamic "acl" {
    for_each = var.acl
    content {
      # force_destroy - (optional) is a type of bool
      force_destroy = acl.value["force_destroy"]
      # name - (required) is a type of string
      name = acl.value["name"]
    }
  }

  dynamic "backend" {
    for_each = var.backend
    content {
      # address - (required) is a type of string
      address = backend.value["address"]
      # auto_loadbalance - (optional) is a type of bool
      auto_loadbalance = backend.value["auto_loadbalance"]
      # between_bytes_timeout - (optional) is a type of number
      between_bytes_timeout = backend.value["between_bytes_timeout"]
      # connect_timeout - (optional) is a type of number
      connect_timeout = backend.value["connect_timeout"]
      # error_threshold - (optional) is a type of number
      error_threshold = backend.value["error_threshold"]
      # first_byte_timeout - (optional) is a type of number
      first_byte_timeout = backend.value["first_byte_timeout"]
      # healthcheck - (optional) is a type of string
      healthcheck = backend.value["healthcheck"]
      # max_conn - (optional) is a type of number
      max_conn = backend.value["max_conn"]
      # max_tls_version - (optional) is a type of string
      max_tls_version = backend.value["max_tls_version"]
      # min_tls_version - (optional) is a type of string
      min_tls_version = backend.value["min_tls_version"]
      # name - (required) is a type of string
      name = backend.value["name"]
      # override_host - (optional) is a type of string
      override_host = backend.value["override_host"]
      # port - (optional) is a type of number
      port = backend.value["port"]
      # request_condition - (optional) is a type of string
      request_condition = backend.value["request_condition"]
      # shield - (optional) is a type of string
      shield = backend.value["shield"]
      # ssl_ca_cert - (optional) is a type of string
      ssl_ca_cert = backend.value["ssl_ca_cert"]
      # ssl_cert_hostname - (optional) is a type of string
      ssl_cert_hostname = backend.value["ssl_cert_hostname"]
      # ssl_check_cert - (optional) is a type of bool
      ssl_check_cert = backend.value["ssl_check_cert"]
      # ssl_ciphers - (optional) is a type of string
      ssl_ciphers = backend.value["ssl_ciphers"]
      # ssl_client_cert - (optional) is a type of string
      ssl_client_cert = backend.value["ssl_client_cert"]
      # ssl_client_key - (optional) is a type of string
      ssl_client_key = backend.value["ssl_client_key"]
      # ssl_hostname - (optional) is a type of string
      ssl_hostname = backend.value["ssl_hostname"]
      # ssl_sni_hostname - (optional) is a type of string
      ssl_sni_hostname = backend.value["ssl_sni_hostname"]
      # use_ssl - (optional) is a type of bool
      use_ssl = backend.value["use_ssl"]
      # weight - (optional) is a type of number
      weight = backend.value["weight"]
    }
  }

  dynamic "bigquerylogging" {
    for_each = var.bigquerylogging
    content {
      # dataset - (required) is a type of string
      dataset = bigquerylogging.value["dataset"]
      # email - (optional) is a type of string
      email = bigquerylogging.value["email"]
      # format - (optional) is a type of string
      format = bigquerylogging.value["format"]
      # name - (required) is a type of string
      name = bigquerylogging.value["name"]
      # placement - (optional) is a type of string
      placement = bigquerylogging.value["placement"]
      # project_id - (required) is a type of string
      project_id = bigquerylogging.value["project_id"]
      # response_condition - (optional) is a type of string
      response_condition = bigquerylogging.value["response_condition"]
      # secret_key - (optional) is a type of string
      secret_key = bigquerylogging.value["secret_key"]
      # table - (required) is a type of string
      table = bigquerylogging.value["table"]
      # template - (optional) is a type of string
      template = bigquerylogging.value["template"]
    }
  }

  dynamic "blobstoragelogging" {
    for_each = var.blobstoragelogging
    content {
      # account_name - (required) is a type of string
      account_name = blobstoragelogging.value["account_name"]
      # container - (required) is a type of string
      container = blobstoragelogging.value["container"]
      # format - (optional) is a type of string
      format = blobstoragelogging.value["format"]
      # format_version - (optional) is a type of number
      format_version = blobstoragelogging.value["format_version"]
      # gzip_level - (optional) is a type of number
      gzip_level = blobstoragelogging.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = blobstoragelogging.value["message_type"]
      # name - (required) is a type of string
      name = blobstoragelogging.value["name"]
      # path - (optional) is a type of string
      path = blobstoragelogging.value["path"]
      # period - (optional) is a type of number
      period = blobstoragelogging.value["period"]
      # placement - (optional) is a type of string
      placement = blobstoragelogging.value["placement"]
      # public_key - (optional) is a type of string
      public_key = blobstoragelogging.value["public_key"]
      # response_condition - (optional) is a type of string
      response_condition = blobstoragelogging.value["response_condition"]
      # sas_token - (optional) is a type of string
      sas_token = blobstoragelogging.value["sas_token"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = blobstoragelogging.value["timestamp_format"]
    }
  }

  dynamic "cache_setting" {
    for_each = var.cache_setting
    content {
      # action - (optional) is a type of string
      action = cache_setting.value["action"]
      # cache_condition - (optional) is a type of string
      cache_condition = cache_setting.value["cache_condition"]
      # name - (required) is a type of string
      name = cache_setting.value["name"]
      # stale_ttl - (optional) is a type of number
      stale_ttl = cache_setting.value["stale_ttl"]
      # ttl - (optional) is a type of number
      ttl = cache_setting.value["ttl"]
    }
  }

  dynamic "condition" {
    for_each = var.condition
    content {
      # name - (required) is a type of string
      name = condition.value["name"]
      # priority - (optional) is a type of number
      priority = condition.value["priority"]
      # statement - (required) is a type of string
      statement = condition.value["statement"]
      # type - (required) is a type of string
      type = condition.value["type"]
    }
  }

  dynamic "dictionary" {
    for_each = var.dictionary
    content {
      # force_destroy - (optional) is a type of bool
      force_destroy = dictionary.value["force_destroy"]
      # name - (required) is a type of string
      name = dictionary.value["name"]
      # write_only - (optional) is a type of bool
      write_only = dictionary.value["write_only"]
    }
  }

  dynamic "director" {
    for_each = var.director
    content {
      # backends - (required) is a type of set of string
      backends = director.value["backends"]
      # capacity - (optional) is a type of number
      capacity = director.value["capacity"]
      # comment - (optional) is a type of string
      comment = director.value["comment"]
      # name - (required) is a type of string
      name = director.value["name"]
      # quorum - (optional) is a type of number
      quorum = director.value["quorum"]
      # retries - (optional) is a type of number
      retries = director.value["retries"]
      # shield - (optional) is a type of string
      shield = director.value["shield"]
      # type - (optional) is a type of number
      type = director.value["type"]
    }
  }

  dynamic "domain" {
    for_each = var.domain
    content {
      # comment - (optional) is a type of string
      comment = domain.value["comment"]
      # name - (required) is a type of string
      name = domain.value["name"]
    }
  }

  dynamic "dynamicsnippet" {
    for_each = var.dynamicsnippet
    content {
      # name - (required) is a type of string
      name = dynamicsnippet.value["name"]
      # priority - (optional) is a type of number
      priority = dynamicsnippet.value["priority"]
      # type - (required) is a type of string
      type = dynamicsnippet.value["type"]
    }
  }

  dynamic "gcslogging" {
    for_each = var.gcslogging
    content {
      # bucket_name - (required) is a type of string
      bucket_name = gcslogging.value["bucket_name"]
      # email - (optional) is a type of string
      email = gcslogging.value["email"]
      # format - (optional) is a type of string
      format = gcslogging.value["format"]
      # gzip_level - (optional) is a type of number
      gzip_level = gcslogging.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = gcslogging.value["message_type"]
      # name - (required) is a type of string
      name = gcslogging.value["name"]
      # path - (optional) is a type of string
      path = gcslogging.value["path"]
      # period - (optional) is a type of number
      period = gcslogging.value["period"]
      # placement - (optional) is a type of string
      placement = gcslogging.value["placement"]
      # response_condition - (optional) is a type of string
      response_condition = gcslogging.value["response_condition"]
      # secret_key - (optional) is a type of string
      secret_key = gcslogging.value["secret_key"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = gcslogging.value["timestamp_format"]
    }
  }

  dynamic "gzip" {
    for_each = var.gzip
    content {
      # cache_condition - (optional) is a type of string
      cache_condition = gzip.value["cache_condition"]
      # content_types - (optional) is a type of set of string
      content_types = gzip.value["content_types"]
      # extensions - (optional) is a type of set of string
      extensions = gzip.value["extensions"]
      # name - (required) is a type of string
      name = gzip.value["name"]
    }
  }

  dynamic "header" {
    for_each = var.header
    content {
      # action - (required) is a type of string
      action = header.value["action"]
      # cache_condition - (optional) is a type of string
      cache_condition = header.value["cache_condition"]
      # destination - (required) is a type of string
      destination = header.value["destination"]
      # ignore_if_set - (optional) is a type of bool
      ignore_if_set = header.value["ignore_if_set"]
      # name - (required) is a type of string
      name = header.value["name"]
      # priority - (optional) is a type of number
      priority = header.value["priority"]
      # regex - (optional) is a type of string
      regex = header.value["regex"]
      # request_condition - (optional) is a type of string
      request_condition = header.value["request_condition"]
      # response_condition - (optional) is a type of string
      response_condition = header.value["response_condition"]
      # source - (optional) is a type of string
      source = header.value["source"]
      # substitution - (optional) is a type of string
      substitution = header.value["substitution"]
      # type - (required) is a type of string
      type = header.value["type"]
    }
  }

  dynamic "healthcheck" {
    for_each = var.healthcheck
    content {
      # check_interval - (optional) is a type of number
      check_interval = healthcheck.value["check_interval"]
      # expected_response - (optional) is a type of number
      expected_response = healthcheck.value["expected_response"]
      # host - (required) is a type of string
      host = healthcheck.value["host"]
      # http_version - (optional) is a type of string
      http_version = healthcheck.value["http_version"]
      # initial - (optional) is a type of number
      initial = healthcheck.value["initial"]
      # method - (optional) is a type of string
      method = healthcheck.value["method"]
      # name - (required) is a type of string
      name = healthcheck.value["name"]
      # path - (required) is a type of string
      path = healthcheck.value["path"]
      # threshold - (optional) is a type of number
      threshold = healthcheck.value["threshold"]
      # timeout - (optional) is a type of number
      timeout = healthcheck.value["timeout"]
      # window - (optional) is a type of number
      window = healthcheck.value["window"]
    }
  }

  dynamic "httpslogging" {
    for_each = var.httpslogging
    content {
      # content_type - (optional) is a type of string
      content_type = httpslogging.value["content_type"]
      # format - (optional) is a type of string
      format = httpslogging.value["format"]
      # format_version - (optional) is a type of number
      format_version = httpslogging.value["format_version"]
      # header_name - (optional) is a type of string
      header_name = httpslogging.value["header_name"]
      # header_value - (optional) is a type of string
      header_value = httpslogging.value["header_value"]
      # json_format - (optional) is a type of string
      json_format = httpslogging.value["json_format"]
      # message_type - (optional) is a type of string
      message_type = httpslogging.value["message_type"]
      # method - (optional) is a type of string
      method = httpslogging.value["method"]
      # name - (required) is a type of string
      name = httpslogging.value["name"]
      # placement - (optional) is a type of string
      placement = httpslogging.value["placement"]
      # request_max_bytes - (optional) is a type of number
      request_max_bytes = httpslogging.value["request_max_bytes"]
      # request_max_entries - (optional) is a type of number
      request_max_entries = httpslogging.value["request_max_entries"]
      # response_condition - (optional) is a type of string
      response_condition = httpslogging.value["response_condition"]
      # tls_ca_cert - (optional) is a type of string
      tls_ca_cert = httpslogging.value["tls_ca_cert"]
      # tls_client_cert - (optional) is a type of string
      tls_client_cert = httpslogging.value["tls_client_cert"]
      # tls_client_key - (optional) is a type of string
      tls_client_key = httpslogging.value["tls_client_key"]
      # tls_hostname - (optional) is a type of string
      tls_hostname = httpslogging.value["tls_hostname"]
      # url - (required) is a type of string
      url = httpslogging.value["url"]
    }
  }

  dynamic "logentries" {
    for_each = var.logentries
    content {
      # format - (optional) is a type of string
      format = logentries.value["format"]
      # format_version - (optional) is a type of number
      format_version = logentries.value["format_version"]
      # name - (required) is a type of string
      name = logentries.value["name"]
      # placement - (optional) is a type of string
      placement = logentries.value["placement"]
      # port - (optional) is a type of number
      port = logentries.value["port"]
      # response_condition - (optional) is a type of string
      response_condition = logentries.value["response_condition"]
      # token - (required) is a type of string
      token = logentries.value["token"]
      # use_tls - (optional) is a type of bool
      use_tls = logentries.value["use_tls"]
    }
  }

  dynamic "logging_cloudfiles" {
    for_each = var.logging_cloudfiles
    content {
      # access_key - (required) is a type of string
      access_key = logging_cloudfiles.value["access_key"]
      # bucket_name - (required) is a type of string
      bucket_name = logging_cloudfiles.value["bucket_name"]
      # format - (optional) is a type of string
      format = logging_cloudfiles.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_cloudfiles.value["format_version"]
      # gzip_level - (optional) is a type of number
      gzip_level = logging_cloudfiles.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = logging_cloudfiles.value["message_type"]
      # name - (required) is a type of string
      name = logging_cloudfiles.value["name"]
      # path - (optional) is a type of string
      path = logging_cloudfiles.value["path"]
      # period - (optional) is a type of number
      period = logging_cloudfiles.value["period"]
      # placement - (optional) is a type of string
      placement = logging_cloudfiles.value["placement"]
      # public_key - (optional) is a type of string
      public_key = logging_cloudfiles.value["public_key"]
      # region - (optional) is a type of string
      region = logging_cloudfiles.value["region"]
      # response_condition - (optional) is a type of string
      response_condition = logging_cloudfiles.value["response_condition"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = logging_cloudfiles.value["timestamp_format"]
      # user - (required) is a type of string
      user = logging_cloudfiles.value["user"]
    }
  }

  dynamic "logging_datadog" {
    for_each = var.logging_datadog
    content {
      # format - (optional) is a type of string
      format = logging_datadog.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_datadog.value["format_version"]
      # name - (required) is a type of string
      name = logging_datadog.value["name"]
      # placement - (optional) is a type of string
      placement = logging_datadog.value["placement"]
      # region - (optional) is a type of string
      region = logging_datadog.value["region"]
      # response_condition - (optional) is a type of string
      response_condition = logging_datadog.value["response_condition"]
      # token - (required) is a type of string
      token = logging_datadog.value["token"]
    }
  }

  dynamic "logging_digitalocean" {
    for_each = var.logging_digitalocean
    content {
      # access_key - (required) is a type of string
      access_key = logging_digitalocean.value["access_key"]
      # bucket_name - (required) is a type of string
      bucket_name = logging_digitalocean.value["bucket_name"]
      # domain - (optional) is a type of string
      domain = logging_digitalocean.value["domain"]
      # format - (optional) is a type of string
      format = logging_digitalocean.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_digitalocean.value["format_version"]
      # gzip_level - (optional) is a type of number
      gzip_level = logging_digitalocean.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = logging_digitalocean.value["message_type"]
      # name - (required) is a type of string
      name = logging_digitalocean.value["name"]
      # path - (optional) is a type of string
      path = logging_digitalocean.value["path"]
      # period - (optional) is a type of number
      period = logging_digitalocean.value["period"]
      # placement - (optional) is a type of string
      placement = logging_digitalocean.value["placement"]
      # public_key - (optional) is a type of string
      public_key = logging_digitalocean.value["public_key"]
      # response_condition - (optional) is a type of string
      response_condition = logging_digitalocean.value["response_condition"]
      # secret_key - (required) is a type of string
      secret_key = logging_digitalocean.value["secret_key"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = logging_digitalocean.value["timestamp_format"]
    }
  }

  dynamic "logging_elasticsearch" {
    for_each = var.logging_elasticsearch
    content {
      # format - (optional) is a type of string
      format = logging_elasticsearch.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_elasticsearch.value["format_version"]
      # index - (required) is a type of string
      index = logging_elasticsearch.value["index"]
      # name - (required) is a type of string
      name = logging_elasticsearch.value["name"]
      # password - (optional) is a type of string
      password = logging_elasticsearch.value["password"]
      # pipeline - (optional) is a type of string
      pipeline = logging_elasticsearch.value["pipeline"]
      # placement - (optional) is a type of string
      placement = logging_elasticsearch.value["placement"]
      # request_max_bytes - (optional) is a type of number
      request_max_bytes = logging_elasticsearch.value["request_max_bytes"]
      # request_max_entries - (optional) is a type of number
      request_max_entries = logging_elasticsearch.value["request_max_entries"]
      # response_condition - (optional) is a type of string
      response_condition = logging_elasticsearch.value["response_condition"]
      # tls_ca_cert - (optional) is a type of string
      tls_ca_cert = logging_elasticsearch.value["tls_ca_cert"]
      # tls_client_cert - (optional) is a type of string
      tls_client_cert = logging_elasticsearch.value["tls_client_cert"]
      # tls_client_key - (optional) is a type of string
      tls_client_key = logging_elasticsearch.value["tls_client_key"]
      # tls_hostname - (optional) is a type of string
      tls_hostname = logging_elasticsearch.value["tls_hostname"]
      # url - (required) is a type of string
      url = logging_elasticsearch.value["url"]
      # user - (optional) is a type of string
      user = logging_elasticsearch.value["user"]
    }
  }

  dynamic "logging_ftp" {
    for_each = var.logging_ftp
    content {
      # address - (required) is a type of string
      address = logging_ftp.value["address"]
      # format - (optional) is a type of string
      format = logging_ftp.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_ftp.value["format_version"]
      # gzip_level - (optional) is a type of number
      gzip_level = logging_ftp.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = logging_ftp.value["message_type"]
      # name - (required) is a type of string
      name = logging_ftp.value["name"]
      # password - (required) is a type of string
      password = logging_ftp.value["password"]
      # path - (required) is a type of string
      path = logging_ftp.value["path"]
      # period - (optional) is a type of number
      period = logging_ftp.value["period"]
      # placement - (optional) is a type of string
      placement = logging_ftp.value["placement"]
      # port - (optional) is a type of number
      port = logging_ftp.value["port"]
      # public_key - (optional) is a type of string
      public_key = logging_ftp.value["public_key"]
      # response_condition - (optional) is a type of string
      response_condition = logging_ftp.value["response_condition"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = logging_ftp.value["timestamp_format"]
      # user - (required) is a type of string
      user = logging_ftp.value["user"]
    }
  }

  dynamic "logging_googlepubsub" {
    for_each = var.logging_googlepubsub
    content {
      # format - (optional) is a type of string
      format = logging_googlepubsub.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_googlepubsub.value["format_version"]
      # name - (required) is a type of string
      name = logging_googlepubsub.value["name"]
      # placement - (optional) is a type of string
      placement = logging_googlepubsub.value["placement"]
      # project_id - (required) is a type of string
      project_id = logging_googlepubsub.value["project_id"]
      # response_condition - (optional) is a type of string
      response_condition = logging_googlepubsub.value["response_condition"]
      # secret_key - (optional) is a type of string
      secret_key = logging_googlepubsub.value["secret_key"]
      # topic - (required) is a type of string
      topic = logging_googlepubsub.value["topic"]
      # user - (optional) is a type of string
      user = logging_googlepubsub.value["user"]
    }
  }

  dynamic "logging_heroku" {
    for_each = var.logging_heroku
    content {
      # format - (optional) is a type of string
      format = logging_heroku.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_heroku.value["format_version"]
      # name - (required) is a type of string
      name = logging_heroku.value["name"]
      # placement - (optional) is a type of string
      placement = logging_heroku.value["placement"]
      # response_condition - (optional) is a type of string
      response_condition = logging_heroku.value["response_condition"]
      # token - (required) is a type of string
      token = logging_heroku.value["token"]
      # url - (required) is a type of string
      url = logging_heroku.value["url"]
    }
  }

  dynamic "logging_honeycomb" {
    for_each = var.logging_honeycomb
    content {
      # dataset - (required) is a type of string
      dataset = logging_honeycomb.value["dataset"]
      # format - (optional) is a type of string
      format = logging_honeycomb.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_honeycomb.value["format_version"]
      # name - (required) is a type of string
      name = logging_honeycomb.value["name"]
      # placement - (optional) is a type of string
      placement = logging_honeycomb.value["placement"]
      # response_condition - (optional) is a type of string
      response_condition = logging_honeycomb.value["response_condition"]
      # token - (required) is a type of string
      token = logging_honeycomb.value["token"]
    }
  }

  dynamic "logging_kafka" {
    for_each = var.logging_kafka
    content {
      # auth_method - (optional) is a type of string
      auth_method = logging_kafka.value["auth_method"]
      # brokers - (required) is a type of string
      brokers = logging_kafka.value["brokers"]
      # compression_codec - (optional) is a type of string
      compression_codec = logging_kafka.value["compression_codec"]
      # format - (optional) is a type of string
      format = logging_kafka.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_kafka.value["format_version"]
      # name - (required) is a type of string
      name = logging_kafka.value["name"]
      # parse_log_keyvals - (optional) is a type of bool
      parse_log_keyvals = logging_kafka.value["parse_log_keyvals"]
      # password - (optional) is a type of string
      password = logging_kafka.value["password"]
      # placement - (optional) is a type of string
      placement = logging_kafka.value["placement"]
      # request_max_bytes - (optional) is a type of number
      request_max_bytes = logging_kafka.value["request_max_bytes"]
      # required_acks - (optional) is a type of string
      required_acks = logging_kafka.value["required_acks"]
      # response_condition - (optional) is a type of string
      response_condition = logging_kafka.value["response_condition"]
      # tls_ca_cert - (optional) is a type of string
      tls_ca_cert = logging_kafka.value["tls_ca_cert"]
      # tls_client_cert - (optional) is a type of string
      tls_client_cert = logging_kafka.value["tls_client_cert"]
      # tls_client_key - (optional) is a type of string
      tls_client_key = logging_kafka.value["tls_client_key"]
      # tls_hostname - (optional) is a type of string
      tls_hostname = logging_kafka.value["tls_hostname"]
      # topic - (required) is a type of string
      topic = logging_kafka.value["topic"]
      # use_tls - (optional) is a type of bool
      use_tls = logging_kafka.value["use_tls"]
      # user - (optional) is a type of string
      user = logging_kafka.value["user"]
    }
  }

  dynamic "logging_kinesis" {
    for_each = var.logging_kinesis
    content {
      # access_key - (required) is a type of string
      access_key = logging_kinesis.value["access_key"]
      # format - (optional) is a type of string
      format = logging_kinesis.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_kinesis.value["format_version"]
      # name - (required) is a type of string
      name = logging_kinesis.value["name"]
      # placement - (optional) is a type of string
      placement = logging_kinesis.value["placement"]
      # region - (optional) is a type of string
      region = logging_kinesis.value["region"]
      # response_condition - (optional) is a type of string
      response_condition = logging_kinesis.value["response_condition"]
      # secret_key - (required) is a type of string
      secret_key = logging_kinesis.value["secret_key"]
      # topic - (required) is a type of string
      topic = logging_kinesis.value["topic"]
    }
  }

  dynamic "logging_loggly" {
    for_each = var.logging_loggly
    content {
      # format - (optional) is a type of string
      format = logging_loggly.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_loggly.value["format_version"]
      # name - (required) is a type of string
      name = logging_loggly.value["name"]
      # placement - (optional) is a type of string
      placement = logging_loggly.value["placement"]
      # response_condition - (optional) is a type of string
      response_condition = logging_loggly.value["response_condition"]
      # token - (required) is a type of string
      token = logging_loggly.value["token"]
    }
  }

  dynamic "logging_logshuttle" {
    for_each = var.logging_logshuttle
    content {
      # format - (optional) is a type of string
      format = logging_logshuttle.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_logshuttle.value["format_version"]
      # name - (required) is a type of string
      name = logging_logshuttle.value["name"]
      # placement - (optional) is a type of string
      placement = logging_logshuttle.value["placement"]
      # response_condition - (optional) is a type of string
      response_condition = logging_logshuttle.value["response_condition"]
      # token - (required) is a type of string
      token = logging_logshuttle.value["token"]
      # url - (required) is a type of string
      url = logging_logshuttle.value["url"]
    }
  }

  dynamic "logging_newrelic" {
    for_each = var.logging_newrelic
    content {
      # format - (optional) is a type of string
      format = logging_newrelic.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_newrelic.value["format_version"]
      # name - (required) is a type of string
      name = logging_newrelic.value["name"]
      # placement - (optional) is a type of string
      placement = logging_newrelic.value["placement"]
      # response_condition - (optional) is a type of string
      response_condition = logging_newrelic.value["response_condition"]
      # token - (required) is a type of string
      token = logging_newrelic.value["token"]
    }
  }

  dynamic "logging_openstack" {
    for_each = var.logging_openstack
    content {
      # access_key - (required) is a type of string
      access_key = logging_openstack.value["access_key"]
      # bucket_name - (required) is a type of string
      bucket_name = logging_openstack.value["bucket_name"]
      # format - (optional) is a type of string
      format = logging_openstack.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_openstack.value["format_version"]
      # gzip_level - (optional) is a type of number
      gzip_level = logging_openstack.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = logging_openstack.value["message_type"]
      # name - (required) is a type of string
      name = logging_openstack.value["name"]
      # path - (optional) is a type of string
      path = logging_openstack.value["path"]
      # period - (optional) is a type of number
      period = logging_openstack.value["period"]
      # placement - (optional) is a type of string
      placement = logging_openstack.value["placement"]
      # public_key - (optional) is a type of string
      public_key = logging_openstack.value["public_key"]
      # response_condition - (optional) is a type of string
      response_condition = logging_openstack.value["response_condition"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = logging_openstack.value["timestamp_format"]
      # url - (required) is a type of string
      url = logging_openstack.value["url"]
      # user - (required) is a type of string
      user = logging_openstack.value["user"]
    }
  }

  dynamic "logging_scalyr" {
    for_each = var.logging_scalyr
    content {
      # format - (optional) is a type of string
      format = logging_scalyr.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_scalyr.value["format_version"]
      # name - (required) is a type of string
      name = logging_scalyr.value["name"]
      # placement - (optional) is a type of string
      placement = logging_scalyr.value["placement"]
      # region - (optional) is a type of string
      region = logging_scalyr.value["region"]
      # response_condition - (optional) is a type of string
      response_condition = logging_scalyr.value["response_condition"]
      # token - (required) is a type of string
      token = logging_scalyr.value["token"]
    }
  }

  dynamic "logging_sftp" {
    for_each = var.logging_sftp
    content {
      # address - (required) is a type of string
      address = logging_sftp.value["address"]
      # format - (optional) is a type of string
      format = logging_sftp.value["format"]
      # format_version - (optional) is a type of number
      format_version = logging_sftp.value["format_version"]
      # gzip_level - (optional) is a type of number
      gzip_level = logging_sftp.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = logging_sftp.value["message_type"]
      # name - (required) is a type of string
      name = logging_sftp.value["name"]
      # password - (optional) is a type of string
      password = logging_sftp.value["password"]
      # path - (required) is a type of string
      path = logging_sftp.value["path"]
      # period - (optional) is a type of number
      period = logging_sftp.value["period"]
      # placement - (optional) is a type of string
      placement = logging_sftp.value["placement"]
      # port - (optional) is a type of number
      port = logging_sftp.value["port"]
      # public_key - (optional) is a type of string
      public_key = logging_sftp.value["public_key"]
      # response_condition - (optional) is a type of string
      response_condition = logging_sftp.value["response_condition"]
      # secret_key - (optional) is a type of string
      secret_key = logging_sftp.value["secret_key"]
      # ssh_known_hosts - (required) is a type of string
      ssh_known_hosts = logging_sftp.value["ssh_known_hosts"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = logging_sftp.value["timestamp_format"]
      # user - (required) is a type of string
      user = logging_sftp.value["user"]
    }
  }

  dynamic "papertrail" {
    for_each = var.papertrail
    content {
      # address - (required) is a type of string
      address = papertrail.value["address"]
      # format - (optional) is a type of string
      format = papertrail.value["format"]
      # format_version - (optional) is a type of number
      format_version = papertrail.value["format_version"]
      # name - (required) is a type of string
      name = papertrail.value["name"]
      # placement - (optional) is a type of string
      placement = papertrail.value["placement"]
      # port - (required) is a type of number
      port = papertrail.value["port"]
      # response_condition - (optional) is a type of string
      response_condition = papertrail.value["response_condition"]
    }
  }

  dynamic "request_setting" {
    for_each = var.request_setting
    content {
      # action - (optional) is a type of string
      action = request_setting.value["action"]
      # bypass_busy_wait - (optional) is a type of bool
      bypass_busy_wait = request_setting.value["bypass_busy_wait"]
      # default_host - (optional) is a type of string
      default_host = request_setting.value["default_host"]
      # force_miss - (optional) is a type of bool
      force_miss = request_setting.value["force_miss"]
      # force_ssl - (optional) is a type of bool
      force_ssl = request_setting.value["force_ssl"]
      # geo_headers - (optional) is a type of bool
      geo_headers = request_setting.value["geo_headers"]
      # hash_keys - (optional) is a type of string
      hash_keys = request_setting.value["hash_keys"]
      # max_stale_age - (optional) is a type of number
      max_stale_age = request_setting.value["max_stale_age"]
      # name - (required) is a type of string
      name = request_setting.value["name"]
      # request_condition - (optional) is a type of string
      request_condition = request_setting.value["request_condition"]
      # timer_support - (optional) is a type of bool
      timer_support = request_setting.value["timer_support"]
      # xff - (optional) is a type of string
      xff = request_setting.value["xff"]
    }
  }

  dynamic "response_object" {
    for_each = var.response_object
    content {
      # cache_condition - (optional) is a type of string
      cache_condition = response_object.value["cache_condition"]
      # content - (optional) is a type of string
      content = response_object.value["content"]
      # content_type - (optional) is a type of string
      content_type = response_object.value["content_type"]
      # name - (required) is a type of string
      name = response_object.value["name"]
      # request_condition - (optional) is a type of string
      request_condition = response_object.value["request_condition"]
      # response - (optional) is a type of string
      response = response_object.value["response"]
      # status - (optional) is a type of number
      status = response_object.value["status"]
    }
  }

  dynamic "s3logging" {
    for_each = var.s3logging
    content {
      # bucket_name - (required) is a type of string
      bucket_name = s3logging.value["bucket_name"]
      # domain - (optional) is a type of string
      domain = s3logging.value["domain"]
      # format - (optional) is a type of string
      format = s3logging.value["format"]
      # format_version - (optional) is a type of number
      format_version = s3logging.value["format_version"]
      # gzip_level - (optional) is a type of number
      gzip_level = s3logging.value["gzip_level"]
      # message_type - (optional) is a type of string
      message_type = s3logging.value["message_type"]
      # name - (required) is a type of string
      name = s3logging.value["name"]
      # path - (optional) is a type of string
      path = s3logging.value["path"]
      # period - (optional) is a type of number
      period = s3logging.value["period"]
      # placement - (optional) is a type of string
      placement = s3logging.value["placement"]
      # public_key - (optional) is a type of string
      public_key = s3logging.value["public_key"]
      # redundancy - (optional) is a type of string
      redundancy = s3logging.value["redundancy"]
      # response_condition - (optional) is a type of string
      response_condition = s3logging.value["response_condition"]
      # s3_access_key - (optional) is a type of string
      s3_access_key = s3logging.value["s3_access_key"]
      # s3_secret_key - (optional) is a type of string
      s3_secret_key = s3logging.value["s3_secret_key"]
      # server_side_encryption - (optional) is a type of string
      server_side_encryption = s3logging.value["server_side_encryption"]
      # server_side_encryption_kms_key_id - (optional) is a type of string
      server_side_encryption_kms_key_id = s3logging.value["server_side_encryption_kms_key_id"]
      # timestamp_format - (optional) is a type of string
      timestamp_format = s3logging.value["timestamp_format"]
    }
  }

  dynamic "snippet" {
    for_each = var.snippet
    content {
      # content - (required) is a type of string
      content = snippet.value["content"]
      # name - (required) is a type of string
      name = snippet.value["name"]
      # priority - (optional) is a type of number
      priority = snippet.value["priority"]
      # type - (required) is a type of string
      type = snippet.value["type"]
    }
  }

  dynamic "splunk" {
    for_each = var.splunk
    content {
      # format - (optional) is a type of string
      format = splunk.value["format"]
      # format_version - (optional) is a type of number
      format_version = splunk.value["format_version"]
      # name - (required) is a type of string
      name = splunk.value["name"]
      # placement - (optional) is a type of string
      placement = splunk.value["placement"]
      # response_condition - (optional) is a type of string
      response_condition = splunk.value["response_condition"]
      # tls_ca_cert - (optional) is a type of string
      tls_ca_cert = splunk.value["tls_ca_cert"]
      # tls_client_cert - (optional) is a type of string
      tls_client_cert = splunk.value["tls_client_cert"]
      # tls_client_key - (optional) is a type of string
      tls_client_key = splunk.value["tls_client_key"]
      # tls_hostname - (optional) is a type of string
      tls_hostname = splunk.value["tls_hostname"]
      # token - (optional) is a type of string
      token = splunk.value["token"]
      # url - (required) is a type of string
      url = splunk.value["url"]
    }
  }

  dynamic "sumologic" {
    for_each = var.sumologic
    content {
      # format - (optional) is a type of string
      format = sumologic.value["format"]
      # format_version - (optional) is a type of number
      format_version = sumologic.value["format_version"]
      # message_type - (optional) is a type of string
      message_type = sumologic.value["message_type"]
      # name - (required) is a type of string
      name = sumologic.value["name"]
      # placement - (optional) is a type of string
      placement = sumologic.value["placement"]
      # response_condition - (optional) is a type of string
      response_condition = sumologic.value["response_condition"]
      # url - (required) is a type of string
      url = sumologic.value["url"]
    }
  }

  dynamic "syslog" {
    for_each = var.syslog
    content {
      # address - (required) is a type of string
      address = syslog.value["address"]
      # format - (optional) is a type of string
      format = syslog.value["format"]
      # format_version - (optional) is a type of number
      format_version = syslog.value["format_version"]
      # message_type - (optional) is a type of string
      message_type = syslog.value["message_type"]
      # name - (required) is a type of string
      name = syslog.value["name"]
      # placement - (optional) is a type of string
      placement = syslog.value["placement"]
      # port - (optional) is a type of number
      port = syslog.value["port"]
      # response_condition - (optional) is a type of string
      response_condition = syslog.value["response_condition"]
      # tls_ca_cert - (optional) is a type of string
      tls_ca_cert = syslog.value["tls_ca_cert"]
      # tls_client_cert - (optional) is a type of string
      tls_client_cert = syslog.value["tls_client_cert"]
      # tls_client_key - (optional) is a type of string
      tls_client_key = syslog.value["tls_client_key"]
      # tls_hostname - (optional) is a type of string
      tls_hostname = syslog.value["tls_hostname"]
      # token - (optional) is a type of string
      token = syslog.value["token"]
      # use_tls - (optional) is a type of bool
      use_tls = syslog.value["use_tls"]
    }
  }

  dynamic "vcl" {
    for_each = var.vcl
    content {
      # content - (required) is a type of string
      content = vcl.value["content"]
      # main - (optional) is a type of bool
      main = vcl.value["main"]
      # name - (required) is a type of string
      name = vcl.value["name"]
    }
  }

  dynamic "waf" {
    for_each = var.waf
    content {
      # disabled - (optional) is a type of bool
      disabled = waf.value["disabled"]
      # prefetch_condition - (optional) is a type of string
      prefetch_condition = waf.value["prefetch_condition"]
      # response_object - (required) is a type of string
      response_object = waf.value["response_object"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "active_version" {
  description = "returns a number"
  value       = fastly_service_v1.this.active_version
}

output "cloned_version" {
  description = "returns a number"
  value       = fastly_service_v1.this.cloned_version
}

output "default_host" {
  description = "returns a string"
  value       = fastly_service_v1.this.default_host
}

output "id" {
  description = "returns a string"
  value       = fastly_service_v1.this.id
}

output "this" {
  value = fastly_service_v1.this
}
```

[top](#index)