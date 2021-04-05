# sdm_resource

[back](../sdm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sdm = ">= 1.0.19"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sdm_resource" {
  source = "./modules/sdm/r/sdm_resource"


  aks = [{
    certificate_authority                   = null
    client_certificate                      = null
    client_key                              = null
    healthcheck_namespace                   = null
    hostname                                = null
    name                                    = null
    port                                    = null
    secret_store_certificate_authority_key  = null
    secret_store_certificate_authority_path = null
    secret_store_client_certificate_key     = null
    secret_store_client_certificate_path    = null
    secret_store_client_key_key             = null
    secret_store_client_key_path            = null
    secret_store_id                         = null
    tags                                    = {}
  }]

  aks_basic_auth = [{
    healthcheck_namespace      = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  aks_service_account = [{
    healthcheck_namespace   = null
    hostname                = null
    name                    = null
    port                    = null
    secret_store_id         = null
    secret_store_token_key  = null
    secret_store_token_path = null
    tags                    = {}
    token                   = null
  }]

  amazon_eks = [{
    access_key                              = null
    certificate_authority                   = null
    cluster_name                            = null
    endpoint                                = null
    healthcheck_namespace                   = null
    name                                    = null
    region                                  = null
    role_arn                                = null
    role_external_id                        = null
    secret_access_key                       = null
    secret_store_access_key_key             = null
    secret_store_access_key_path            = null
    secret_store_certificate_authority_key  = null
    secret_store_certificate_authority_path = null
    secret_store_id                         = null
    secret_store_role_arn_key               = null
    secret_store_role_arn_path              = null
    secret_store_role_external_id_key       = null
    secret_store_role_external_id_path      = null
    secret_store_secret_access_key_key      = null
    secret_store_secret_access_key_path     = null
    tags                                    = {}
  }]

  amazon_es = [{
    access_key                          = null
    endpoint                            = null
    name                                = null
    port_override                       = null
    region                              = null
    role_arn                            = null
    role_external_id                    = null
    secret_access_key                   = null
    secret_store_access_key_key         = null
    secret_store_access_key_path        = null
    secret_store_id                     = null
    secret_store_role_arn_key           = null
    secret_store_role_arn_path          = null
    secret_store_role_external_id_key   = null
    secret_store_role_external_id_path  = null
    secret_store_secret_access_key_key  = null
    secret_store_secret_access_key_path = null
    tags                                = {}
  }]

  athena = [{
    access_key                          = null
    name                                = null
    output                              = null
    port_override                       = null
    region                              = null
    role_arn                            = null
    role_external_id                    = null
    secret_access_key                   = null
    secret_store_access_key_key         = null
    secret_store_access_key_path        = null
    secret_store_id                     = null
    secret_store_role_arn_key           = null
    secret_store_role_arn_path          = null
    secret_store_role_external_id_key   = null
    secret_store_role_external_id_path  = null
    secret_store_secret_access_key_key  = null
    secret_store_secret_access_key_path = null
    tags                                = {}
  }]

  aurora_mysql = [{
    database                   = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  aurora_postgres = [{
    database                   = null
    hostname                   = null
    name                       = null
    override_database          = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  aws = [{
    access_key                          = null
    healthcheck_region                  = null
    name                                = null
    role_arn                            = null
    role_external_id                    = null
    secret_access_key                   = null
    secret_store_access_key_key         = null
    secret_store_access_key_path        = null
    secret_store_id                     = null
    secret_store_role_arn_key           = null
    secret_store_role_arn_path          = null
    secret_store_role_external_id_key   = null
    secret_store_role_external_id_path  = null
    secret_store_secret_access_key_key  = null
    secret_store_secret_access_key_path = null
    tags                                = {}
  }]

  big_query = [{
    endpoint                      = null
    name                          = null
    port_override                 = null
    private_key                   = null
    project                       = null
    secret_store_id               = null
    secret_store_private_key_key  = null
    secret_store_private_key_path = null
    tags                          = {}
    username                      = null
  }]

  cassandra = [{
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    tls_required               = null
    username                   = null
  }]

  citus = [{
    database                   = null
    hostname                   = null
    name                       = null
    override_database          = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  clustrix = [{
    database                   = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  cockroach = [{
    database                   = null
    hostname                   = null
    name                       = null
    override_database          = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  db_2_i = [{
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    tls_required               = null
    username                   = null
  }]

  db_2_luw = [{
    database                   = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  druid = [{
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  dynamo_db = [{
    access_key                          = null
    endpoint                            = null
    name                                = null
    port_override                       = null
    region                              = null
    role_arn                            = null
    role_external_id                    = null
    secret_access_key                   = null
    secret_store_access_key_key         = null
    secret_store_access_key_path        = null
    secret_store_id                     = null
    secret_store_role_arn_key           = null
    secret_store_role_arn_path          = null
    secret_store_role_external_id_key   = null
    secret_store_role_external_id_path  = null
    secret_store_secret_access_key_key  = null
    secret_store_secret_access_key_path = null
    tags                                = {}
  }]

  elastic = [{
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    tls_required               = null
    username                   = null
  }]

  elasticache_redis = [{
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    tags                       = {}
    tls_required               = null
  }]

  google_gke = [{
    certificate_authority                   = null
    endpoint                                = null
    healthcheck_namespace                   = null
    name                                    = null
    secret_store_certificate_authority_key  = null
    secret_store_certificate_authority_path = null
    secret_store_id                         = null
    secret_store_service_account_key_key    = null
    secret_store_service_account_key_path   = null
    service_account_key                     = null
    tags                                    = {}
  }]

  greenplum = [{
    database                   = null
    hostname                   = null
    name                       = null
    override_database          = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  http_auth = [{
    auth_header                   = null
    default_path                  = null
    headers_blacklist             = null
    healthcheck_path              = null
    name                          = null
    secret_store_auth_header_key  = null
    secret_store_auth_header_path = null
    secret_store_id               = null
    subdomain                     = null
    tags                          = {}
    url                           = null
  }]

  http_basic_auth = [{
    default_path               = null
    headers_blacklist          = null
    healthcheck_path           = null
    name                       = null
    password                   = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    subdomain                  = null
    tags                       = {}
    url                        = null
    username                   = null
  }]

  http_no_auth = [{
    default_path      = null
    headers_blacklist = null
    healthcheck_path  = null
    name              = null
    secret_store_id   = null
    subdomain         = null
    tags              = {}
    url               = null
  }]

  kubernetes = [{
    certificate_authority                   = null
    client_certificate                      = null
    client_key                              = null
    healthcheck_namespace                   = null
    hostname                                = null
    name                                    = null
    port                                    = null
    secret_store_certificate_authority_key  = null
    secret_store_certificate_authority_path = null
    secret_store_client_certificate_key     = null
    secret_store_client_certificate_path    = null
    secret_store_client_key_key             = null
    secret_store_client_key_path            = null
    secret_store_id                         = null
    tags                                    = {}
  }]

  kubernetes_basic_auth = [{
    healthcheck_namespace      = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  kubernetes_service_account = [{
    healthcheck_namespace   = null
    hostname                = null
    name                    = null
    port                    = null
    secret_store_id         = null
    secret_store_token_key  = null
    secret_store_token_path = null
    tags                    = {}
    token                   = null
  }]

  maria = [{
    database                   = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  memcached = [{
    hostname        = null
    name            = null
    port            = null
    port_override   = null
    secret_store_id = null
    tags            = {}
  }]

  memsql = [{
    database                   = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  mongo_host = [{
    auth_database              = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    tls_required               = null
    username                   = null
  }]

  mongo_legacy_host = [{
    auth_database              = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    replica_set                = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    tls_required               = null
    username                   = null
  }]

  mongo_legacy_replicaset = [{
    auth_database              = null
    connect_to_replica         = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    replica_set                = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    tls_required               = null
    username                   = null
  }]

  mongo_replica_set = [{
    auth_database              = null
    connect_to_replica         = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    replica_set                = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    tls_required               = null
    username                   = null
  }]

  mysql = [{
    database                   = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  oracle = [{
    database                   = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    tls_required               = null
    username                   = null
  }]

  postgres = [{
    database                   = null
    hostname                   = null
    name                       = null
    override_database          = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  presto = [{
    database                   = null
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    tags                       = {}
    tls_required               = null
    username                   = null
  }]

  rdp = [{
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  redis = [{
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    tags                       = {}
  }]

  redshift = [{
    database                   = null
    hostname                   = null
    name                       = null
    override_database          = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  snowflake = [{
    database                   = null
    hostname                   = null
    name                       = null
    password                   = null
    port_override              = null
    schema                     = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  sql_server = [{
    database                   = null
    hostname                   = null
    name                       = null
    override_database          = null
    password                   = null
    port                       = null
    port_override              = null
    schema                     = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  ssh = [{
    allow_deprecated_key_exchanges = null
    hostname                       = null
    name                           = null
    port                           = null
    port_forwarding                = null
    public_key                     = null
    secret_store_id                = null
    tags                           = {}
    username                       = null
  }]

  ssh_cert = [{
    allow_deprecated_key_exchanges = null
    hostname                       = null
    name                           = null
    port                           = null
    port_forwarding                = null
    secret_store_id                = null
    tags                           = {}
    username                       = null
  }]

  sybase = [{
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  sybase_iq = [{
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  teradata = [{
    hostname                   = null
    name                       = null
    password                   = null
    port                       = null
    port_override              = null
    secret_store_id            = null
    secret_store_password_key  = null
    secret_store_password_path = null
    secret_store_username_key  = null
    secret_store_username_path = null
    tags                       = {}
    username                   = null
  }]

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "aks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_authority                   = string
      client_certificate                      = string
      client_key                              = string
      healthcheck_namespace                   = string
      hostname                                = string
      name                                    = string
      port                                    = number
      secret_store_certificate_authority_key  = string
      secret_store_certificate_authority_path = string
      secret_store_client_certificate_key     = string
      secret_store_client_certificate_path    = string
      secret_store_client_key_key             = string
      secret_store_client_key_path            = string
      secret_store_id                         = string
      tags                                    = map(string)
    }
  ))
  default = []
}

variable "aks_basic_auth" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      healthcheck_namespace      = string
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "aks_service_account" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      healthcheck_namespace   = string
      hostname                = string
      name                    = string
      port                    = number
      secret_store_id         = string
      secret_store_token_key  = string
      secret_store_token_path = string
      tags                    = map(string)
      token                   = string
    }
  ))
  default = []
}

variable "amazon_eks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_key                              = string
      certificate_authority                   = string
      cluster_name                            = string
      endpoint                                = string
      healthcheck_namespace                   = string
      name                                    = string
      region                                  = string
      role_arn                                = string
      role_external_id                        = string
      secret_access_key                       = string
      secret_store_access_key_key             = string
      secret_store_access_key_path            = string
      secret_store_certificate_authority_key  = string
      secret_store_certificate_authority_path = string
      secret_store_id                         = string
      secret_store_role_arn_key               = string
      secret_store_role_arn_path              = string
      secret_store_role_external_id_key       = string
      secret_store_role_external_id_path      = string
      secret_store_secret_access_key_key      = string
      secret_store_secret_access_key_path     = string
      tags                                    = map(string)
    }
  ))
  default = []
}

variable "amazon_es" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_key                          = string
      endpoint                            = string
      name                                = string
      port_override                       = number
      region                              = string
      role_arn                            = string
      role_external_id                    = string
      secret_access_key                   = string
      secret_store_access_key_key         = string
      secret_store_access_key_path        = string
      secret_store_id                     = string
      secret_store_role_arn_key           = string
      secret_store_role_arn_path          = string
      secret_store_role_external_id_key   = string
      secret_store_role_external_id_path  = string
      secret_store_secret_access_key_key  = string
      secret_store_secret_access_key_path = string
      tags                                = map(string)
    }
  ))
  default = []
}

variable "athena" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_key                          = string
      name                                = string
      output                              = string
      port_override                       = number
      region                              = string
      role_arn                            = string
      role_external_id                    = string
      secret_access_key                   = string
      secret_store_access_key_key         = string
      secret_store_access_key_path        = string
      secret_store_id                     = string
      secret_store_role_arn_key           = string
      secret_store_role_arn_path          = string
      secret_store_role_external_id_key   = string
      secret_store_role_external_id_path  = string
      secret_store_secret_access_key_key  = string
      secret_store_secret_access_key_path = string
      tags                                = map(string)
    }
  ))
  default = []
}

variable "aurora_mysql" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "aurora_postgres" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      override_database          = bool
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "aws" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_key                          = string
      healthcheck_region                  = string
      name                                = string
      role_arn                            = string
      role_external_id                    = string
      secret_access_key                   = string
      secret_store_access_key_key         = string
      secret_store_access_key_path        = string
      secret_store_id                     = string
      secret_store_role_arn_key           = string
      secret_store_role_arn_path          = string
      secret_store_role_external_id_key   = string
      secret_store_role_external_id_path  = string
      secret_store_secret_access_key_key  = string
      secret_store_secret_access_key_path = string
      tags                                = map(string)
    }
  ))
  default = []
}

variable "big_query" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      endpoint                      = string
      name                          = string
      port_override                 = number
      private_key                   = string
      project                       = string
      secret_store_id               = string
      secret_store_private_key_key  = string
      secret_store_private_key_path = string
      tags                          = map(string)
      username                      = string
    }
  ))
  default = []
}

variable "cassandra" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      tls_required               = bool
      username                   = string
    }
  ))
  default = []
}

variable "citus" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      override_database          = bool
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "clustrix" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "cockroach" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      override_database          = bool
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "db_2_i" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      tls_required               = bool
      username                   = string
    }
  ))
  default = []
}

variable "db_2_luw" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "druid" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "dynamo_db" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_key                          = string
      endpoint                            = string
      name                                = string
      port_override                       = number
      region                              = string
      role_arn                            = string
      role_external_id                    = string
      secret_access_key                   = string
      secret_store_access_key_key         = string
      secret_store_access_key_path        = string
      secret_store_id                     = string
      secret_store_role_arn_key           = string
      secret_store_role_arn_path          = string
      secret_store_role_external_id_key   = string
      secret_store_role_external_id_path  = string
      secret_store_secret_access_key_key  = string
      secret_store_secret_access_key_path = string
      tags                                = map(string)
    }
  ))
  default = []
}

variable "elastic" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      tls_required               = bool
      username                   = string
    }
  ))
  default = []
}

