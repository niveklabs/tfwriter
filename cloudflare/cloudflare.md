# cloudflare

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "cloudflare" {
  version = "2.15.0"

  # account_id - (optional) is a type of string
  account_id = null
  # api_client_logging - (optional) is a type of bool
  api_client_logging = null
  # api_key - (optional) is a type of string
  api_key = null
  # api_token - (optional) is a type of string
  api_token = null
  # api_user_service_key - (optional) is a type of string
  api_user_service_key = null
  # email - (optional) is a type of string
  email = null
  # max_backoff - (optional) is a type of number
  max_backoff = null
  # min_backoff - (optional) is a type of number
  min_backoff = null
  # retries - (optional) is a type of number
  retries = null
  # rps - (optional) is a type of number
  rps = null
}
```

[top](#index)

### Resources


- [cloudflare_access_application](./r/cloudflare_access_application.md)

- [cloudflare_access_group](./r/cloudflare_access_group.md)

- [cloudflare_access_identity_provider](./r/cloudflare_access_identity_provider.md)

- [cloudflare_access_policy](./r/cloudflare_access_policy.md)

- [cloudflare_access_rule](./r/cloudflare_access_rule.md)

- [cloudflare_access_service_token](./r/cloudflare_access_service_token.md)

- [cloudflare_account_member](./r/cloudflare_account_member.md)

- [cloudflare_api_token](./r/cloudflare_api_token.md)

- [cloudflare_argo](./r/cloudflare_argo.md)

- [cloudflare_authenticated_origin_pulls](./r/cloudflare_authenticated_origin_pulls.md)

- [cloudflare_authenticated_origin_pulls_certificate](./r/cloudflare_authenticated_origin_pulls_certificate.md)

- [cloudflare_byo_ip_prefix](./r/cloudflare_byo_ip_prefix.md)

- [cloudflare_certificate_pack](./r/cloudflare_certificate_pack.md)

- [cloudflare_custom_hostname](./r/cloudflare_custom_hostname.md)

- [cloudflare_custom_hostname_fallback_origin](./r/cloudflare_custom_hostname_fallback_origin.md)

- [cloudflare_custom_pages](./r/cloudflare_custom_pages.md)

- [cloudflare_custom_ssl](./r/cloudflare_custom_ssl.md)

- [cloudflare_filter](./r/cloudflare_filter.md)

- [cloudflare_firewall_rule](./r/cloudflare_firewall_rule.md)

- [cloudflare_healthcheck](./r/cloudflare_healthcheck.md)

- [cloudflare_ip_list](./r/cloudflare_ip_list.md)

- [cloudflare_load_balancer](./r/cloudflare_load_balancer.md)

- [cloudflare_load_balancer_monitor](./r/cloudflare_load_balancer_monitor.md)

- [cloudflare_load_balancer_pool](./r/cloudflare_load_balancer_pool.md)

- [cloudflare_logpull_retention](./r/cloudflare_logpull_retention.md)

- [cloudflare_logpush_job](./r/cloudflare_logpush_job.md)

- [cloudflare_logpush_ownership_challenge](./r/cloudflare_logpush_ownership_challenge.md)

- [cloudflare_origin_ca_certificate](./r/cloudflare_origin_ca_certificate.md)

- [cloudflare_page_rule](./r/cloudflare_page_rule.md)

- [cloudflare_rate_limit](./r/cloudflare_rate_limit.md)

- [cloudflare_record](./r/cloudflare_record.md)

- [cloudflare_spectrum_application](./r/cloudflare_spectrum_application.md)

- [cloudflare_waf_group](./r/cloudflare_waf_group.md)

- [cloudflare_waf_override](./r/cloudflare_waf_override.md)

- [cloudflare_waf_package](./r/cloudflare_waf_package.md)

- [cloudflare_waf_rule](./r/cloudflare_waf_rule.md)

- [cloudflare_worker_route](./r/cloudflare_worker_route.md)

- [cloudflare_worker_script](./r/cloudflare_worker_script.md)

- [cloudflare_workers_kv](./r/cloudflare_workers_kv.md)

- [cloudflare_workers_kv_namespace](./r/cloudflare_workers_kv_namespace.md)

- [cloudflare_zone](./r/cloudflare_zone.md)

- [cloudflare_zone_dnssec](./r/cloudflare_zone_dnssec.md)

- [cloudflare_zone_lockdown](./r/cloudflare_zone_lockdown.md)

- [cloudflare_zone_settings_override](./r/cloudflare_zone_settings_override.md)


[top](#index)

### Datasources


- [cloudflare_api_token_permission_groups](./d/cloudflare_api_token_permission_groups.md)

- [cloudflare_ip_ranges](./d/cloudflare_ip_ranges.md)

- [cloudflare_waf_groups](./d/cloudflare_waf_groups.md)

- [cloudflare_waf_packages](./d/cloudflare_waf_packages.md)

- [cloudflare_waf_rules](./d/cloudflare_waf_rules.md)

- [cloudflare_zone_dnssec](./d/cloudflare_zone_dnssec.md)

- [cloudflare_zones](./d/cloudflare_zones.md)


[top](#index)