variable "elasticache_redis" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      tags                       = map(string)
      tls_required               = bool
    }
  ))
  default = []
}

variable "google_gke" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_authority                   = string
      endpoint                                = string
      healthcheck_namespace                   = string
      name                                    = string
      secret_store_certificate_authority_key  = string
      secret_store_certificate_authority_path = string
      secret_store_id                         = string
      secret_store_service_account_key_key    = string
      secret_store_service_account_key_path   = string
      service_account_key                     = string
      tags                                    = map(string)
    }
  ))
  default = []
}

variable "greenplum" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      override_database          = bool
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "http_auth" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth_header                   = string
      default_path                  = string
      headers_blacklist             = string
      healthcheck_path              = string
      name                          = string
      secret_store_auth_header_key  = string
      secret_store_auth_header_path = string
      secret_store_id               = string
      subdomain                     = string
      tags                          = map(string)
      url                           = string
    }
  ))
  default = []
}

variable "http_basic_auth" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      default_path               = string
      headers_blacklist          = string
      healthcheck_path           = string
      name                       = string
      password                   = string
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      subdomain                  = string
      tags                       = map(string)
      url                        = string
      username                   = string
    }
  ))
  default = []
}

variable "http_no_auth" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      default_path      = string
      headers_blacklist = string
      healthcheck_path  = string
      name              = string
      secret_store_id   = string
      subdomain         = string
      tags              = map(string)
      url               = string
    }
  ))
  default = []
}

variable "kubernetes" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_authority                   = string
      client_certificate                      = string
      client_key                              = string
      healthcheck_namespace                   = string
      hostname                                = string
      name                                    = string
      port                                    = number
      secret_store_certificate_authority_key  = string
      secret_store_certificate_authority_path = string
      secret_store_client_certificate_key     = string
      secret_store_client_certificate_path    = string
      secret_store_client_key_key             = string
      secret_store_client_key_path            = string
      secret_store_id                         = string
      tags                                    = map(string)
    }
  ))
  default = []
}

variable "kubernetes_basic_auth" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      healthcheck_namespace      = string
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "kubernetes_service_account" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      healthcheck_namespace   = string
      hostname                = string
      name                    = string
      port                    = number
      secret_store_id         = string
      secret_store_token_key  = string
      secret_store_token_path = string
      tags                    = map(string)
      token                   = string
    }
  ))
  default = []
}

variable "maria" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "memcached" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname        = string
      name            = string
      port            = number
      port_override   = number
      secret_store_id = string
      tags            = map(string)
    }
  ))
  default = []
}

variable "memsql" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "mongo_host" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth_database              = string
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      tls_required               = bool
      username                   = string
    }
  ))
  default = []
}

variable "mongo_legacy_host" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth_database              = string
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      replica_set                = string
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      tls_required               = bool
      username                   = string
    }
  ))
  default = []
}

variable "mongo_legacy_replicaset" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth_database              = string
      connect_to_replica         = bool
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      replica_set                = string
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      tls_required               = bool
      username                   = string
    }
  ))
  default = []
}

variable "mongo_replica_set" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth_database              = string
      connect_to_replica         = bool
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      replica_set                = string
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      tls_required               = bool
      username                   = string
    }
  ))
  default = []
}

variable "mysql" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "oracle" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      tls_required               = bool
      username                   = string
    }
  ))
  default = []
}

variable "postgres" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      override_database          = bool
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "presto" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      tags                       = map(string)
      tls_required               = bool
      username                   = string
    }
  ))
  default = []
}

variable "rdp" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "redis" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      tags                       = map(string)
    }
  ))
  default = []
}

variable "redshift" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      override_database          = bool
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "snowflake" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      password                   = string
      port_override              = number
      schema                     = string
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "sql_server" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database                   = string
      hostname                   = string
      name                       = string
      override_database          = bool
      password                   = string
      port                       = number
      port_override              = number
      schema                     = string
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "ssh" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allow_deprecated_key_exchanges = bool
      hostname                       = string
      name                           = string
      port                           = number
      port_forwarding                = bool
      public_key                     = string
      secret_store_id                = string
      tags                           = map(string)
      username                       = string
    }
  ))
  default = []
}

variable "ssh_cert" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allow_deprecated_key_exchanges = bool
      hostname                       = string
      name                           = string
      port                           = number
      port_forwarding                = bool
      secret_store_id                = string
      tags                           = map(string)
      username                       = string
    }
  ))
  default = []
}

variable "sybase" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "sybase_iq" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "teradata" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname                   = string
      name                       = string
      password                   = string
      port                       = number
      port_override              = number
      secret_store_id            = string
      secret_store_password_key  = string
      secret_store_password_path = string
      secret_store_username_key  = string
      secret_store_username_path = string
      tags                       = map(string)
      username                   = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "sdm_resource" "this" {

  dynamic "aks" {
    for_each = var.aks
    content {
      certificate_authority                   = aks.value["certificate_authority"]
      client_certificate                      = aks.value["client_certificate"]
      client_key                              = aks.value["client_key"]
      healthcheck_namespace                   = aks.value["healthcheck_namespace"]
      hostname                                = aks.value["hostname"]
      name                                    = aks.value["name"]
      port                                    = aks.value["port"]
      secret_store_certificate_authority_key  = aks.value["secret_store_certificate_authority_key"]
      secret_store_certificate_authority_path = aks.value["secret_store_certificate_authority_path"]
      secret_store_client_certificate_key     = aks.value["secret_store_client_certificate_key"]
      secret_store_client_certificate_path    = aks.value["secret_store_client_certificate_path"]
      secret_store_client_key_key             = aks.value["secret_store_client_key_key"]
      secret_store_client_key_path            = aks.value["secret_store_client_key_path"]
      secret_store_id                         = aks.value["secret_store_id"]
      tags                                    = aks.value["tags"]
    }
  }

  dynamic "aks_basic_auth" {
    for_each = var.aks_basic_auth
    content {
      healthcheck_namespace      = aks_basic_auth.value["healthcheck_namespace"]
      hostname                   = aks_basic_auth.value["hostname"]
      name                       = aks_basic_auth.value["name"]
      password                   = aks_basic_auth.value["password"]
      port                       = aks_basic_auth.value["port"]
      secret_store_id            = aks_basic_auth.value["secret_store_id"]
      secret_store_password_key  = aks_basic_auth.value["secret_store_password_key"]
      secret_store_password_path = aks_basic_auth.value["secret_store_password_path"]
      secret_store_username_key  = aks_basic_auth.value["secret_store_username_key"]
      secret_store_username_path = aks_basic_auth.value["secret_store_username_path"]
      tags                       = aks_basic_auth.value["tags"]
      username                   = aks_basic_auth.value["username"]
    }
  }

  dynamic "aks_service_account" {
    for_each = var.aks_service_account
    content {
      healthcheck_namespace   = aks_service_account.value["healthcheck_namespace"]
      hostname                = aks_service_account.value["hostname"]
      name                    = aks_service_account.value["name"]
      port                    = aks_service_account.value["port"]
      secret_store_id         = aks_service_account.value["secret_store_id"]
      secret_store_token_key  = aks_service_account.value["secret_store_token_key"]
      secret_store_token_path = aks_service_account.value["secret_store_token_path"]
      tags                    = aks_service_account.value["tags"]
      token                   = aks_service_account.value["token"]
    }
  }

  dynamic "amazon_eks" {
    for_each = var.amazon_eks
    content {
      access_key                              = amazon_eks.value["access_key"]
      certificate_authority                   = amazon_eks.value["certificate_authority"]
      cluster_name                            = amazon_eks.value["cluster_name"]
      endpoint                                = amazon_eks.value["endpoint"]
      healthcheck_namespace                   = amazon_eks.value["healthcheck_namespace"]
      name                                    = amazon_eks.value["name"]
      region                                  = amazon_eks.value["region"]
      role_arn                                = amazon_eks.value["role_arn"]
      role_external_id                        = amazon_eks.value["role_external_id"]
      secret_access_key                       = amazon_eks.value["secret_access_key"]
      secret_store_access_key_key             = amazon_eks.value["secret_store_access_key_key"]
      secret_store_access_key_path            = amazon_eks.value["secret_store_access_key_path"]
      secret_store_certificate_authority_key  = amazon_eks.value["secret_store_certificate_authority_key"]
      secret_store_certificate_authority_path = amazon_eks.value["secret_store_certificate_authority_path"]
      secret_store_id                         = amazon_eks.value["secret_store_id"]
      secret_store_role_arn_key               = amazon_eks.value["secret_store_role_arn_key"]
      secret_store_role_arn_path              = amazon_eks.value["secret_store_role_arn_path"]
      secret_store_role_external_id_key       = amazon_eks.value["secret_store_role_external_id_key"]
      secret_store_role_external_id_path      = amazon_eks.value["secret_store_role_external_id_path"]
      secret_store_secret_access_key_key      = amazon_eks.value["secret_store_secret_access_key_key"]
      secret_store_secret_access_key_path     = amazon_eks.value["secret_store_secret_access_key_path"]
      tags                                    = amazon_eks.value["tags"]
    }
  }

  dynamic "amazon_es" {
    for_each = var.amazon_es
    content {
      access_key                          = amazon_es.value["access_key"]
      endpoint                            = amazon_es.value["endpoint"]
      name                                = amazon_es.value["name"]
      region                              = amazon_es.value["region"]
      role_arn                            = amazon_es.value["role_arn"]
      role_external_id                    = amazon_es.value["role_external_id"]
      secret_access_key                   = amazon_es.value["secret_access_key"]
      secret_store_access_key_key         = amazon_es.value["secret_store_access_key_key"]
      secret_store_access_key_path        = amazon_es.value["secret_store_access_key_path"]
      secret_store_id                     = amazon_es.value["secret_store_id"]
      secret_store_role_arn_key           = amazon_es.value["secret_store_role_arn_key"]
      secret_store_role_arn_path          = amazon_es.value["secret_store_role_arn_path"]
      secret_store_role_external_id_key   = amazon_es.value["secret_store_role_external_id_key"]
      secret_store_role_external_id_path  = amazon_es.value["secret_store_role_external_id_path"]
      secret_store_secret_access_key_key  = amazon_es.value["secret_store_secret_access_key_key"]
      secret_store_secret_access_key_path = amazon_es.value["secret_store_secret_access_key_path"]
      tags                                = amazon_es.value["tags"]
    }
  }

  dynamic "athena" {
    for_each = var.athena
    content {
      access_key                          = athena.value["access_key"]
      name                                = athena.value["name"]
      output                              = athena.value["output"]
      region                              = athena.value["region"]
      role_arn                            = athena.value["role_arn"]
      role_external_id                    = athena.value["role_external_id"]
      secret_access_key                   = athena.value["secret_access_key"]
      secret_store_access_key_key         = athena.value["secret_store_access_key_key"]
      secret_store_access_key_path        = athena.value["secret_store_access_key_path"]
      secret_store_id                     = athena.value["secret_store_id"]
      secret_store_role_arn_key           = athena.value["secret_store_role_arn_key"]
      secret_store_role_arn_path          = athena.value["secret_store_role_arn_path"]
      secret_store_role_external_id_key   = athena.value["secret_store_role_external_id_key"]
      secret_store_role_external_id_path  = athena.value["secret_store_role_external_id_path"]
      secret_store_secret_access_key_key  = athena.value["secret_store_secret_access_key_key"]
      secret_store_secret_access_key_path = athena.value["secret_store_secret_access_key_path"]
      tags                                = athena.value["tags"]
    }
  }

  dynamic "aurora_mysql" {
    for_each = var.aurora_mysql
    content {
      database                   = aurora_mysql.value["database"]
      hostname                   = aurora_mysql.value["hostname"]
      name                       = aurora_mysql.value["name"]
      password                   = aurora_mysql.value["password"]
      port                       = aurora_mysql.value["port"]
      secret_store_id            = aurora_mysql.value["secret_store_id"]
      secret_store_password_key  = aurora_mysql.value["secret_store_password_key"]
      secret_store_password_path = aurora_mysql.value["secret_store_password_path"]
      secret_store_username_key  = aurora_mysql.value["secret_store_username_key"]
      secret_store_username_path = aurora_mysql.value["secret_store_username_path"]
      tags                       = aurora_mysql.value["tags"]
      username                   = aurora_mysql.value["username"]
    }
  }

  dynamic "aurora_postgres" {
    for_each = var.aurora_postgres
    content {
      database                   = aurora_postgres.value["database"]
      hostname                   = aurora_postgres.value["hostname"]
      name                       = aurora_postgres.value["name"]
      override_database          = aurora_postgres.value["override_database"]
      password                   = aurora_postgres.value["password"]
      port                       = aurora_postgres.value["port"]
      secret_store_id            = aurora_postgres.value["secret_store_id"]
      secret_store_password_key  = aurora_postgres.value["secret_store_password_key"]
      secret_store_password_path = aurora_postgres.value["secret_store_password_path"]
      secret_store_username_key  = aurora_postgres.value["secret_store_username_key"]
      secret_store_username_path = aurora_postgres.value["secret_store_username_path"]
      tags                       = aurora_postgres.value["tags"]
      username                   = aurora_postgres.value["username"]
    }
  }

  dynamic "aws" {
    for_each = var.aws
    content {
      access_key                          = aws.value["access_key"]
      healthcheck_region                  = aws.value["healthcheck_region"]
      name                                = aws.value["name"]
      role_arn                            = aws.value["role_arn"]
      role_external_id                    = aws.value["role_external_id"]
      secret_access_key                   = aws.value["secret_access_key"]
      secret_store_access_key_key         = aws.value["secret_store_access_key_key"]
      secret_store_access_key_path        = aws.value["secret_store_access_key_path"]
      secret_store_id                     = aws.value["secret_store_id"]
      secret_store_role_arn_key           = aws.value["secret_store_role_arn_key"]
      secret_store_role_arn_path          = aws.value["secret_store_role_arn_path"]
      secret_store_role_external_id_key   = aws.value["secret_store_role_external_id_key"]
      secret_store_role_external_id_path  = aws.value["secret_store_role_external_id_path"]
      secret_store_secret_access_key_key  = aws.value["secret_store_secret_access_key_key"]
      secret_store_secret_access_key_path = aws.value["secret_store_secret_access_key_path"]
      tags                                = aws.value["tags"]
    }
  }

  dynamic "big_query" {
    for_each = var.big_query
    content {
      endpoint                      = big_query.value["endpoint"]
      name                          = big_query.value["name"]
      private_key                   = big_query.value["private_key"]
      project                       = big_query.value["project"]
      secret_store_id               = big_query.value["secret_store_id"]
      secret_store_private_key_key  = big_query.value["secret_store_private_key_key"]
      secret_store_private_key_path = big_query.value["secret_store_private_key_path"]
      tags                          = big_query.value["tags"]
      username                      = big_query.value["username"]
    }
  }

  dynamic "cassandra" {
    for_each = var.cassandra
    content {
      hostname                   = cassandra.value["hostname"]
      name                       = cassandra.value["name"]
      password                   = cassandra.value["password"]
      port                       = cassandra.value["port"]
      secret_store_id            = cassandra.value["secret_store_id"]
      secret_store_password_key  = cassandra.value["secret_store_password_key"]
      secret_store_password_path = cassandra.value["secret_store_password_path"]
      secret_store_username_key  = cassandra.value["secret_store_username_key"]
      secret_store_username_path = cassandra.value["secret_store_username_path"]
      tags                       = cassandra.value["tags"]
      tls_required               = cassandra.value["tls_required"]
      username                   = cassandra.value["username"]
    }
  }

  dynamic "citus" {
    for_each = var.citus
    content {
      database                   = citus.value["database"]
      hostname                   = citus.value["hostname"]
      name                       = citus.value["name"]
      override_database          = citus.value["override_database"]
      password                   = citus.value["password"]
      port                       = citus.value["port"]
      secret_store_id            = citus.value["secret_store_id"]
      secret_store_password_key  = citus.value["secret_store_password_key"]
      secret_store_password_path = citus.value["secret_store_password_path"]
      secret_store_username_key  = citus.value["secret_store_username_key"]
      secret_store_username_path = citus.value["secret_store_username_path"]
      tags                       = citus.value["tags"]
      username                   = citus.value["username"]
    }
  }

  dynamic "clustrix" {
    for_each = var.clustrix
    content {
      database                   = clustrix.value["database"]
      hostname                   = clustrix.value["hostname"]
      name                       = clustrix.value["name"]
      password                   = clustrix.value["password"]
      port                       = clustrix.value["port"]
      secret_store_id            = clustrix.value["secret_store_id"]
      secret_store_password_key  = clustrix.value["secret_store_password_key"]
      secret_store_password_path = clustrix.value["secret_store_password_path"]
      secret_store_username_key  = clustrix.value["secret_store_username_key"]
      secret_store_username_path = clustrix.value["secret_store_username_path"]
      tags                       = clustrix.value["tags"]
      username                   = clustrix.value["username"]
    }
  }

  dynamic "cockroach" {
    for_each = var.cockroach
    content {
      database                   = cockroach.value["database"]
      hostname                   = cockroach.value["hostname"]
      name                       = cockroach.value["name"]
      override_database          = cockroach.value["override_database"]
      password                   = cockroach.value["password"]
      port                       = cockroach.value["port"]
      secret_store_id            = cockroach.value["secret_store_id"]
      secret_store_password_key  = cockroach.value["secret_store_password_key"]
      secret_store_password_path = cockroach.value["secret_store_password_path"]
      secret_store_username_key  = cockroach.value["secret_store_username_key"]
      secret_store_username_path = cockroach.value["secret_store_username_path"]
      tags                       = cockroach.value["tags"]
      username                   = cockroach.value["username"]
    }
  }

  dynamic "db_2_i" {
    for_each = var.db_2_i
    content {
      hostname                   = db_2_i.value["hostname"]
      name                       = db_2_i.value["name"]
      password                   = db_2_i.value["password"]
      port                       = db_2_i.value["port"]
      secret_store_id            = db_2_i.value["secret_store_id"]
      secret_store_password_key  = db_2_i.value["secret_store_password_key"]
      secret_store_password_path = db_2_i.value["secret_store_password_path"]
      secret_store_username_key  = db_2_i.value["secret_store_username_key"]
      secret_store_username_path = db_2_i.value["secret_store_username_path"]
      tags                       = db_2_i.value["tags"]
      tls_required               = db_2_i.value["tls_required"]
      username                   = db_2_i.value["username"]
    }
  }

  dynamic "db_2_luw" {
    for_each = var.db_2_luw
    content {
      database                   = db_2_luw.value["database"]
      hostname                   = db_2_luw.value["hostname"]
      name                       = db_2_luw.value["name"]
      password                   = db_2_luw.value["password"]
      port                       = db_2_luw.value["port"]
      secret_store_id            = db_2_luw.value["secret_store_id"]
      secret_store_password_key  = db_2_luw.value["secret_store_password_key"]
      secret_store_password_path = db_2_luw.value["secret_store_password_path"]
      secret_store_username_key  = db_2_luw.value["secret_store_username_key"]
      secret_store_username_path = db_2_luw.value["secret_store_username_path"]
      tags                       = db_2_luw.value["tags"]
      username                   = db_2_luw.value["username"]
    }
  }

  dynamic "druid" {
    for_each = var.druid
    content {
      hostname                   = druid.value["hostname"]
      name                       = druid.value["name"]
      password                   = druid.value["password"]
      port                       = druid.value["port"]
      secret_store_id            = druid.value["secret_store_id"]
      secret_store_password_key  = druid.value["secret_store_password_key"]
      secret_store_password_path = druid.value["secret_store_password_path"]
      secret_store_username_key  = druid.value["secret_store_username_key"]
      secret_store_username_path = druid.value["secret_store_username_path"]
      tags                       = druid.value["tags"]
      username                   = druid.value["username"]
    }
  }

  dynamic "dynamo_db" {
    for_each = var.dynamo_db
    content {
      access_key                          = dynamo_db.value["access_key"]
      endpoint                            = dynamo_db.value["endpoint"]
      name                                = dynamo_db.value["name"]
      region                              = dynamo_db.value["region"]
      role_arn                            = dynamo_db.value["role_arn"]
      role_external_id                    = dynamo_db.value["role_external_id"]
      secret_access_key                   = dynamo_db.value["secret_access_key"]
      secret_store_access_key_key         = dynamo_db.value["secret_store_access_key_key"]
      secret_store_access_key_path        = dynamo_db.value["secret_store_access_key_path"]
      secret_store_id                     = dynamo_db.value["secret_store_id"]
      secret_store_role_arn_key           = dynamo_db.value["secret_store_role_arn_key"]
      secret_store_role_arn_path          = dynamo_db.value["secret_store_role_arn_path"]
      secret_store_role_external_id_key   = dynamo_db.value["secret_store_role_external_id_key"]
      secret_store_role_external_id_path  = dynamo_db.value["secret_store_role_external_id_path"]
      secret_store_secret_access_key_key  = dynamo_db.value["secret_store_secret_access_key_key"]
      secret_store_secret_access_key_path = dynamo_db.value["secret_store_secret_access_key_path"]
      tags                                = dynamo_db.value["tags"]
    }
  }

  dynamic "elastic" {
    for_each = var.elastic
    content {
      hostname                   = elastic.value["hostname"]
      name                       = elastic.value["name"]
      password                   = elastic.value["password"]
      port                       = elastic.value["port"]
      secret_store_id            = elastic.value["secret_store_id"]
      secret_store_password_key  = elastic.value["secret_store_password_key"]
      secret_store_password_path = elastic.value["secret_store_password_path"]
      secret_store_username_key  = elastic.value["secret_store_username_key"]
      secret_store_username_path = elastic.value["secret_store_username_path"]
      tags                       = elastic.value["tags"]
      tls_required               = elastic.value["tls_required"]
      username                   = elastic.value["username"]
    }
  }

  dynamic "elasticache_redis" {
    for_each = var.elasticache_redis
    content {
      hostname                   = elasticache_redis.value["hostname"]
      name                       = elasticache_redis.value["name"]
      password                   = elasticache_redis.value["password"]
      port                       = elasticache_redis.value["port"]
      secret_store_id            = elasticache_redis.value["secret_store_id"]
      secret_store_password_key  = elasticache_redis.value["secret_store_password_key"]
      secret_store_password_path = elasticache_redis.value["secret_store_password_path"]
      tags                       = elasticache_redis.value["tags"]
      tls_required               = elasticache_redis.value["tls_required"]
    }
  }

  dynamic "google_gke" {
    for_each = var.google_gke
    content {
      certificate_authority                   = google_gke.value["certificate_authority"]
      endpoint                                = google_gke.value["endpoint"]
      healthcheck_namespace                   = google_gke.value["healthcheck_namespace"]
      name                                    = google_gke.value["name"]
      secret_store_certificate_authority_key  = google_gke.value["secret_store_certificate_authority_key"]
      secret_store_certificate_authority_path = google_gke.value["secret_store_certificate_authority_path"]
      secret_store_id                         = google_gke.value["secret_store_id"]
      secret_store_service_account_key_key    = google_gke.value["secret_store_service_account_key_key"]
      secret_store_service_account_key_path   = google_gke.value["secret_store_service_account_key_path"]
      service_account_key                     = google_gke.value["service_account_key"]
      tags                                    = google_gke.value["tags"]
    }
  }

  dynamic "greenplum" {
    for_each = var.greenplum
    content {
      database                   = greenplum.value["database"]
      hostname                   = greenplum.value["hostname"]
      name                       = greenplum.value["name"]
      override_database          = greenplum.value["override_database"]
      password                   = greenplum.value["password"]
      port                       = greenplum.value["port"]
      secret_store_id            = greenplum.value["secret_store_id"]
      secret_store_password_key  = greenplum.value["secret_store_password_key"]
      secret_store_password_path = greenplum.value["secret_store_password_path"]
      secret_store_username_key  = greenplum.value["secret_store_username_key"]
      secret_store_username_path = greenplum.value["secret_store_username_path"]
      tags                       = greenplum.value["tags"]
      username                   = greenplum.value["username"]
    }
  }

  dynamic "http_auth" {
    for_each = var.http_auth
    content {
      auth_header                   = http_auth.value["auth_header"]
      default_path                  = http_auth.value["default_path"]
      headers_blacklist             = http_auth.value["headers_blacklist"]
      healthcheck_path              = http_auth.value["healthcheck_path"]
      name                          = http_auth.value["name"]
      secret_store_auth_header_key  = http_auth.value["secret_store_auth_header_key"]
      secret_store_auth_header_path = http_auth.value["secret_store_auth_header_path"]
      secret_store_id               = http_auth.value["secret_store_id"]
      subdomain                     = http_auth.value["subdomain"]
      tags                          = http_auth.value["tags"]
      url                           = http_auth.value["url"]
    }
  }

  dynamic "http_basic_auth" {
    for_each = var.http_basic_auth
    content {
      default_path               = http_basic_auth.value["default_path"]
      headers_blacklist          = http_basic_auth.value["headers_blacklist"]
      healthcheck_path           = http_basic_auth.value["healthcheck_path"]
      name                       = http_basic_auth.value["name"]
      password                   = http_basic_auth.value["password"]
      secret_store_id            = http_basic_auth.value["secret_store_id"]
      secret_store_password_key  = http_basic_auth.value["secret_store_password_key"]
      secret_store_password_path = http_basic_auth.value["secret_store_password_path"]
      secret_store_username_key  = http_basic_auth.value["secret_store_username_key"]
      secret_store_username_path = http_basic_auth.value["secret_store_username_path"]
      subdomain                  = http_basic_auth.value["subdomain"]
      tags                       = http_basic_auth.value["tags"]
      url                        = http_basic_auth.value["url"]
      username                   = http_basic_auth.value["username"]
    }
  }

  dynamic "http_no_auth" {
    for_each = var.http_no_auth
    content {
      default_path      = http_no_auth.value["default_path"]
      headers_blacklist = http_no_auth.value["headers_blacklist"]
      healthcheck_path  = http_no_auth.value["healthcheck_path"]
      name              = http_no_auth.value["name"]
      secret_store_id   = http_no_auth.value["secret_store_id"]
      subdomain         = http_no_auth.value["subdomain"]
      tags              = http_no_auth.value["tags"]
      url               = http_no_auth.value["url"]
    }
  }

  dynamic "kubernetes" {
    for_each = var.kubernetes
    content {
      certificate_authority                   = kubernetes.value["certificate_authority"]
      client_certificate                      = kubernetes.value["client_certificate"]
      client_key                              = kubernetes.value["client_key"]
      healthcheck_namespace                   = kubernetes.value["healthcheck_namespace"]
      hostname                                = kubernetes.value["hostname"]
      name                                    = kubernetes.value["name"]
      port                                    = kubernetes.value["port"]
      secret_store_certificate_authority_key  = kubernetes.value["secret_store_certificate_authority_key"]
      secret_store_certificate_authority_path = kubernetes.value["secret_store_certificate_authority_path"]
      secret_store_client_certificate_key     = kubernetes.value["secret_store_client_certificate_key"]
      secret_store_client_certificate_path    = kubernetes.value["secret_store_client_certificate_path"]
      secret_store_client_key_key             = kubernetes.value["secret_store_client_key_key"]
      secret_store_client_key_path            = kubernetes.value["secret_store_client_key_path"]
      secret_store_id                         = kubernetes.value["secret_store_id"]
      tags                                    = kubernetes.value["tags"]
    }
  }

  dynamic "kubernetes_basic_auth" {
    for_each = var.kubernetes_basic_auth
    content {
      healthcheck_namespace      = kubernetes_basic_auth.value["healthcheck_namespace"]
      hostname                   = kubernetes_basic_auth.value["hostname"]
      name                       = kubernetes_basic_auth.value["name"]
      password                   = kubernetes_basic_auth.value["password"]
      port                       = kubernetes_basic_auth.value["port"]
      secret_store_id            = kubernetes_basic_auth.value["secret_store_id"]
      secret_store_password_key  = kubernetes_basic_auth.value["secret_store_password_key"]
      secret_store_password_path = kubernetes_basic_auth.value["secret_store_password_path"]
      secret_store_username_key  = kubernetes_basic_auth.value["secret_store_username_key"]
      secret_store_username_path = kubernetes_basic_auth.value["secret_store_username_path"]
      tags                       = kubernetes_basic_auth.value["tags"]
      username                   = kubernetes_basic_auth.value["username"]
    }
  }

  dynamic "kubernetes_service_account" {
    for_each = var.kubernetes_service_account
    content {
      healthcheck_namespace   = kubernetes_service_account.value["healthcheck_namespace"]
      hostname                = kubernetes_service_account.value["hostname"]
      name                    = kubernetes_service_account.value["name"]
      port                    = kubernetes_service_account.value["port"]
      secret_store_id         = kubernetes_service_account.value["secret_store_id"]
      secret_store_token_key  = kubernetes_service_account.value["secret_store_token_key"]
      secret_store_token_path = kubernetes_service_account.value["secret_store_token_path"]
      tags                    = kubernetes_service_account.value["tags"]
      token                   = kubernetes_service_account.value["token"]
    }
  }

  dynamic "maria" {
    for_each = var.maria
    content {
      database                   = maria.value["database"]
      hostname                   = maria.value["hostname"]
      name                       = maria.value["name"]
      password                   = maria.value["password"]
      port                       = maria.value["port"]
      secret_store_id            = maria.value["secret_store_id"]
      secret_store_password_key  = maria.value["secret_store_password_key"]
      secret_store_password_path = maria.value["secret_store_password_path"]
      secret_store_username_key  = maria.value["secret_store_username_key"]
      secret_store_username_path = maria.value["secret_store_username_path"]
      tags                       = maria.value["tags"]
      username                   = maria.value["username"]
    }
  }

  dynamic "memcached" {
    for_each = var.memcached
    content {
      hostname        = memcached.value["hostname"]
      name            = memcached.value["name"]
      port            = memcached.value["port"]
      secret_store_id = memcached.value["secret_store_id"]
      tags            = memcached.value["tags"]
    }
  }

  dynamic "memsql" {
    for_each = var.memsql
    content {
      database                   = memsql.value["database"]
      hostname                   = memsql.value["hostname"]
      name                       = memsql.value["name"]
      password                   = memsql.value["password"]
      port                       = memsql.value["port"]
      secret_store_id            = memsql.value["secret_store_id"]
      secret_store_password_key  = memsql.value["secret_store_password_key"]
      secret_store_password_path = memsql.value["secret_store_password_path"]
      secret_store_username_key  = memsql.value["secret_store_username_key"]
      secret_store_username_path = memsql.value["secret_store_username_path"]
      tags                       = memsql.value["tags"]
      username                   = memsql.value["username"]
    }
  }

  dynamic "mongo_host" {
    for_each = var.mongo_host
    content {
      auth_database              = mongo_host.value["auth_database"]
      hostname                   = mongo_host.value["hostname"]
      name                       = mongo_host.value["name"]
      password                   = mongo_host.value["password"]
      port                       = mongo_host.value["port"]
      secret_store_id            = mongo_host.value["secret_store_id"]
      secret_store_password_key  = mongo_host.value["secret_store_password_key"]
      secret_store_password_path = mongo_host.value["secret_store_password_path"]
      secret_store_username_key  = mongo_host.value["secret_store_username_key"]
      secret_store_username_path = mongo_host.value["secret_store_username_path"]
      tags                       = mongo_host.value["tags"]
      tls_required               = mongo_host.value["tls_required"]
      username                   = mongo_host.value["username"]
    }
  }

  dynamic "mongo_legacy_host" {
    for_each = var.mongo_legacy_host
    content {
      auth_database              = mongo_legacy_host.value["auth_database"]
      hostname                   = mongo_legacy_host.value["hostname"]
      name                       = mongo_legacy_host.value["name"]
      password                   = mongo_legacy_host.value["password"]
      port                       = mongo_legacy_host.value["port"]
      replica_set                = mongo_legacy_host.value["replica_set"]
      secret_store_id            = mongo_legacy_host.value["secret_store_id"]
      secret_store_password_key  = mongo_legacy_host.value["secret_store_password_key"]
      secret_store_password_path = mongo_legacy_host.value["secret_store_password_path"]
      secret_store_username_key  = mongo_legacy_host.value["secret_store_username_key"]
      secret_store_username_path = mongo_legacy_host.value["secret_store_username_path"]
      tags                       = mongo_legacy_host.value["tags"]
      tls_required               = mongo_legacy_host.value["tls_required"]
      username                   = mongo_legacy_host.value["username"]
    }
  }

  dynamic "mongo_legacy_replicaset" {
    for_each = var.mongo_legacy_replicaset
    content {
      auth_database              = mongo_legacy_replicaset.value["auth_database"]
      connect_to_replica         = mongo_legacy_replicaset.value["connect_to_replica"]
      hostname                   = mongo_legacy_replicaset.value["hostname"]
      name                       = mongo_legacy_replicaset.value["name"]
      password                   = mongo_legacy_replicaset.value["password"]
      port                       = mongo_legacy_replicaset.value["port"]
      replica_set                = mongo_legacy_replicaset.value["replica_set"]
      secret_store_id            = mongo_legacy_replicaset.value["secret_store_id"]
      secret_store_password_key  = mongo_legacy_replicaset.value["secret_store_password_key"]
      secret_store_password_path = mongo_legacy_replicaset.value["secret_store_password_path"]
      secret_store_username_key  = mongo_legacy_replicaset.value["secret_store_username_key"]
      secret_store_username_path = mongo_legacy_replicaset.value["secret_store_username_path"]
      tags                       = mongo_legacy_replicaset.value["tags"]
      tls_required               = mongo_legacy_replicaset.value["tls_required"]
      username                   = mongo_legacy_replicaset.value["username"]
    }
  }

  dynamic "mongo_replica_set" {
    for_each = var.mongo_replica_set
    content {
      auth_database              = mongo_replica_set.value["auth_database"]
      connect_to_replica         = mongo_replica_set.value["connect_to_replica"]
      hostname                   = mongo_replica_set.value["hostname"]
      name                       = mongo_replica_set.value["name"]
      password                   = mongo_replica_set.value["password"]
      port                       = mongo_replica_set.value["port"]
      replica_set                = mongo_replica_set.value["replica_set"]
      secret_store_id            = mongo_replica_set.value["secret_store_id"]
      secret_store_password_key  = mongo_replica_set.value["secret_store_password_key"]
      secret_store_password_path = mongo_replica_set.value["secret_store_password_path"]
      secret_store_username_key  = mongo_replica_set.value["secret_store_username_key"]
      secret_store_username_path = mongo_replica_set.value["secret_store_username_path"]
      tags                       = mongo_replica_set.value["tags"]
      tls_required               = mongo_replica_set.value["tls_required"]
      username                   = mongo_replica_set.value["username"]
    }
  }

  dynamic "mysql" {
    for_each = var.mysql
    content {
      database                   = mysql.value["database"]
      hostname                   = mysql.value["hostname"]
      name                       = mysql.value["name"]
      password                   = mysql.value["password"]
      port                       = mysql.value["port"]
      secret_store_id            = mysql.value["secret_store_id"]
      secret_store_password_key  = mysql.value["secret_store_password_key"]
      secret_store_password_path = mysql.value["secret_store_password_path"]
      secret_store_username_key  = mysql.value["secret_store_username_key"]
      secret_store_username_path = mysql.value["secret_store_username_path"]
      tags                       = mysql.value["tags"]
      username                   = mysql.value["username"]
    }
  }

  dynamic "oracle" {
    for_each = var.oracle
    content {
      database                   = oracle.value["database"]
      hostname                   = oracle.value["hostname"]
      name                       = oracle.value["name"]
      password                   = oracle.value["password"]
      port                       = oracle.value["port"]
      secret_store_id            = oracle.value["secret_store_id"]
      secret_store_password_key  = oracle.value["secret_store_password_key"]
      secret_store_password_path = oracle.value["secret_store_password_path"]
      secret_store_username_key  = oracle.value["secret_store_username_key"]
      secret_store_username_path = oracle.value["secret_store_username_path"]
      tags                       = oracle.value["tags"]
      tls_required               = oracle.value["tls_required"]
      username                   = oracle.value["username"]
    }
  }

  dynamic "postgres" {
    for_each = var.postgres
    content {
      database                   = postgres.value["database"]
      hostname                   = postgres.value["hostname"]
      name                       = postgres.value["name"]
      override_database          = postgres.value["override_database"]
      password                   = postgres.value["password"]
      port                       = postgres.value["port"]
      secret_store_id            = postgres.value["secret_store_id"]
      secret_store_password_key  = postgres.value["secret_store_password_key"]
      secret_store_password_path = postgres.value["secret_store_password_path"]
      secret_store_username_key  = postgres.value["secret_store_username_key"]
      secret_store_username_path = postgres.value["secret_store_username_path"]
      tags                       = postgres.value["tags"]
      username                   = postgres.value["username"]
    }
  }

  dynamic "presto" {
    for_each = var.presto
    content {
      database                   = presto.value["database"]
      hostname                   = presto.value["hostname"]
      name                       = presto.value["name"]
      password                   = presto.value["password"]
      port                       = presto.value["port"]
      secret_store_id            = presto.value["secret_store_id"]
      secret_store_password_key  = presto.value["secret_store_password_key"]
      secret_store_password_path = presto.value["secret_store_password_path"]
      tags                       = presto.value["tags"]
      tls_required               = presto.value["tls_required"]
      username                   = presto.value["username"]
    }
  }

  dynamic "rdp" {
    for_each = var.rdp
    content {
      hostname                   = rdp.value["hostname"]
      name                       = rdp.value["name"]
      password                   = rdp.value["password"]
      port                       = rdp.value["port"]
      secret_store_id            = rdp.value["secret_store_id"]
      secret_store_password_key  = rdp.value["secret_store_password_key"]
      secret_store_password_path = rdp.value["secret_store_password_path"]
      secret_store_username_key  = rdp.value["secret_store_username_key"]
      secret_store_username_path = rdp.value["secret_store_username_path"]
      tags                       = rdp.value["tags"]
      username                   = rdp.value["username"]
    }
  }

  dynamic "redis" {
    for_each = var.redis
    content {
      hostname                   = redis.value["hostname"]
      name                       = redis.value["name"]
      password                   = redis.value["password"]
      port                       = redis.value["port"]
      secret_store_id            = redis.value["secret_store_id"]
      secret_store_password_key  = redis.value["secret_store_password_key"]
      secret_store_password_path = redis.value["secret_store_password_path"]
      tags                       = redis.value["tags"]
    }
  }

  dynamic "redshift" {
    for_each = var.redshift
    content {
      database                   = redshift.value["database"]
      hostname                   = redshift.value["hostname"]
      name                       = redshift.value["name"]
      override_database          = redshift.value["override_database"]
      password                   = redshift.value["password"]
      port                       = redshift.value["port"]
      secret_store_id            = redshift.value["secret_store_id"]
      secret_store_password_key  = redshift.value["secret_store_password_key"]
      secret_store_password_path = redshift.value["secret_store_password_path"]
      secret_store_username_key  = redshift.value["secret_store_username_key"]
      secret_store_username_path = redshift.value["secret_store_username_path"]
      tags                       = redshift.value["tags"]
      username                   = redshift.value["username"]
    }
  }

  dynamic "snowflake" {
    for_each = var.snowflake
    content {
      database                   = snowflake.value["database"]
      hostname                   = snowflake.value["hostname"]
      name                       = snowflake.value["name"]
      password                   = snowflake.value["password"]
      schema                     = snowflake.value["schema"]
      secret_store_id            = snowflake.value["secret_store_id"]
      secret_store_password_key  = snowflake.value["secret_store_password_key"]
      secret_store_password_path = snowflake.value["secret_store_password_path"]
      secret_store_username_key  = snowflake.value["secret_store_username_key"]
      secret_store_username_path = snowflake.value["secret_store_username_path"]
      tags                       = snowflake.value["tags"]
      username                   = snowflake.value["username"]
    }
  }

  dynamic "sql_server" {
    for_each = var.sql_server
    content {
      database                   = sql_server.value["database"]
      hostname                   = sql_server.value["hostname"]
      name                       = sql_server.value["name"]
      override_database          = sql_server.value["override_database"]
      password                   = sql_server.value["password"]
      port                       = sql_server.value["port"]
      schema                     = sql_server.value["schema"]
      secret_store_id            = sql_server.value["secret_store_id"]
      secret_store_password_key  = sql_server.value["secret_store_password_key"]
      secret_store_password_path = sql_server.value["secret_store_password_path"]
      secret_store_username_key  = sql_server.value["secret_store_username_key"]
      secret_store_username_path = sql_server.value["secret_store_username_path"]
      tags                       = sql_server.value["tags"]
      username                   = sql_server.value["username"]
    }
  }

  dynamic "ssh" {
    for_each = var.ssh
    content {
      allow_deprecated_key_exchanges = ssh.value["allow_deprecated_key_exchanges"]
      hostname                       = ssh.value["hostname"]
      name                           = ssh.value["name"]
      port                           = ssh.value["port"]
      port_forwarding                = ssh.value["port_forwarding"]
      secret_store_id                = ssh.value["secret_store_id"]
      tags                           = ssh.value["tags"]
      username                       = ssh.value["username"]
    }
  }

  dynamic "ssh_cert" {
    for_each = var.ssh_cert
    content {
      allow_deprecated_key_exchanges = ssh_cert.value["allow_deprecated_key_exchanges"]
      hostname                       = ssh_cert.value["hostname"]
      name                           = ssh_cert.value["name"]
      port                           = ssh_cert.value["port"]
      port_forwarding                = ssh_cert.value["port_forwarding"]
      secret_store_id                = ssh_cert.value["secret_store_id"]
      tags                           = ssh_cert.value["tags"]
      username                       = ssh_cert.value["username"]
    }
  }

  dynamic "sybase" {
    for_each = var.sybase
    content {
      hostname                   = sybase.value["hostname"]
      name                       = sybase.value["name"]
      password                   = sybase.value["password"]
      port                       = sybase.value["port"]
      secret_store_id            = sybase.value["secret_store_id"]
      secret_store_password_key  = sybase.value["secret_store_password_key"]
      secret_store_password_path = sybase.value["secret_store_password_path"]
      secret_store_username_key  = sybase.value["secret_store_username_key"]
      secret_store_username_path = sybase.value["secret_store_username_path"]
      tags                       = sybase.value["tags"]
      username                   = sybase.value["username"]
    }
  }

  dynamic "sybase_iq" {
    for_each = var.sybase_iq
    content {
      hostname                   = sybase_iq.value["hostname"]
      name                       = sybase_iq.value["name"]
      password                   = sybase_iq.value["password"]
      port                       = sybase_iq.value["port"]
      secret_store_id            = sybase_iq.value["secret_store_id"]
      secret_store_password_key  = sybase_iq.value["secret_store_password_key"]
      secret_store_password_path = sybase_iq.value["secret_store_password_path"]
      secret_store_username_key  = sybase_iq.value["secret_store_username_key"]
      secret_store_username_path = sybase_iq.value["secret_store_username_path"]
      tags                       = sybase_iq.value["tags"]
      username                   = sybase_iq.value["username"]
    }
  }

  dynamic "teradata" {
    for_each = var.teradata
    content {
      hostname                   = teradata.value["hostname"]
      name                       = teradata.value["name"]
      password                   = teradata.value["password"]
      port                       = teradata.value["port"]
      secret_store_id            = teradata.value["secret_store_id"]
      secret_store_password_key  = teradata.value["secret_store_password_key"]
      secret_store_password_path = teradata.value["secret_store_password_path"]
      secret_store_username_key  = teradata.value["secret_store_username_key"]
      secret_store_username_path = teradata.value["secret_store_username_path"]
      tags                       = teradata.value["tags"]
      username                   = teradata.value["username"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sdm_resource.this.id
}

output "this" {
  value = sdm_resource.this
}
```

[top](#index)