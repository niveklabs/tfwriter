# aws

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "aws" {
  version = "3.35.0"

  # access_key - (optional) is a type of string
  access_key = null
  # allowed_account_ids - (optional) is a type of set of string
  allowed_account_ids = []
  # forbidden_account_ids - (optional) is a type of set of string
  forbidden_account_ids = []
  # insecure - (optional) is a type of bool
  insecure = null
  # max_retries - (optional) is a type of number
  max_retries = null
  # profile - (optional) is a type of string
  profile = null
  # region - (required) is a type of string
  region = null
  # s3_force_path_style - (optional) is a type of bool
  s3_force_path_style = null
  # secret_key - (optional) is a type of string
  secret_key = null
  # shared_credentials_file - (optional) is a type of string
  shared_credentials_file = null
  # skip_credentials_validation - (optional) is a type of bool
  skip_credentials_validation = null
  # skip_get_ec2_platforms - (optional) is a type of bool
  skip_get_ec2_platforms = null
  # skip_metadata_api_check - (optional) is a type of bool
  skip_metadata_api_check = null
  # skip_region_validation - (optional) is a type of bool
  skip_region_validation = null
  # skip_requesting_account_id - (optional) is a type of bool
  skip_requesting_account_id = null
  # token - (optional) is a type of string
  token = null

  # NestingList
  assume_role {
    # duration_seconds - (optional) is a type of number
    duration_seconds = null
    # external_id - (optional) is a type of string
    external_id = null
    # policy - (optional) is a type of string
    policy = null
    # policy_arns - (optional) is a type of set of string
    policy_arns = []
    # role_arn - (optional) is a type of string
    role_arn = null
    # session_name - (optional) is a type of string
    session_name = null
    # tags - (optional) is a type of map of string
    tags = {}
    # transitive_tag_keys - (optional) is a type of set of string
    transitive_tag_keys = []
  }

  # NestingList
  default_tags {
    # tags - (optional) is a type of map of string
    tags = {}
  }

  # NestingSet
  endpoints {
    # accessanalyzer - (optional) is a type of string
    accessanalyzer = null
    # acm - (optional) is a type of string
    acm = null
    # acmpca - (optional) is a type of string
    acmpca = null
    # amplify - (optional) is a type of string
    amplify = null
    # apigateway - (optional) is a type of string
    apigateway = null
    # applicationautoscaling - (optional) is a type of string
    applicationautoscaling = null
    # applicationinsights - (optional) is a type of string
    applicationinsights = null
    # appmesh - (optional) is a type of string
    appmesh = null
    # appstream - (optional) is a type of string
    appstream = null
    # appsync - (optional) is a type of string
    appsync = null
    # athena - (optional) is a type of string
    athena = null
    # auditmanager - (optional) is a type of string
    auditmanager = null
    # autoscaling - (optional) is a type of string
    autoscaling = null
    # autoscalingplans - (optional) is a type of string
    autoscalingplans = null
    # backup - (optional) is a type of string
    backup = null
    # batch - (optional) is a type of string
    batch = null
    # budgets - (optional) is a type of string
    budgets = null
    # cloud9 - (optional) is a type of string
    cloud9 = null
    # cloudformation - (optional) is a type of string
    cloudformation = null
    # cloudfront - (optional) is a type of string
    cloudfront = null
    # cloudhsm - (optional) is a type of string
    cloudhsm = null
    # cloudsearch - (optional) is a type of string
    cloudsearch = null
    # cloudtrail - (optional) is a type of string
    cloudtrail = null
    # cloudwatch - (optional) is a type of string
    cloudwatch = null
    # cloudwatchevents - (optional) is a type of string
    cloudwatchevents = null
    # cloudwatchlogs - (optional) is a type of string
    cloudwatchlogs = null
    # codeartifact - (optional) is a type of string
    codeartifact = null
    # codebuild - (optional) is a type of string
    codebuild = null
    # codecommit - (optional) is a type of string
    codecommit = null
    # codedeploy - (optional) is a type of string
    codedeploy = null
    # codepipeline - (optional) is a type of string
    codepipeline = null
    # codestarconnections - (optional) is a type of string
    codestarconnections = null
    # cognitoidentity - (optional) is a type of string
    cognitoidentity = null
    # cognitoidp - (optional) is a type of string
    cognitoidp = null
    # configservice - (optional) is a type of string
    configservice = null
    # connect - (optional) is a type of string
    connect = null
    # cur - (optional) is a type of string
    cur = null
    # dataexchange - (optional) is a type of string
    dataexchange = null
    # datapipeline - (optional) is a type of string
    datapipeline = null
    # datasync - (optional) is a type of string
    datasync = null
    # dax - (optional) is a type of string
    dax = null
    # devicefarm - (optional) is a type of string
    devicefarm = null
    # directconnect - (optional) is a type of string
    directconnect = null
    # dlm - (optional) is a type of string
    dlm = null
    # dms - (optional) is a type of string
    dms = null
    # docdb - (optional) is a type of string
    docdb = null
    # ds - (optional) is a type of string
    ds = null
    # dynamodb - (optional) is a type of string
    dynamodb = null
    # ec2 - (optional) is a type of string
    ec2 = null
    # ecr - (optional) is a type of string
    ecr = null
    # ecrpublic - (optional) is a type of string
    ecrpublic = null
    # ecs - (optional) is a type of string
    ecs = null
    # efs - (optional) is a type of string
    efs = null
    # eks - (optional) is a type of string
    eks = null
    # elasticache - (optional) is a type of string
    elasticache = null
    # elasticbeanstalk - (optional) is a type of string
    elasticbeanstalk = null
    # elastictranscoder - (optional) is a type of string
    elastictranscoder = null
    # elb - (optional) is a type of string
    elb = null
    # emr - (optional) is a type of string
    emr = null
    # emrcontainers - (optional) is a type of string
    emrcontainers = null
    # es - (optional) is a type of string
    es = null
    # firehose - (optional) is a type of string
    firehose = null
    # fms - (optional) is a type of string
    fms = null
    # forecast - (optional) is a type of string
    forecast = null
    # fsx - (optional) is a type of string
    fsx = null
    # gamelift - (optional) is a type of string
    gamelift = null
    # glacier - (optional) is a type of string
    glacier = null
    # globalaccelerator - (optional) is a type of string
    globalaccelerator = null
    # glue - (optional) is a type of string
    glue = null
    # greengrass - (optional) is a type of string
    greengrass = null
    # guardduty - (optional) is a type of string
    guardduty = null
    # iam - (optional) is a type of string
    iam = null
    # identitystore - (optional) is a type of string
    identitystore = null
    # imagebuilder - (optional) is a type of string
    imagebuilder = null
    # inspector - (optional) is a type of string
    inspector = null
    # iot - (optional) is a type of string
    iot = null
    # iotanalytics - (optional) is a type of string
    iotanalytics = null
    # iotevents - (optional) is a type of string
    iotevents = null
    # kafka - (optional) is a type of string
    kafka = null
    # kinesis - (optional) is a type of string
    kinesis = null
    # kinesisanalytics - (optional) is a type of string
    kinesisanalytics = null
    # kinesisanalyticsv2 - (optional) is a type of string
    kinesisanalyticsv2 = null
    # kinesisvideo - (optional) is a type of string
    kinesisvideo = null
    # kms - (optional) is a type of string
    kms = null
    # lakeformation - (optional) is a type of string
    lakeformation = null
    # lambda - (optional) is a type of string
    lambda = null
    # lexmodels - (optional) is a type of string
    lexmodels = null
    # licensemanager - (optional) is a type of string
    licensemanager = null
    # lightsail - (optional) is a type of string
    lightsail = null
    # macie - (optional) is a type of string
    macie = null
    # macie2 - (optional) is a type of string
    macie2 = null
    # managedblockchain - (optional) is a type of string
    managedblockchain = null
    # marketplacecatalog - (optional) is a type of string
    marketplacecatalog = null
    # mediaconnect - (optional) is a type of string
    mediaconnect = null
    # mediaconvert - (optional) is a type of string
    mediaconvert = null
    # medialive - (optional) is a type of string
    medialive = null
    # mediapackage - (optional) is a type of string
    mediapackage = null
    # mediastore - (optional) is a type of string
    mediastore = null
    # mediastoredata - (optional) is a type of string
    mediastoredata = null
    # mq - (optional) is a type of string
    mq = null
    # mwaa - (optional) is a type of string
    mwaa = null
    # neptune - (optional) is a type of string
    neptune = null
    # networkfirewall - (optional) is a type of string
    networkfirewall = null
    # networkmanager - (optional) is a type of string
    networkmanager = null
    # opsworks - (optional) is a type of string
    opsworks = null
    # organizations - (optional) is a type of string
    organizations = null
    # outposts - (optional) is a type of string
    outposts = null
    # personalize - (optional) is a type of string
    personalize = null
    # pinpoint - (optional) is a type of string
    pinpoint = null
    # pricing - (optional) is a type of string
    pricing = null
    # qldb - (optional) is a type of string
    qldb = null
    # quicksight - (optional) is a type of string
    quicksight = null
    # ram - (optional) is a type of string
    ram = null
    # rds - (optional) is a type of string
    rds = null
    # redshift - (optional) is a type of string
    redshift = null
    # resourcegroups - (optional) is a type of string
    resourcegroups = null
    # resourcegroupstaggingapi - (optional) is a type of string
    resourcegroupstaggingapi = null
    # route53 - (optional) is a type of string
    route53 = null
    # route53domains - (optional) is a type of string
    route53domains = null
    # route53resolver - (optional) is a type of string
    route53resolver = null
    # s3 - (optional) is a type of string
    s3 = null
    # s3control - (optional) is a type of string
    s3control = null
    # s3outposts - (optional) is a type of string
    s3outposts = null
    # sagemaker - (optional) is a type of string
    sagemaker = null
    # sdb - (optional) is a type of string
    sdb = null
    # secretsmanager - (optional) is a type of string
    secretsmanager = null
    # securityhub - (optional) is a type of string
    securityhub = null
    # serverlessrepo - (optional) is a type of string
    serverlessrepo = null
    # servicecatalog - (optional) is a type of string
    servicecatalog = null
    # servicediscovery - (optional) is a type of string
    servicediscovery = null
    # servicequotas - (optional) is a type of string
    servicequotas = null
    # ses - (optional) is a type of string
    ses = null
    # shield - (optional) is a type of string
    shield = null
    # signer - (optional) is a type of string
    signer = null
    # sns - (optional) is a type of string
    sns = null
    # sqs - (optional) is a type of string
    sqs = null
    # ssm - (optional) is a type of string
    ssm = null
    # ssoadmin - (optional) is a type of string
    ssoadmin = null
    # stepfunctions - (optional) is a type of string
    stepfunctions = null
    # storagegateway - (optional) is a type of string
    storagegateway = null
    # sts - (optional) is a type of string
    sts = null
    # swf - (optional) is a type of string
    swf = null
    # synthetics - (optional) is a type of string
    synthetics = null
    # timestreamwrite - (optional) is a type of string
    timestreamwrite = null
    # transfer - (optional) is a type of string
    transfer = null
    # waf - (optional) is a type of string
    waf = null
    # wafregional - (optional) is a type of string
    wafregional = null
    # wafv2 - (optional) is a type of string
    wafv2 = null
    # worklink - (optional) is a type of string
    worklink = null
    # workmail - (optional) is a type of string
    workmail = null
    # workspaces - (optional) is a type of string
    workspaces = null
    # xray - (optional) is a type of string
    xray = null
  }

  # NestingList
  ignore_tags {
    # key_prefixes - (optional) is a type of set of string
    key_prefixes = []
    # keys - (optional) is a type of set of string
    keys = []
  }
}
```

[top](#index)

### Resources


- [aws_accessanalyzer_analyzer](./r/aws_accessanalyzer_analyzer.md)

- [aws_acm_certificate](./r/aws_acm_certificate.md)

- [aws_acm_certificate_validation](./r/aws_acm_certificate_validation.md)

- [aws_acmpca_certificate](./r/aws_acmpca_certificate.md)

- [aws_acmpca_certificate_authority](./r/aws_acmpca_certificate_authority.md)

- [aws_acmpca_certificate_authority_certificate](./r/aws_acmpca_certificate_authority_certificate.md)

- [aws_alb](./r/aws_alb.md)

- [aws_alb_listener](./r/aws_alb_listener.md)

- [aws_alb_listener_certificate](./r/aws_alb_listener_certificate.md)

- [aws_alb_listener_rule](./r/aws_alb_listener_rule.md)

- [aws_alb_target_group](./r/aws_alb_target_group.md)

- [aws_alb_target_group_attachment](./r/aws_alb_target_group_attachment.md)

- [aws_ami](./r/aws_ami.md)

- [aws_ami_copy](./r/aws_ami_copy.md)

- [aws_ami_from_instance](./r/aws_ami_from_instance.md)

- [aws_ami_launch_permission](./r/aws_ami_launch_permission.md)

- [aws_api_gateway_account](./r/aws_api_gateway_account.md)

- [aws_api_gateway_api_key](./r/aws_api_gateway_api_key.md)

- [aws_api_gateway_authorizer](./r/aws_api_gateway_authorizer.md)

- [aws_api_gateway_base_path_mapping](./r/aws_api_gateway_base_path_mapping.md)

- [aws_api_gateway_client_certificate](./r/aws_api_gateway_client_certificate.md)

- [aws_api_gateway_deployment](./r/aws_api_gateway_deployment.md)

- [aws_api_gateway_documentation_part](./r/aws_api_gateway_documentation_part.md)

- [aws_api_gateway_documentation_version](./r/aws_api_gateway_documentation_version.md)

- [aws_api_gateway_domain_name](./r/aws_api_gateway_domain_name.md)

- [aws_api_gateway_gateway_response](./r/aws_api_gateway_gateway_response.md)

- [aws_api_gateway_integration](./r/aws_api_gateway_integration.md)

- [aws_api_gateway_integration_response](./r/aws_api_gateway_integration_response.md)

- [aws_api_gateway_method](./r/aws_api_gateway_method.md)

- [aws_api_gateway_method_response](./r/aws_api_gateway_method_response.md)

- [aws_api_gateway_method_settings](./r/aws_api_gateway_method_settings.md)

- [aws_api_gateway_model](./r/aws_api_gateway_model.md)

- [aws_api_gateway_request_validator](./r/aws_api_gateway_request_validator.md)

- [aws_api_gateway_resource](./r/aws_api_gateway_resource.md)

- [aws_api_gateway_rest_api](./r/aws_api_gateway_rest_api.md)

- [aws_api_gateway_rest_api_policy](./r/aws_api_gateway_rest_api_policy.md)

- [aws_api_gateway_stage](./r/aws_api_gateway_stage.md)

- [aws_api_gateway_usage_plan](./r/aws_api_gateway_usage_plan.md)

- [aws_api_gateway_usage_plan_key](./r/aws_api_gateway_usage_plan_key.md)

- [aws_api_gateway_vpc_link](./r/aws_api_gateway_vpc_link.md)

- [aws_apigatewayv2_api](./r/aws_apigatewayv2_api.md)

- [aws_apigatewayv2_api_mapping](./r/aws_apigatewayv2_api_mapping.md)

- [aws_apigatewayv2_authorizer](./r/aws_apigatewayv2_authorizer.md)

- [aws_apigatewayv2_deployment](./r/aws_apigatewayv2_deployment.md)

- [aws_apigatewayv2_domain_name](./r/aws_apigatewayv2_domain_name.md)

- [aws_apigatewayv2_integration](./r/aws_apigatewayv2_integration.md)

- [aws_apigatewayv2_integration_response](./r/aws_apigatewayv2_integration_response.md)

- [aws_apigatewayv2_model](./r/aws_apigatewayv2_model.md)

- [aws_apigatewayv2_route](./r/aws_apigatewayv2_route.md)

- [aws_apigatewayv2_route_response](./r/aws_apigatewayv2_route_response.md)

- [aws_apigatewayv2_stage](./r/aws_apigatewayv2_stage.md)

- [aws_apigatewayv2_vpc_link](./r/aws_apigatewayv2_vpc_link.md)

- [aws_app_cookie_stickiness_policy](./r/aws_app_cookie_stickiness_policy.md)

- [aws_appautoscaling_policy](./r/aws_appautoscaling_policy.md)

- [aws_appautoscaling_scheduled_action](./r/aws_appautoscaling_scheduled_action.md)

- [aws_appautoscaling_target](./r/aws_appautoscaling_target.md)

- [aws_appmesh_gateway_route](./r/aws_appmesh_gateway_route.md)

- [aws_appmesh_mesh](./r/aws_appmesh_mesh.md)

- [aws_appmesh_route](./r/aws_appmesh_route.md)

- [aws_appmesh_virtual_gateway](./r/aws_appmesh_virtual_gateway.md)

- [aws_appmesh_virtual_node](./r/aws_appmesh_virtual_node.md)

- [aws_appmesh_virtual_router](./r/aws_appmesh_virtual_router.md)

- [aws_appmesh_virtual_service](./r/aws_appmesh_virtual_service.md)

- [aws_appsync_api_key](./r/aws_appsync_api_key.md)

- [aws_appsync_datasource](./r/aws_appsync_datasource.md)

- [aws_appsync_function](./r/aws_appsync_function.md)

- [aws_appsync_graphql_api](./r/aws_appsync_graphql_api.md)

- [aws_appsync_resolver](./r/aws_appsync_resolver.md)

- [aws_athena_database](./r/aws_athena_database.md)

- [aws_athena_named_query](./r/aws_athena_named_query.md)

- [aws_athena_workgroup](./r/aws_athena_workgroup.md)

- [aws_autoscaling_attachment](./r/aws_autoscaling_attachment.md)

- [aws_autoscaling_group](./r/aws_autoscaling_group.md)

- [aws_autoscaling_lifecycle_hook](./r/aws_autoscaling_lifecycle_hook.md)

- [aws_autoscaling_notification](./r/aws_autoscaling_notification.md)

- [aws_autoscaling_policy](./r/aws_autoscaling_policy.md)

- [aws_autoscaling_schedule](./r/aws_autoscaling_schedule.md)

- [aws_autoscalingplans_scaling_plan](./r/aws_autoscalingplans_scaling_plan.md)

- [aws_backup_global_settings](./r/aws_backup_global_settings.md)

- [aws_backup_plan](./r/aws_backup_plan.md)

- [aws_backup_region_settings](./r/aws_backup_region_settings.md)

- [aws_backup_selection](./r/aws_backup_selection.md)

- [aws_backup_vault](./r/aws_backup_vault.md)

- [aws_backup_vault_notifications](./r/aws_backup_vault_notifications.md)

- [aws_backup_vault_policy](./r/aws_backup_vault_policy.md)

- [aws_batch_compute_environment](./r/aws_batch_compute_environment.md)

- [aws_batch_job_definition](./r/aws_batch_job_definition.md)

- [aws_batch_job_queue](./r/aws_batch_job_queue.md)

- [aws_budgets_budget](./r/aws_budgets_budget.md)

- [aws_cloud9_environment_ec2](./r/aws_cloud9_environment_ec2.md)

- [aws_cloudformation_stack](./r/aws_cloudformation_stack.md)

- [aws_cloudformation_stack_set](./r/aws_cloudformation_stack_set.md)

- [aws_cloudformation_stack_set_instance](./r/aws_cloudformation_stack_set_instance.md)

- [aws_cloudfront_cache_policy](./r/aws_cloudfront_cache_policy.md)

- [aws_cloudfront_distribution](./r/aws_cloudfront_distribution.md)

- [aws_cloudfront_origin_access_identity](./r/aws_cloudfront_origin_access_identity.md)

- [aws_cloudfront_origin_request_policy](./r/aws_cloudfront_origin_request_policy.md)

- [aws_cloudfront_public_key](./r/aws_cloudfront_public_key.md)

- [aws_cloudfront_realtime_log_config](./r/aws_cloudfront_realtime_log_config.md)

- [aws_cloudhsm_v2_cluster](./r/aws_cloudhsm_v2_cluster.md)

- [aws_cloudhsm_v2_hsm](./r/aws_cloudhsm_v2_hsm.md)

- [aws_cloudtrail](./r/aws_cloudtrail.md)

- [aws_cloudwatch_composite_alarm](./r/aws_cloudwatch_composite_alarm.md)

- [aws_cloudwatch_dashboard](./r/aws_cloudwatch_dashboard.md)

- [aws_cloudwatch_event_archive](./r/aws_cloudwatch_event_archive.md)

- [aws_cloudwatch_event_bus](./r/aws_cloudwatch_event_bus.md)

- [aws_cloudwatch_event_permission](./r/aws_cloudwatch_event_permission.md)

- [aws_cloudwatch_event_rule](./r/aws_cloudwatch_event_rule.md)

- [aws_cloudwatch_event_target](./r/aws_cloudwatch_event_target.md)

- [aws_cloudwatch_log_destination](./r/aws_cloudwatch_log_destination.md)

- [aws_cloudwatch_log_destination_policy](./r/aws_cloudwatch_log_destination_policy.md)

- [aws_cloudwatch_log_group](./r/aws_cloudwatch_log_group.md)

- [aws_cloudwatch_log_metric_filter](./r/aws_cloudwatch_log_metric_filter.md)

- [aws_cloudwatch_log_resource_policy](./r/aws_cloudwatch_log_resource_policy.md)

- [aws_cloudwatch_log_stream](./r/aws_cloudwatch_log_stream.md)

- [aws_cloudwatch_log_subscription_filter](./r/aws_cloudwatch_log_subscription_filter.md)

- [aws_cloudwatch_metric_alarm](./r/aws_cloudwatch_metric_alarm.md)

- [aws_cloudwatch_query_definition](./r/aws_cloudwatch_query_definition.md)

- [aws_codeartifact_domain](./r/aws_codeartifact_domain.md)

- [aws_codeartifact_domain_permissions_policy](./r/aws_codeartifact_domain_permissions_policy.md)

- [aws_codeartifact_repository](./r/aws_codeartifact_repository.md)

- [aws_codeartifact_repository_permissions_policy](./r/aws_codeartifact_repository_permissions_policy.md)

- [aws_codebuild_project](./r/aws_codebuild_project.md)

- [aws_codebuild_report_group](./r/aws_codebuild_report_group.md)

- [aws_codebuild_source_credential](./r/aws_codebuild_source_credential.md)

- [aws_codebuild_webhook](./r/aws_codebuild_webhook.md)

- [aws_codecommit_repository](./r/aws_codecommit_repository.md)

- [aws_codecommit_trigger](./r/aws_codecommit_trigger.md)

- [aws_codedeploy_app](./r/aws_codedeploy_app.md)

- [aws_codedeploy_deployment_config](./r/aws_codedeploy_deployment_config.md)

- [aws_codedeploy_deployment_group](./r/aws_codedeploy_deployment_group.md)

- [aws_codepipeline](./r/aws_codepipeline.md)

- [aws_codepipeline_webhook](./r/aws_codepipeline_webhook.md)

- [aws_codestarconnections_connection](./r/aws_codestarconnections_connection.md)

- [aws_codestarnotifications_notification_rule](./r/aws_codestarnotifications_notification_rule.md)

- [aws_cognito_identity_pool](./r/aws_cognito_identity_pool.md)

- [aws_cognito_identity_pool_roles_attachment](./r/aws_cognito_identity_pool_roles_attachment.md)

- [aws_cognito_identity_provider](./r/aws_cognito_identity_provider.md)

- [aws_cognito_resource_server](./r/aws_cognito_resource_server.md)

- [aws_cognito_user_group](./r/aws_cognito_user_group.md)

- [aws_cognito_user_pool](./r/aws_cognito_user_pool.md)

- [aws_cognito_user_pool_client](./r/aws_cognito_user_pool_client.md)

- [aws_cognito_user_pool_domain](./r/aws_cognito_user_pool_domain.md)

- [aws_cognito_user_pool_ui_customization](./r/aws_cognito_user_pool_ui_customization.md)

- [aws_config_aggregate_authorization](./r/aws_config_aggregate_authorization.md)

- [aws_config_config_rule](./r/aws_config_config_rule.md)

- [aws_config_configuration_aggregator](./r/aws_config_configuration_aggregator.md)

- [aws_config_configuration_recorder](./r/aws_config_configuration_recorder.md)

- [aws_config_configuration_recorder_status](./r/aws_config_configuration_recorder_status.md)

- [aws_config_conformance_pack](./r/aws_config_conformance_pack.md)

- [aws_config_delivery_channel](./r/aws_config_delivery_channel.md)

- [aws_config_organization_custom_rule](./r/aws_config_organization_custom_rule.md)

- [aws_config_organization_managed_rule](./r/aws_config_organization_managed_rule.md)

- [aws_config_remediation_configuration](./r/aws_config_remediation_configuration.md)

- [aws_cur_report_definition](./r/aws_cur_report_definition.md)

- [aws_customer_gateway](./r/aws_customer_gateway.md)

- [aws_datapipeline_pipeline](./r/aws_datapipeline_pipeline.md)

- [aws_datasync_agent](./r/aws_datasync_agent.md)

- [aws_datasync_location_efs](./r/aws_datasync_location_efs.md)

- [aws_datasync_location_fsx_windows_file_system](./r/aws_datasync_location_fsx_windows_file_system.md)

- [aws_datasync_location_nfs](./r/aws_datasync_location_nfs.md)

- [aws_datasync_location_s3](./r/aws_datasync_location_s3.md)

- [aws_datasync_location_smb](./r/aws_datasync_location_smb.md)

- [aws_datasync_task](./r/aws_datasync_task.md)

- [aws_dax_cluster](./r/aws_dax_cluster.md)

- [aws_dax_parameter_group](./r/aws_dax_parameter_group.md)

- [aws_dax_subnet_group](./r/aws_dax_subnet_group.md)

- [aws_db_cluster_snapshot](./r/aws_db_cluster_snapshot.md)

- [aws_db_event_subscription](./r/aws_db_event_subscription.md)

- [aws_db_instance](./r/aws_db_instance.md)

- [aws_db_instance_role_association](./r/aws_db_instance_role_association.md)

- [aws_db_option_group](./r/aws_db_option_group.md)

- [aws_db_parameter_group](./r/aws_db_parameter_group.md)

- [aws_db_proxy](./r/aws_db_proxy.md)

- [aws_db_proxy_default_target_group](./r/aws_db_proxy_default_target_group.md)

- [aws_db_proxy_target](./r/aws_db_proxy_target.md)

- [aws_db_security_group](./r/aws_db_security_group.md)

- [aws_db_snapshot](./r/aws_db_snapshot.md)

- [aws_db_subnet_group](./r/aws_db_subnet_group.md)

- [aws_default_network_acl](./r/aws_default_network_acl.md)

- [aws_default_route_table](./r/aws_default_route_table.md)

- [aws_default_security_group](./r/aws_default_security_group.md)

- [aws_default_subnet](./r/aws_default_subnet.md)

- [aws_default_vpc](./r/aws_default_vpc.md)

- [aws_default_vpc_dhcp_options](./r/aws_default_vpc_dhcp_options.md)

- [aws_devicefarm_project](./r/aws_devicefarm_project.md)

- [aws_directory_service_conditional_forwarder](./r/aws_directory_service_conditional_forwarder.md)

- [aws_directory_service_directory](./r/aws_directory_service_directory.md)

- [aws_directory_service_log_subscription](./r/aws_directory_service_log_subscription.md)

- [aws_dlm_lifecycle_policy](./r/aws_dlm_lifecycle_policy.md)

- [aws_dms_certificate](./r/aws_dms_certificate.md)

- [aws_dms_endpoint](./r/aws_dms_endpoint.md)

- [aws_dms_event_subscription](./r/aws_dms_event_subscription.md)

- [aws_dms_replication_instance](./r/aws_dms_replication_instance.md)

- [aws_dms_replication_subnet_group](./r/aws_dms_replication_subnet_group.md)

- [aws_dms_replication_task](./r/aws_dms_replication_task.md)

- [aws_docdb_cluster](./r/aws_docdb_cluster.md)

- [aws_docdb_cluster_instance](./r/aws_docdb_cluster_instance.md)

- [aws_docdb_cluster_parameter_group](./r/aws_docdb_cluster_parameter_group.md)

- [aws_docdb_cluster_snapshot](./r/aws_docdb_cluster_snapshot.md)

- [aws_docdb_subnet_group](./r/aws_docdb_subnet_group.md)

- [aws_dx_bgp_peer](./r/aws_dx_bgp_peer.md)

- [aws_dx_connection](./r/aws_dx_connection.md)

- [aws_dx_connection_association](./r/aws_dx_connection_association.md)

- [aws_dx_gateway](./r/aws_dx_gateway.md)

- [aws_dx_gateway_association](./r/aws_dx_gateway_association.md)

- [aws_dx_gateway_association_proposal](./r/aws_dx_gateway_association_proposal.md)

- [aws_dx_hosted_private_virtual_interface](./r/aws_dx_hosted_private_virtual_interface.md)

- [aws_dx_hosted_private_virtual_interface_accepter](./r/aws_dx_hosted_private_virtual_interface_accepter.md)

- [aws_dx_hosted_public_virtual_interface](./r/aws_dx_hosted_public_virtual_interface.md)

- [aws_dx_hosted_public_virtual_interface_accepter](./r/aws_dx_hosted_public_virtual_interface_accepter.md)

- [aws_dx_hosted_transit_virtual_interface](./r/aws_dx_hosted_transit_virtual_interface.md)

- [aws_dx_hosted_transit_virtual_interface_accepter](./r/aws_dx_hosted_transit_virtual_interface_accepter.md)

- [aws_dx_lag](./r/aws_dx_lag.md)

- [aws_dx_private_virtual_interface](./r/aws_dx_private_virtual_interface.md)

- [aws_dx_public_virtual_interface](./r/aws_dx_public_virtual_interface.md)

- [aws_dx_transit_virtual_interface](./r/aws_dx_transit_virtual_interface.md)

- [aws_dynamodb_global_table](./r/aws_dynamodb_global_table.md)

- [aws_dynamodb_table](./r/aws_dynamodb_table.md)

- [aws_dynamodb_table_item](./r/aws_dynamodb_table_item.md)

- [aws_ebs_default_kms_key](./r/aws_ebs_default_kms_key.md)

- [aws_ebs_encryption_by_default](./r/aws_ebs_encryption_by_default.md)

- [aws_ebs_snapshot](./r/aws_ebs_snapshot.md)

- [aws_ebs_snapshot_copy](./r/aws_ebs_snapshot_copy.md)

- [aws_ebs_volume](./r/aws_ebs_volume.md)

- [aws_ec2_availability_zone_group](./r/aws_ec2_availability_zone_group.md)

- [aws_ec2_capacity_reservation](./r/aws_ec2_capacity_reservation.md)

- [aws_ec2_carrier_gateway](./r/aws_ec2_carrier_gateway.md)

- [aws_ec2_client_vpn_authorization_rule](./r/aws_ec2_client_vpn_authorization_rule.md)

- [aws_ec2_client_vpn_endpoint](./r/aws_ec2_client_vpn_endpoint.md)

- [aws_ec2_client_vpn_network_association](./r/aws_ec2_client_vpn_network_association.md)

- [aws_ec2_client_vpn_route](./r/aws_ec2_client_vpn_route.md)

- [aws_ec2_fleet](./r/aws_ec2_fleet.md)

- [aws_ec2_local_gateway_route](./r/aws_ec2_local_gateway_route.md)

- [aws_ec2_local_gateway_route_table_vpc_association](./r/aws_ec2_local_gateway_route_table_vpc_association.md)

- [aws_ec2_managed_prefix_list](./r/aws_ec2_managed_prefix_list.md)

- [aws_ec2_tag](./r/aws_ec2_tag.md)

- [aws_ec2_traffic_mirror_filter](./r/aws_ec2_traffic_mirror_filter.md)

- [aws_ec2_traffic_mirror_filter_rule](./r/aws_ec2_traffic_mirror_filter_rule.md)

- [aws_ec2_traffic_mirror_session](./r/aws_ec2_traffic_mirror_session.md)

- [aws_ec2_traffic_mirror_target](./r/aws_ec2_traffic_mirror_target.md)

- [aws_ec2_transit_gateway](./r/aws_ec2_transit_gateway.md)

- [aws_ec2_transit_gateway_peering_attachment](./r/aws_ec2_transit_gateway_peering_attachment.md)

- [aws_ec2_transit_gateway_peering_attachment_accepter](./r/aws_ec2_transit_gateway_peering_attachment_accepter.md)

- [aws_ec2_transit_gateway_prefix_list_reference](./r/aws_ec2_transit_gateway_prefix_list_reference.md)

- [aws_ec2_transit_gateway_route](./r/aws_ec2_transit_gateway_route.md)

- [aws_ec2_transit_gateway_route_table](./r/aws_ec2_transit_gateway_route_table.md)

- [aws_ec2_transit_gateway_route_table_association](./r/aws_ec2_transit_gateway_route_table_association.md)

- [aws_ec2_transit_gateway_route_table_propagation](./r/aws_ec2_transit_gateway_route_table_propagation.md)

- [aws_ec2_transit_gateway_vpc_attachment](./r/aws_ec2_transit_gateway_vpc_attachment.md)

- [aws_ec2_transit_gateway_vpc_attachment_accepter](./r/aws_ec2_transit_gateway_vpc_attachment_accepter.md)

- [aws_ecr_lifecycle_policy](./r/aws_ecr_lifecycle_policy.md)

- [aws_ecr_repository](./r/aws_ecr_repository.md)

- [aws_ecr_repository_policy](./r/aws_ecr_repository_policy.md)

- [aws_ecrpublic_repository](./r/aws_ecrpublic_repository.md)

- [aws_ecs_capacity_provider](./r/aws_ecs_capacity_provider.md)

- [aws_ecs_cluster](./r/aws_ecs_cluster.md)

- [aws_ecs_service](./r/aws_ecs_service.md)

- [aws_ecs_task_definition](./r/aws_ecs_task_definition.md)

- [aws_efs_access_point](./r/aws_efs_access_point.md)

- [aws_efs_file_system](./r/aws_efs_file_system.md)

- [aws_efs_file_system_policy](./r/aws_efs_file_system_policy.md)

- [aws_efs_mount_target](./r/aws_efs_mount_target.md)

- [aws_egress_only_internet_gateway](./r/aws_egress_only_internet_gateway.md)

- [aws_eip](./r/aws_eip.md)

- [aws_eip_association](./r/aws_eip_association.md)

- [aws_eks_cluster](./r/aws_eks_cluster.md)

- [aws_eks_fargate_profile](./r/aws_eks_fargate_profile.md)

- [aws_eks_node_group](./r/aws_eks_node_group.md)

- [aws_elastic_beanstalk_application](./r/aws_elastic_beanstalk_application.md)

- [aws_elastic_beanstalk_application_version](./r/aws_elastic_beanstalk_application_version.md)

- [aws_elastic_beanstalk_configuration_template](./r/aws_elastic_beanstalk_configuration_template.md)

- [aws_elastic_beanstalk_environment](./r/aws_elastic_beanstalk_environment.md)

- [aws_elasticache_cluster](./r/aws_elasticache_cluster.md)

- [aws_elasticache_global_replication_group](./r/aws_elasticache_global_replication_group.md)

- [aws_elasticache_parameter_group](./r/aws_elasticache_parameter_group.md)

- [aws_elasticache_replication_group](./r/aws_elasticache_replication_group.md)

- [aws_elasticache_security_group](./r/aws_elasticache_security_group.md)

- [aws_elasticache_subnet_group](./r/aws_elasticache_subnet_group.md)

- [aws_elasticsearch_domain](./r/aws_elasticsearch_domain.md)

- [aws_elasticsearch_domain_policy](./r/aws_elasticsearch_domain_policy.md)

- [aws_elastictranscoder_pipeline](./r/aws_elastictranscoder_pipeline.md)

- [aws_elastictranscoder_preset](./r/aws_elastictranscoder_preset.md)

- [aws_elb](./r/aws_elb.md)

- [aws_elb_attachment](./r/aws_elb_attachment.md)

- [aws_emr_cluster](./r/aws_emr_cluster.md)

- [aws_emr_instance_fleet](./r/aws_emr_instance_fleet.md)

- [aws_emr_instance_group](./r/aws_emr_instance_group.md)

- [aws_emr_managed_scaling_policy](./r/aws_emr_managed_scaling_policy.md)

- [aws_emr_security_configuration](./r/aws_emr_security_configuration.md)

- [aws_flow_log](./r/aws_flow_log.md)

- [aws_fms_admin_account](./r/aws_fms_admin_account.md)

- [aws_fms_policy](./r/aws_fms_policy.md)

- [aws_fsx_lustre_file_system](./r/aws_fsx_lustre_file_system.md)

- [aws_fsx_windows_file_system](./r/aws_fsx_windows_file_system.md)

- [aws_gamelift_alias](./r/aws_gamelift_alias.md)

- [aws_gamelift_build](./r/aws_gamelift_build.md)

- [aws_gamelift_fleet](./r/aws_gamelift_fleet.md)

- [aws_gamelift_game_session_queue](./r/aws_gamelift_game_session_queue.md)

- [aws_glacier_vault](./r/aws_glacier_vault.md)

- [aws_glacier_vault_lock](./r/aws_glacier_vault_lock.md)

- [aws_globalaccelerator_accelerator](./r/aws_globalaccelerator_accelerator.md)

- [aws_globalaccelerator_endpoint_group](./r/aws_globalaccelerator_endpoint_group.md)

- [aws_globalaccelerator_listener](./r/aws_globalaccelerator_listener.md)

- [aws_glue_catalog_database](./r/aws_glue_catalog_database.md)

- [aws_glue_catalog_table](./r/aws_glue_catalog_table.md)

- [aws_glue_classifier](./r/aws_glue_classifier.md)

- [aws_glue_connection](./r/aws_glue_connection.md)

- [aws_glue_crawler](./r/aws_glue_crawler.md)

- [aws_glue_data_catalog_encryption_settings](./r/aws_glue_data_catalog_encryption_settings.md)

- [aws_glue_dev_endpoint](./r/aws_glue_dev_endpoint.md)

- [aws_glue_job](./r/aws_glue_job.md)

- [aws_glue_ml_transform](./r/aws_glue_ml_transform.md)

- [aws_glue_partition](./r/aws_glue_partition.md)

- [aws_glue_registry](./r/aws_glue_registry.md)

- [aws_glue_resource_policy](./r/aws_glue_resource_policy.md)

- [aws_glue_schema](./r/aws_glue_schema.md)

- [aws_glue_security_configuration](./r/aws_glue_security_configuration.md)

- [aws_glue_trigger](./r/aws_glue_trigger.md)

- [aws_glue_user_defined_function](./r/aws_glue_user_defined_function.md)

- [aws_glue_workflow](./r/aws_glue_workflow.md)

- [aws_guardduty_detector](./r/aws_guardduty_detector.md)

- [aws_guardduty_filter](./r/aws_guardduty_filter.md)

- [aws_guardduty_invite_accepter](./r/aws_guardduty_invite_accepter.md)

- [aws_guardduty_ipset](./r/aws_guardduty_ipset.md)

- [aws_guardduty_member](./r/aws_guardduty_member.md)

- [aws_guardduty_organization_admin_account](./r/aws_guardduty_organization_admin_account.md)

- [aws_guardduty_organization_configuration](./r/aws_guardduty_organization_configuration.md)

- [aws_guardduty_publishing_destination](./r/aws_guardduty_publishing_destination.md)

- [aws_guardduty_threatintelset](./r/aws_guardduty_threatintelset.md)

- [aws_iam_access_key](./r/aws_iam_access_key.md)

- [aws_iam_account_alias](./r/aws_iam_account_alias.md)

- [aws_iam_account_password_policy](./r/aws_iam_account_password_policy.md)

- [aws_iam_group](./r/aws_iam_group.md)

- [aws_iam_group_membership](./r/aws_iam_group_membership.md)

- [aws_iam_group_policy](./r/aws_iam_group_policy.md)

- [aws_iam_group_policy_attachment](./r/aws_iam_group_policy_attachment.md)

- [aws_iam_instance_profile](./r/aws_iam_instance_profile.md)

- [aws_iam_openid_connect_provider](./r/aws_iam_openid_connect_provider.md)

- [aws_iam_policy](./r/aws_iam_policy.md)

- [aws_iam_policy_attachment](./r/aws_iam_policy_attachment.md)

- [aws_iam_role](./r/aws_iam_role.md)

- [aws_iam_role_policy](./r/aws_iam_role_policy.md)

- [aws_iam_role_policy_attachment](./r/aws_iam_role_policy_attachment.md)

- [aws_iam_saml_provider](./r/aws_iam_saml_provider.md)

- [aws_iam_server_certificate](./r/aws_iam_server_certificate.md)

- [aws_iam_service_linked_role](./r/aws_iam_service_linked_role.md)

- [aws_iam_user](./r/aws_iam_user.md)

- [aws_iam_user_group_membership](./r/aws_iam_user_group_membership.md)

- [aws_iam_user_login_profile](./r/aws_iam_user_login_profile.md)

- [aws_iam_user_policy](./r/aws_iam_user_policy.md)

- [aws_iam_user_policy_attachment](./r/aws_iam_user_policy_attachment.md)

- [aws_iam_user_ssh_key](./r/aws_iam_user_ssh_key.md)

- [aws_imagebuilder_component](./r/aws_imagebuilder_component.md)

- [aws_imagebuilder_distribution_configuration](./r/aws_imagebuilder_distribution_configuration.md)

- [aws_imagebuilder_image](./r/aws_imagebuilder_image.md)

- [aws_imagebuilder_image_pipeline](./r/aws_imagebuilder_image_pipeline.md)

- [aws_imagebuilder_image_recipe](./r/aws_imagebuilder_image_recipe.md)

- [aws_imagebuilder_infrastructure_configuration](./r/aws_imagebuilder_infrastructure_configuration.md)

- [aws_inspector_assessment_target](./r/aws_inspector_assessment_target.md)

- [aws_inspector_assessment_template](./r/aws_inspector_assessment_template.md)

- [aws_inspector_resource_group](./r/aws_inspector_resource_group.md)

- [aws_instance](./r/aws_instance.md)

- [aws_internet_gateway](./r/aws_internet_gateway.md)

- [aws_iot_certificate](./r/aws_iot_certificate.md)

- [aws_iot_policy](./r/aws_iot_policy.md)

- [aws_iot_policy_attachment](./r/aws_iot_policy_attachment.md)

- [aws_iot_role_alias](./r/aws_iot_role_alias.md)

- [aws_iot_thing](./r/aws_iot_thing.md)

- [aws_iot_thing_principal_attachment](./r/aws_iot_thing_principal_attachment.md)

- [aws_iot_thing_type](./r/aws_iot_thing_type.md)

- [aws_iot_topic_rule](./r/aws_iot_topic_rule.md)

- [aws_key_pair](./r/aws_key_pair.md)

- [aws_kinesis_analytics_application](./r/aws_kinesis_analytics_application.md)

- [aws_kinesis_firehose_delivery_stream](./r/aws_kinesis_firehose_delivery_stream.md)

- [aws_kinesis_stream](./r/aws_kinesis_stream.md)

- [aws_kinesis_stream_consumer](./r/aws_kinesis_stream_consumer.md)

- [aws_kinesis_video_stream](./r/aws_kinesis_video_stream.md)

- [aws_kinesisanalyticsv2_application](./r/aws_kinesisanalyticsv2_application.md)

- [aws_kms_alias](./r/aws_kms_alias.md)

- [aws_kms_ciphertext](./r/aws_kms_ciphertext.md)

- [aws_kms_external_key](./r/aws_kms_external_key.md)

- [aws_kms_grant](./r/aws_kms_grant.md)

- [aws_kms_key](./r/aws_kms_key.md)

- [aws_lakeformation_data_lake_settings](./r/aws_lakeformation_data_lake_settings.md)

- [aws_lakeformation_permissions](./r/aws_lakeformation_permissions.md)

- [aws_lakeformation_resource](./r/aws_lakeformation_resource.md)

- [aws_lambda_alias](./r/aws_lambda_alias.md)

- [aws_lambda_code_signing_config](./r/aws_lambda_code_signing_config.md)

- [aws_lambda_event_source_mapping](./r/aws_lambda_event_source_mapping.md)

- [aws_lambda_function](./r/aws_lambda_function.md)

- [aws_lambda_function_event_invoke_config](./r/aws_lambda_function_event_invoke_config.md)

- [aws_lambda_layer_version](./r/aws_lambda_layer_version.md)

- [aws_lambda_permission](./r/aws_lambda_permission.md)

- [aws_lambda_provisioned_concurrency_config](./r/aws_lambda_provisioned_concurrency_config.md)

- [aws_launch_configuration](./r/aws_launch_configuration.md)

- [aws_launch_template](./r/aws_launch_template.md)

- [aws_lb](./r/aws_lb.md)

- [aws_lb_cookie_stickiness_policy](./r/aws_lb_cookie_stickiness_policy.md)

- [aws_lb_listener](./r/aws_lb_listener.md)

- [aws_lb_listener_certificate](./r/aws_lb_listener_certificate.md)

- [aws_lb_listener_rule](./r/aws_lb_listener_rule.md)

- [aws_lb_ssl_negotiation_policy](./r/aws_lb_ssl_negotiation_policy.md)

- [aws_lb_target_group](./r/aws_lb_target_group.md)

- [aws_lb_target_group_attachment](./r/aws_lb_target_group_attachment.md)

- [aws_lex_bot](./r/aws_lex_bot.md)

- [aws_lex_bot_alias](./r/aws_lex_bot_alias.md)

- [aws_lex_intent](./r/aws_lex_intent.md)

- [aws_lex_slot_type](./r/aws_lex_slot_type.md)

- [aws_licensemanager_association](./r/aws_licensemanager_association.md)

- [aws_licensemanager_license_configuration](./r/aws_licensemanager_license_configuration.md)

- [aws_lightsail_domain](./r/aws_lightsail_domain.md)

- [aws_lightsail_instance](./r/aws_lightsail_instance.md)

- [aws_lightsail_instance_public_ports](./r/aws_lightsail_instance_public_ports.md)

- [aws_lightsail_key_pair](./r/aws_lightsail_key_pair.md)

- [aws_lightsail_static_ip](./r/aws_lightsail_static_ip.md)

- [aws_lightsail_static_ip_attachment](./r/aws_lightsail_static_ip_attachment.md)

- [aws_load_balancer_backend_server_policy](./r/aws_load_balancer_backend_server_policy.md)

- [aws_load_balancer_listener_policy](./r/aws_load_balancer_listener_policy.md)

- [aws_load_balancer_policy](./r/aws_load_balancer_policy.md)

- [aws_macie_member_account_association](./r/aws_macie_member_account_association.md)

- [aws_macie_s3_bucket_association](./r/aws_macie_s3_bucket_association.md)

- [aws_main_route_table_association](./r/aws_main_route_table_association.md)

- [aws_media_convert_queue](./r/aws_media_convert_queue.md)

- [aws_media_package_channel](./r/aws_media_package_channel.md)

- [aws_media_store_container](./r/aws_media_store_container.md)

- [aws_media_store_container_policy](./r/aws_media_store_container_policy.md)

- [aws_mq_broker](./r/aws_mq_broker.md)

- [aws_mq_configuration](./r/aws_mq_configuration.md)

- [aws_msk_cluster](./r/aws_msk_cluster.md)

- [aws_msk_configuration](./r/aws_msk_configuration.md)

- [aws_msk_scram_secret_association](./r/aws_msk_scram_secret_association.md)

- [aws_nat_gateway](./r/aws_nat_gateway.md)

- [aws_neptune_cluster](./r/aws_neptune_cluster.md)

- [aws_neptune_cluster_instance](./r/aws_neptune_cluster_instance.md)

- [aws_neptune_cluster_parameter_group](./r/aws_neptune_cluster_parameter_group.md)

- [aws_neptune_cluster_snapshot](./r/aws_neptune_cluster_snapshot.md)

- [aws_neptune_event_subscription](./r/aws_neptune_event_subscription.md)

- [aws_neptune_parameter_group](./r/aws_neptune_parameter_group.md)

- [aws_neptune_subnet_group](./r/aws_neptune_subnet_group.md)

- [aws_network_acl](./r/aws_network_acl.md)

- [aws_network_acl_rule](./r/aws_network_acl_rule.md)

- [aws_network_interface](./r/aws_network_interface.md)

- [aws_network_interface_attachment](./r/aws_network_interface_attachment.md)

- [aws_network_interface_sg_attachment](./r/aws_network_interface_sg_attachment.md)

- [aws_networkfirewall_firewall](./r/aws_networkfirewall_firewall.md)

- [aws_networkfirewall_firewall_policy](./r/aws_networkfirewall_firewall_policy.md)

- [aws_networkfirewall_logging_configuration](./r/aws_networkfirewall_logging_configuration.md)

- [aws_networkfirewall_resource_policy](./r/aws_networkfirewall_resource_policy.md)

- [aws_networkfirewall_rule_group](./r/aws_networkfirewall_rule_group.md)

- [aws_opsworks_application](./r/aws_opsworks_application.md)

- [aws_opsworks_custom_layer](./r/aws_opsworks_custom_layer.md)

- [aws_opsworks_ganglia_layer](./r/aws_opsworks_ganglia_layer.md)

- [aws_opsworks_haproxy_layer](./r/aws_opsworks_haproxy_layer.md)

- [aws_opsworks_instance](./r/aws_opsworks_instance.md)

- [aws_opsworks_java_app_layer](./r/aws_opsworks_java_app_layer.md)

- [aws_opsworks_memcached_layer](./r/aws_opsworks_memcached_layer.md)

- [aws_opsworks_mysql_layer](./r/aws_opsworks_mysql_layer.md)

- [aws_opsworks_nodejs_app_layer](./r/aws_opsworks_nodejs_app_layer.md)

- [aws_opsworks_permission](./r/aws_opsworks_permission.md)

- [aws_opsworks_php_app_layer](./r/aws_opsworks_php_app_layer.md)

- [aws_opsworks_rails_app_layer](./r/aws_opsworks_rails_app_layer.md)

- [aws_opsworks_rds_db_instance](./r/aws_opsworks_rds_db_instance.md)

- [aws_opsworks_stack](./r/aws_opsworks_stack.md)

- [aws_opsworks_static_web_layer](./r/aws_opsworks_static_web_layer.md)

- [aws_opsworks_user_profile](./r/aws_opsworks_user_profile.md)

- [aws_organizations_account](./r/aws_organizations_account.md)

- [aws_organizations_organization](./r/aws_organizations_organization.md)

- [aws_organizations_organizational_unit](./r/aws_organizations_organizational_unit.md)

- [aws_organizations_policy](./r/aws_organizations_policy.md)

- [aws_organizations_policy_attachment](./r/aws_organizations_policy_attachment.md)

- [aws_pinpoint_adm_channel](./r/aws_pinpoint_adm_channel.md)

- [aws_pinpoint_apns_channel](./r/aws_pinpoint_apns_channel.md)

- [aws_pinpoint_apns_sandbox_channel](./r/aws_pinpoint_apns_sandbox_channel.md)

- [aws_pinpoint_apns_voip_channel](./r/aws_pinpoint_apns_voip_channel.md)

- [aws_pinpoint_apns_voip_sandbox_channel](./r/aws_pinpoint_apns_voip_sandbox_channel.md)

- [aws_pinpoint_app](./r/aws_pinpoint_app.md)

- [aws_pinpoint_baidu_channel](./r/aws_pinpoint_baidu_channel.md)

- [aws_pinpoint_email_channel](./r/aws_pinpoint_email_channel.md)

- [aws_pinpoint_event_stream](./r/aws_pinpoint_event_stream.md)

- [aws_pinpoint_gcm_channel](./r/aws_pinpoint_gcm_channel.md)

- [aws_pinpoint_sms_channel](./r/aws_pinpoint_sms_channel.md)

- [aws_placement_group](./r/aws_placement_group.md)

- [aws_prometheus_workspace](./r/aws_prometheus_workspace.md)

- [aws_proxy_protocol_policy](./r/aws_proxy_protocol_policy.md)

- [aws_qldb_ledger](./r/aws_qldb_ledger.md)

- [aws_quicksight_group](./r/aws_quicksight_group.md)

- [aws_quicksight_user](./r/aws_quicksight_user.md)

- [aws_ram_principal_association](./r/aws_ram_principal_association.md)

- [aws_ram_resource_association](./r/aws_ram_resource_association.md)

- [aws_ram_resource_share](./r/aws_ram_resource_share.md)

- [aws_ram_resource_share_accepter](./r/aws_ram_resource_share_accepter.md)

- [aws_rds_cluster](./r/aws_rds_cluster.md)

- [aws_rds_cluster_endpoint](./r/aws_rds_cluster_endpoint.md)

- [aws_rds_cluster_instance](./r/aws_rds_cluster_instance.md)

- [aws_rds_cluster_parameter_group](./r/aws_rds_cluster_parameter_group.md)

- [aws_rds_global_cluster](./r/aws_rds_global_cluster.md)

- [aws_redshift_cluster](./r/aws_redshift_cluster.md)

- [aws_redshift_event_subscription](./r/aws_redshift_event_subscription.md)

- [aws_redshift_parameter_group](./r/aws_redshift_parameter_group.md)

- [aws_redshift_security_group](./r/aws_redshift_security_group.md)

- [aws_redshift_snapshot_copy_grant](./r/aws_redshift_snapshot_copy_grant.md)

- [aws_redshift_snapshot_schedule](./r/aws_redshift_snapshot_schedule.md)

- [aws_redshift_snapshot_schedule_association](./r/aws_redshift_snapshot_schedule_association.md)

- [aws_redshift_subnet_group](./r/aws_redshift_subnet_group.md)

- [aws_resourcegroups_group](./r/aws_resourcegroups_group.md)

- [aws_route](./r/aws_route.md)

- [aws_route53_delegation_set](./r/aws_route53_delegation_set.md)

- [aws_route53_health_check](./r/aws_route53_health_check.md)

- [aws_route53_hosted_zone_dnssec](./r/aws_route53_hosted_zone_dnssec.md)

- [aws_route53_key_signing_key](./r/aws_route53_key_signing_key.md)

- [aws_route53_query_log](./r/aws_route53_query_log.md)

- [aws_route53_record](./r/aws_route53_record.md)

- [aws_route53_resolver_dnssec_config](./r/aws_route53_resolver_dnssec_config.md)

- [aws_route53_resolver_endpoint](./r/aws_route53_resolver_endpoint.md)

- [aws_route53_resolver_query_log_config](./r/aws_route53_resolver_query_log_config.md)

- [aws_route53_resolver_query_log_config_association](./r/aws_route53_resolver_query_log_config_association.md)

- [aws_route53_resolver_rule](./r/aws_route53_resolver_rule.md)

- [aws_route53_resolver_rule_association](./r/aws_route53_resolver_rule_association.md)

- [aws_route53_vpc_association_authorization](./r/aws_route53_vpc_association_authorization.md)

- [aws_route53_zone](./r/aws_route53_zone.md)

- [aws_route53_zone_association](./r/aws_route53_zone_association.md)

- [aws_route_table](./r/aws_route_table.md)

- [aws_route_table_association](./r/aws_route_table_association.md)

- [aws_s3_access_point](./r/aws_s3_access_point.md)

- [aws_s3_account_public_access_block](./r/aws_s3_account_public_access_block.md)

- [aws_s3_bucket](./r/aws_s3_bucket.md)

- [aws_s3_bucket_analytics_configuration](./r/aws_s3_bucket_analytics_configuration.md)

- [aws_s3_bucket_inventory](./r/aws_s3_bucket_inventory.md)

- [aws_s3_bucket_metric](./r/aws_s3_bucket_metric.md)

- [aws_s3_bucket_notification](./r/aws_s3_bucket_notification.md)

- [aws_s3_bucket_object](./r/aws_s3_bucket_object.md)

- [aws_s3_bucket_ownership_controls](./r/aws_s3_bucket_ownership_controls.md)

- [aws_s3_bucket_policy](./r/aws_s3_bucket_policy.md)

- [aws_s3_bucket_public_access_block](./r/aws_s3_bucket_public_access_block.md)

- [aws_s3_object_copy](./r/aws_s3_object_copy.md)

- [aws_s3control_bucket](./r/aws_s3control_bucket.md)

- [aws_s3control_bucket_lifecycle_configuration](./r/aws_s3control_bucket_lifecycle_configuration.md)

- [aws_s3control_bucket_policy](./r/aws_s3control_bucket_policy.md)

- [aws_s3outposts_endpoint](./r/aws_s3outposts_endpoint.md)

- [aws_sagemaker_app](./r/aws_sagemaker_app.md)

- [aws_sagemaker_app_image_config](./r/aws_sagemaker_app_image_config.md)

- [aws_sagemaker_code_repository](./r/aws_sagemaker_code_repository.md)

- [aws_sagemaker_domain](./r/aws_sagemaker_domain.md)

- [aws_sagemaker_endpoint](./r/aws_sagemaker_endpoint.md)

- [aws_sagemaker_endpoint_configuration](./r/aws_sagemaker_endpoint_configuration.md)

- [aws_sagemaker_feature_group](./r/aws_sagemaker_feature_group.md)

- [aws_sagemaker_image](./r/aws_sagemaker_image.md)

- [aws_sagemaker_image_version](./r/aws_sagemaker_image_version.md)

- [aws_sagemaker_model](./r/aws_sagemaker_model.md)

- [aws_sagemaker_model_package_group](./r/aws_sagemaker_model_package_group.md)

- [aws_sagemaker_notebook_instance](./r/aws_sagemaker_notebook_instance.md)

- [aws_sagemaker_notebook_instance_lifecycle_configuration](./r/aws_sagemaker_notebook_instance_lifecycle_configuration.md)

- [aws_sagemaker_user_profile](./r/aws_sagemaker_user_profile.md)

- [aws_secretsmanager_secret](./r/aws_secretsmanager_secret.md)

- [aws_secretsmanager_secret_policy](./r/aws_secretsmanager_secret_policy.md)

- [aws_secretsmanager_secret_rotation](./r/aws_secretsmanager_secret_rotation.md)

- [aws_secretsmanager_secret_version](./r/aws_secretsmanager_secret_version.md)

- [aws_security_group](./r/aws_security_group.md)

- [aws_security_group_rule](./r/aws_security_group_rule.md)

- [aws_securityhub_account](./r/aws_securityhub_account.md)

- [aws_securityhub_action_target](./r/aws_securityhub_action_target.md)

- [aws_securityhub_invite_accepter](./r/aws_securityhub_invite_accepter.md)

- [aws_securityhub_member](./r/aws_securityhub_member.md)

- [aws_securityhub_organization_admin_account](./r/aws_securityhub_organization_admin_account.md)

- [aws_securityhub_product_subscription](./r/aws_securityhub_product_subscription.md)

- [aws_securityhub_standards_subscription](./r/aws_securityhub_standards_subscription.md)

- [aws_serverlessapplicationrepository_cloudformation_stack](./r/aws_serverlessapplicationrepository_cloudformation_stack.md)

- [aws_service_discovery_http_namespace](./r/aws_service_discovery_http_namespace.md)

- [aws_service_discovery_private_dns_namespace](./r/aws_service_discovery_private_dns_namespace.md)

- [aws_service_discovery_public_dns_namespace](./r/aws_service_discovery_public_dns_namespace.md)

- [aws_service_discovery_service](./r/aws_service_discovery_service.md)

- [aws_servicecatalog_portfolio](./r/aws_servicecatalog_portfolio.md)

- [aws_servicequotas_service_quota](./r/aws_servicequotas_service_quota.md)

- [aws_ses_active_receipt_rule_set](./r/aws_ses_active_receipt_rule_set.md)

- [aws_ses_configuration_set](./r/aws_ses_configuration_set.md)

- [aws_ses_domain_dkim](./r/aws_ses_domain_dkim.md)

- [aws_ses_domain_identity](./r/aws_ses_domain_identity.md)

- [aws_ses_domain_identity_verification](./r/aws_ses_domain_identity_verification.md)

- [aws_ses_domain_mail_from](./r/aws_ses_domain_mail_from.md)

- [aws_ses_email_identity](./r/aws_ses_email_identity.md)

- [aws_ses_event_destination](./r/aws_ses_event_destination.md)

- [aws_ses_identity_notification_topic](./r/aws_ses_identity_notification_topic.md)

- [aws_ses_identity_policy](./r/aws_ses_identity_policy.md)

- [aws_ses_receipt_filter](./r/aws_ses_receipt_filter.md)

- [aws_ses_receipt_rule](./r/aws_ses_receipt_rule.md)

- [aws_ses_receipt_rule_set](./r/aws_ses_receipt_rule_set.md)

- [aws_ses_template](./r/aws_ses_template.md)

- [aws_sfn_activity](./r/aws_sfn_activity.md)

- [aws_sfn_state_machine](./r/aws_sfn_state_machine.md)

- [aws_shield_protection](./r/aws_shield_protection.md)

- [aws_signer_signing_job](./r/aws_signer_signing_job.md)

- [aws_signer_signing_profile](./r/aws_signer_signing_profile.md)

- [aws_signer_signing_profile_permission](./r/aws_signer_signing_profile_permission.md)

- [aws_simpledb_domain](./r/aws_simpledb_domain.md)

- [aws_snapshot_create_volume_permission](./r/aws_snapshot_create_volume_permission.md)

- [aws_sns_platform_application](./r/aws_sns_platform_application.md)

- [aws_sns_sms_preferences](./r/aws_sns_sms_preferences.md)

- [aws_sns_topic](./r/aws_sns_topic.md)

- [aws_sns_topic_policy](./r/aws_sns_topic_policy.md)

- [aws_sns_topic_subscription](./r/aws_sns_topic_subscription.md)

- [aws_spot_datafeed_subscription](./r/aws_spot_datafeed_subscription.md)

- [aws_spot_fleet_request](./r/aws_spot_fleet_request.md)

- [aws_spot_instance_request](./r/aws_spot_instance_request.md)

- [aws_sqs_queue](./r/aws_sqs_queue.md)

- [aws_sqs_queue_policy](./r/aws_sqs_queue_policy.md)

- [aws_ssm_activation](./r/aws_ssm_activation.md)

- [aws_ssm_association](./r/aws_ssm_association.md)

- [aws_ssm_document](./r/aws_ssm_document.md)

- [aws_ssm_maintenance_window](./r/aws_ssm_maintenance_window.md)

- [aws_ssm_maintenance_window_target](./r/aws_ssm_maintenance_window_target.md)

- [aws_ssm_maintenance_window_task](./r/aws_ssm_maintenance_window_task.md)

- [aws_ssm_parameter](./r/aws_ssm_parameter.md)

- [aws_ssm_patch_baseline](./r/aws_ssm_patch_baseline.md)

- [aws_ssm_patch_group](./r/aws_ssm_patch_group.md)

- [aws_ssm_resource_data_sync](./r/aws_ssm_resource_data_sync.md)

- [aws_ssoadmin_account_assignment](./r/aws_ssoadmin_account_assignment.md)

- [aws_ssoadmin_managed_policy_attachment](./r/aws_ssoadmin_managed_policy_attachment.md)

- [aws_ssoadmin_permission_set](./r/aws_ssoadmin_permission_set.md)

- [aws_ssoadmin_permission_set_inline_policy](./r/aws_ssoadmin_permission_set_inline_policy.md)

- [aws_storagegateway_cache](./r/aws_storagegateway_cache.md)

- [aws_storagegateway_cached_iscsi_volume](./r/aws_storagegateway_cached_iscsi_volume.md)

- [aws_storagegateway_gateway](./r/aws_storagegateway_gateway.md)

- [aws_storagegateway_nfs_file_share](./r/aws_storagegateway_nfs_file_share.md)

- [aws_storagegateway_smb_file_share](./r/aws_storagegateway_smb_file_share.md)

- [aws_storagegateway_stored_iscsi_volume](./r/aws_storagegateway_stored_iscsi_volume.md)

- [aws_storagegateway_tape_pool](./r/aws_storagegateway_tape_pool.md)

- [aws_storagegateway_upload_buffer](./r/aws_storagegateway_upload_buffer.md)

- [aws_storagegateway_working_storage](./r/aws_storagegateway_working_storage.md)

- [aws_subnet](./r/aws_subnet.md)

- [aws_swf_domain](./r/aws_swf_domain.md)

- [aws_synthetics_canary](./r/aws_synthetics_canary.md)

- [aws_transfer_server](./r/aws_transfer_server.md)

- [aws_transfer_ssh_key](./r/aws_transfer_ssh_key.md)

- [aws_transfer_user](./r/aws_transfer_user.md)

- [aws_volume_attachment](./r/aws_volume_attachment.md)

- [aws_vpc](./r/aws_vpc.md)

- [aws_vpc_dhcp_options](./r/aws_vpc_dhcp_options.md)

- [aws_vpc_dhcp_options_association](./r/aws_vpc_dhcp_options_association.md)

- [aws_vpc_endpoint](./r/aws_vpc_endpoint.md)

- [aws_vpc_endpoint_connection_notification](./r/aws_vpc_endpoint_connection_notification.md)

- [aws_vpc_endpoint_route_table_association](./r/aws_vpc_endpoint_route_table_association.md)

- [aws_vpc_endpoint_service](./r/aws_vpc_endpoint_service.md)

- [aws_vpc_endpoint_service_allowed_principal](./r/aws_vpc_endpoint_service_allowed_principal.md)

- [aws_vpc_endpoint_subnet_association](./r/aws_vpc_endpoint_subnet_association.md)

- [aws_vpc_ipv4_cidr_block_association](./r/aws_vpc_ipv4_cidr_block_association.md)

- [aws_vpc_peering_connection](./r/aws_vpc_peering_connection.md)

- [aws_vpc_peering_connection_accepter](./r/aws_vpc_peering_connection_accepter.md)

- [aws_vpc_peering_connection_options](./r/aws_vpc_peering_connection_options.md)

- [aws_vpn_connection](./r/aws_vpn_connection.md)

- [aws_vpn_connection_route](./r/aws_vpn_connection_route.md)

- [aws_vpn_gateway](./r/aws_vpn_gateway.md)

- [aws_vpn_gateway_attachment](./r/aws_vpn_gateway_attachment.md)

- [aws_vpn_gateway_route_propagation](./r/aws_vpn_gateway_route_propagation.md)

- [aws_waf_byte_match_set](./r/aws_waf_byte_match_set.md)

- [aws_waf_geo_match_set](./r/aws_waf_geo_match_set.md)

- [aws_waf_ipset](./r/aws_waf_ipset.md)

- [aws_waf_rate_based_rule](./r/aws_waf_rate_based_rule.md)

- [aws_waf_regex_match_set](./r/aws_waf_regex_match_set.md)

- [aws_waf_regex_pattern_set](./r/aws_waf_regex_pattern_set.md)

- [aws_waf_rule](./r/aws_waf_rule.md)

- [aws_waf_rule_group](./r/aws_waf_rule_group.md)

- [aws_waf_size_constraint_set](./r/aws_waf_size_constraint_set.md)

- [aws_waf_sql_injection_match_set](./r/aws_waf_sql_injection_match_set.md)

- [aws_waf_web_acl](./r/aws_waf_web_acl.md)

- [aws_waf_xss_match_set](./r/aws_waf_xss_match_set.md)

- [aws_wafregional_byte_match_set](./r/aws_wafregional_byte_match_set.md)

- [aws_wafregional_geo_match_set](./r/aws_wafregional_geo_match_set.md)

- [aws_wafregional_ipset](./r/aws_wafregional_ipset.md)

- [aws_wafregional_rate_based_rule](./r/aws_wafregional_rate_based_rule.md)

- [aws_wafregional_regex_match_set](./r/aws_wafregional_regex_match_set.md)

- [aws_wafregional_regex_pattern_set](./r/aws_wafregional_regex_pattern_set.md)

- [aws_wafregional_rule](./r/aws_wafregional_rule.md)

- [aws_wafregional_rule_group](./r/aws_wafregional_rule_group.md)

- [aws_wafregional_size_constraint_set](./r/aws_wafregional_size_constraint_set.md)

- [aws_wafregional_sql_injection_match_set](./r/aws_wafregional_sql_injection_match_set.md)

- [aws_wafregional_web_acl](./r/aws_wafregional_web_acl.md)

- [aws_wafregional_web_acl_association](./r/aws_wafregional_web_acl_association.md)

- [aws_wafregional_xss_match_set](./r/aws_wafregional_xss_match_set.md)

- [aws_wafv2_ip_set](./r/aws_wafv2_ip_set.md)

- [aws_wafv2_regex_pattern_set](./r/aws_wafv2_regex_pattern_set.md)

- [aws_wafv2_rule_group](./r/aws_wafv2_rule_group.md)

- [aws_wafv2_web_acl](./r/aws_wafv2_web_acl.md)

- [aws_wafv2_web_acl_association](./r/aws_wafv2_web_acl_association.md)

- [aws_wafv2_web_acl_logging_configuration](./r/aws_wafv2_web_acl_logging_configuration.md)

- [aws_worklink_fleet](./r/aws_worklink_fleet.md)

- [aws_worklink_website_certificate_authority_association](./r/aws_worklink_website_certificate_authority_association.md)

- [aws_workspaces_directory](./r/aws_workspaces_directory.md)

- [aws_workspaces_ip_group](./r/aws_workspaces_ip_group.md)

- [aws_workspaces_workspace](./r/aws_workspaces_workspace.md)

- [aws_xray_encryption_config](./r/aws_xray_encryption_config.md)

- [aws_xray_group](./r/aws_xray_group.md)

- [aws_xray_sampling_rule](./r/aws_xray_sampling_rule.md)


[top](#index)

### Datasources


- [aws_acm_certificate](./d/aws_acm_certificate.md)

- [aws_acmpca_certificate](./d/aws_acmpca_certificate.md)

- [aws_acmpca_certificate_authority](./d/aws_acmpca_certificate_authority.md)

- [aws_alb](./d/aws_alb.md)

- [aws_alb_listener](./d/aws_alb_listener.md)

- [aws_alb_target_group](./d/aws_alb_target_group.md)

- [aws_ami](./d/aws_ami.md)

- [aws_ami_ids](./d/aws_ami_ids.md)

- [aws_api_gateway_api_key](./d/aws_api_gateway_api_key.md)

- [aws_api_gateway_domain_name](./d/aws_api_gateway_domain_name.md)

- [aws_api_gateway_resource](./d/aws_api_gateway_resource.md)

- [aws_api_gateway_rest_api](./d/aws_api_gateway_rest_api.md)

- [aws_api_gateway_vpc_link](./d/aws_api_gateway_vpc_link.md)

- [aws_apigatewayv2_api](./d/aws_apigatewayv2_api.md)

- [aws_apigatewayv2_apis](./d/aws_apigatewayv2_apis.md)

- [aws_arn](./d/aws_arn.md)

- [aws_autoscaling_group](./d/aws_autoscaling_group.md)

- [aws_autoscaling_groups](./d/aws_autoscaling_groups.md)

- [aws_availability_zone](./d/aws_availability_zone.md)

- [aws_availability_zones](./d/aws_availability_zones.md)

- [aws_backup_plan](./d/aws_backup_plan.md)

- [aws_backup_selection](./d/aws_backup_selection.md)

- [aws_backup_vault](./d/aws_backup_vault.md)

- [aws_batch_compute_environment](./d/aws_batch_compute_environment.md)

- [aws_batch_job_queue](./d/aws_batch_job_queue.md)

- [aws_billing_service_account](./d/aws_billing_service_account.md)

- [aws_caller_identity](./d/aws_caller_identity.md)

- [aws_canonical_user_id](./d/aws_canonical_user_id.md)

- [aws_cloudformation_export](./d/aws_cloudformation_export.md)

- [aws_cloudformation_stack](./d/aws_cloudformation_stack.md)

- [aws_cloudfront_cache_policy](./d/aws_cloudfront_cache_policy.md)

- [aws_cloudfront_distribution](./d/aws_cloudfront_distribution.md)

- [aws_cloudfront_origin_request_policy](./d/aws_cloudfront_origin_request_policy.md)

- [aws_cloudhsm_v2_cluster](./d/aws_cloudhsm_v2_cluster.md)

- [aws_cloudtrail_service_account](./d/aws_cloudtrail_service_account.md)

- [aws_cloudwatch_log_group](./d/aws_cloudwatch_log_group.md)

- [aws_codeartifact_authorization_token](./d/aws_codeartifact_authorization_token.md)

- [aws_codeartifact_repository_endpoint](./d/aws_codeartifact_repository_endpoint.md)

- [aws_codecommit_repository](./d/aws_codecommit_repository.md)

- [aws_codestarconnections_connection](./d/aws_codestarconnections_connection.md)

- [aws_cognito_user_pools](./d/aws_cognito_user_pools.md)

- [aws_cur_report_definition](./d/aws_cur_report_definition.md)

- [aws_customer_gateway](./d/aws_customer_gateway.md)

- [aws_db_cluster_snapshot](./d/aws_db_cluster_snapshot.md)

- [aws_db_event_categories](./d/aws_db_event_categories.md)

- [aws_db_instance](./d/aws_db_instance.md)

- [aws_db_snapshot](./d/aws_db_snapshot.md)

- [aws_db_subnet_group](./d/aws_db_subnet_group.md)

- [aws_directory_service_directory](./d/aws_directory_service_directory.md)

- [aws_docdb_engine_version](./d/aws_docdb_engine_version.md)

- [aws_docdb_orderable_db_instance](./d/aws_docdb_orderable_db_instance.md)

- [aws_dx_gateway](./d/aws_dx_gateway.md)

- [aws_dynamodb_table](./d/aws_dynamodb_table.md)

- [aws_ebs_default_kms_key](./d/aws_ebs_default_kms_key.md)

- [aws_ebs_encryption_by_default](./d/aws_ebs_encryption_by_default.md)

- [aws_ebs_snapshot](./d/aws_ebs_snapshot.md)

- [aws_ebs_snapshot_ids](./d/aws_ebs_snapshot_ids.md)

- [aws_ebs_volume](./d/aws_ebs_volume.md)

- [aws_ebs_volumes](./d/aws_ebs_volumes.md)

- [aws_ec2_coip_pool](./d/aws_ec2_coip_pool.md)

- [aws_ec2_coip_pools](./d/aws_ec2_coip_pools.md)

- [aws_ec2_instance_type](./d/aws_ec2_instance_type.md)

- [aws_ec2_instance_type_offering](./d/aws_ec2_instance_type_offering.md)

- [aws_ec2_instance_type_offerings](./d/aws_ec2_instance_type_offerings.md)

- [aws_ec2_local_gateway](./d/aws_ec2_local_gateway.md)

- [aws_ec2_local_gateway_route_table](./d/aws_ec2_local_gateway_route_table.md)

- [aws_ec2_local_gateway_route_tables](./d/aws_ec2_local_gateway_route_tables.md)

- [aws_ec2_local_gateway_virtual_interface](./d/aws_ec2_local_gateway_virtual_interface.md)

- [aws_ec2_local_gateway_virtual_interface_group](./d/aws_ec2_local_gateway_virtual_interface_group.md)

- [aws_ec2_local_gateway_virtual_interface_groups](./d/aws_ec2_local_gateway_virtual_interface_groups.md)

- [aws_ec2_local_gateways](./d/aws_ec2_local_gateways.md)

- [aws_ec2_managed_prefix_list](./d/aws_ec2_managed_prefix_list.md)

- [aws_ec2_spot_price](./d/aws_ec2_spot_price.md)

- [aws_ec2_transit_gateway](./d/aws_ec2_transit_gateway.md)

- [aws_ec2_transit_gateway_dx_gateway_attachment](./d/aws_ec2_transit_gateway_dx_gateway_attachment.md)

- [aws_ec2_transit_gateway_peering_attachment](./d/aws_ec2_transit_gateway_peering_attachment.md)

- [aws_ec2_transit_gateway_route_table](./d/aws_ec2_transit_gateway_route_table.md)

- [aws_ec2_transit_gateway_route_tables](./d/aws_ec2_transit_gateway_route_tables.md)

- [aws_ec2_transit_gateway_vpc_attachment](./d/aws_ec2_transit_gateway_vpc_attachment.md)

- [aws_ec2_transit_gateway_vpn_attachment](./d/aws_ec2_transit_gateway_vpn_attachment.md)

- [aws_ecr_authorization_token](./d/aws_ecr_authorization_token.md)

- [aws_ecr_image](./d/aws_ecr_image.md)

- [aws_ecr_repository](./d/aws_ecr_repository.md)

- [aws_ecs_cluster](./d/aws_ecs_cluster.md)

- [aws_ecs_container_definition](./d/aws_ecs_container_definition.md)

- [aws_ecs_service](./d/aws_ecs_service.md)

- [aws_ecs_task_definition](./d/aws_ecs_task_definition.md)

- [aws_efs_access_point](./d/aws_efs_access_point.md)

- [aws_efs_access_points](./d/aws_efs_access_points.md)

- [aws_efs_file_system](./d/aws_efs_file_system.md)

- [aws_efs_mount_target](./d/aws_efs_mount_target.md)

- [aws_eip](./d/aws_eip.md)

- [aws_eks_cluster](./d/aws_eks_cluster.md)

- [aws_eks_cluster_auth](./d/aws_eks_cluster_auth.md)

- [aws_elastic_beanstalk_application](./d/aws_elastic_beanstalk_application.md)

- [aws_elastic_beanstalk_hosted_zone](./d/aws_elastic_beanstalk_hosted_zone.md)

- [aws_elastic_beanstalk_solution_stack](./d/aws_elastic_beanstalk_solution_stack.md)

- [aws_elasticache_cluster](./d/aws_elasticache_cluster.md)

- [aws_elasticache_replication_group](./d/aws_elasticache_replication_group.md)

- [aws_elasticsearch_domain](./d/aws_elasticsearch_domain.md)

- [aws_elb](./d/aws_elb.md)

- [aws_elb_hosted_zone_id](./d/aws_elb_hosted_zone_id.md)

- [aws_elb_service_account](./d/aws_elb_service_account.md)

- [aws_glue_script](./d/aws_glue_script.md)

- [aws_guardduty_detector](./d/aws_guardduty_detector.md)

- [aws_iam_account_alias](./d/aws_iam_account_alias.md)

- [aws_iam_group](./d/aws_iam_group.md)

- [aws_iam_instance_profile](./d/aws_iam_instance_profile.md)

- [aws_iam_policy](./d/aws_iam_policy.md)

- [aws_iam_policy_document](./d/aws_iam_policy_document.md)

- [aws_iam_role](./d/aws_iam_role.md)

- [aws_iam_server_certificate](./d/aws_iam_server_certificate.md)

- [aws_iam_user](./d/aws_iam_user.md)

- [aws_identitystore_group](./d/aws_identitystore_group.md)

- [aws_identitystore_user](./d/aws_identitystore_user.md)

- [aws_imagebuilder_component](./d/aws_imagebuilder_component.md)

- [aws_imagebuilder_distribution_configuration](./d/aws_imagebuilder_distribution_configuration.md)

- [aws_imagebuilder_image](./d/aws_imagebuilder_image.md)

- [aws_imagebuilder_image_pipeline](./d/aws_imagebuilder_image_pipeline.md)

- [aws_imagebuilder_image_recipe](./d/aws_imagebuilder_image_recipe.md)

- [aws_imagebuilder_infrastructure_configuration](./d/aws_imagebuilder_infrastructure_configuration.md)

- [aws_inspector_rules_packages](./d/aws_inspector_rules_packages.md)

- [aws_instance](./d/aws_instance.md)

- [aws_instances](./d/aws_instances.md)

- [aws_internet_gateway](./d/aws_internet_gateway.md)

- [aws_iot_endpoint](./d/aws_iot_endpoint.md)

- [aws_ip_ranges](./d/aws_ip_ranges.md)

- [aws_kinesis_stream](./d/aws_kinesis_stream.md)

- [aws_kinesis_stream_consumer](./d/aws_kinesis_stream_consumer.md)

- [aws_kms_alias](./d/aws_kms_alias.md)

- [aws_kms_ciphertext](./d/aws_kms_ciphertext.md)

- [aws_kms_key](./d/aws_kms_key.md)

- [aws_kms_secret](./d/aws_kms_secret.md)

- [aws_kms_secrets](./d/aws_kms_secrets.md)

- [aws_lakeformation_data_lake_settings](./d/aws_lakeformation_data_lake_settings.md)

- [aws_lakeformation_permissions](./d/aws_lakeformation_permissions.md)

- [aws_lakeformation_resource](./d/aws_lakeformation_resource.md)

- [aws_lambda_alias](./d/aws_lambda_alias.md)

- [aws_lambda_code_signing_config](./d/aws_lambda_code_signing_config.md)

- [aws_lambda_function](./d/aws_lambda_function.md)

- [aws_lambda_invocation](./d/aws_lambda_invocation.md)

- [aws_lambda_layer_version](./d/aws_lambda_layer_version.md)

- [aws_launch_configuration](./d/aws_launch_configuration.md)

- [aws_launch_template](./d/aws_launch_template.md)

- [aws_lb](./d/aws_lb.md)

- [aws_lb_listener](./d/aws_lb_listener.md)

- [aws_lb_target_group](./d/aws_lb_target_group.md)

- [aws_lex_bot](./d/aws_lex_bot.md)

- [aws_lex_bot_alias](./d/aws_lex_bot_alias.md)

- [aws_lex_intent](./d/aws_lex_intent.md)

- [aws_lex_slot_type](./d/aws_lex_slot_type.md)

- [aws_mq_broker](./d/aws_mq_broker.md)

- [aws_msk_cluster](./d/aws_msk_cluster.md)

- [aws_msk_configuration](./d/aws_msk_configuration.md)

- [aws_nat_gateway](./d/aws_nat_gateway.md)

- [aws_neptune_engine_version](./d/aws_neptune_engine_version.md)

- [aws_neptune_orderable_db_instance](./d/aws_neptune_orderable_db_instance.md)

- [aws_network_acls](./d/aws_network_acls.md)

- [aws_network_interface](./d/aws_network_interface.md)

- [aws_network_interfaces](./d/aws_network_interfaces.md)

- [aws_organizations_organization](./d/aws_organizations_organization.md)

- [aws_organizations_organizational_units](./d/aws_organizations_organizational_units.md)

- [aws_outposts_outpost](./d/aws_outposts_outpost.md)

- [aws_outposts_outpost_instance_type](./d/aws_outposts_outpost_instance_type.md)

- [aws_outposts_outpost_instance_types](./d/aws_outposts_outpost_instance_types.md)

- [aws_outposts_outposts](./d/aws_outposts_outposts.md)

- [aws_outposts_site](./d/aws_outposts_site.md)

- [aws_outposts_sites](./d/aws_outposts_sites.md)

- [aws_partition](./d/aws_partition.md)

- [aws_prefix_list](./d/aws_prefix_list.md)

- [aws_pricing_product](./d/aws_pricing_product.md)

- [aws_qldb_ledger](./d/aws_qldb_ledger.md)

- [aws_ram_resource_share](./d/aws_ram_resource_share.md)

- [aws_rds_certificate](./d/aws_rds_certificate.md)

- [aws_rds_cluster](./d/aws_rds_cluster.md)

- [aws_rds_engine_version](./d/aws_rds_engine_version.md)

- [aws_rds_orderable_db_instance](./d/aws_rds_orderable_db_instance.md)

- [aws_redshift_cluster](./d/aws_redshift_cluster.md)

- [aws_redshift_orderable_cluster](./d/aws_redshift_orderable_cluster.md)

- [aws_redshift_service_account](./d/aws_redshift_service_account.md)

- [aws_region](./d/aws_region.md)

- [aws_regions](./d/aws_regions.md)

- [aws_route](./d/aws_route.md)

- [aws_route53_delegation_set](./d/aws_route53_delegation_set.md)

- [aws_route53_resolver_endpoint](./d/aws_route53_resolver_endpoint.md)

- [aws_route53_resolver_rule](./d/aws_route53_resolver_rule.md)

- [aws_route53_resolver_rules](./d/aws_route53_resolver_rules.md)

- [aws_route53_zone](./d/aws_route53_zone.md)

- [aws_route_table](./d/aws_route_table.md)

- [aws_route_tables](./d/aws_route_tables.md)

- [aws_s3_bucket](./d/aws_s3_bucket.md)

- [aws_s3_bucket_object](./d/aws_s3_bucket_object.md)

- [aws_s3_bucket_objects](./d/aws_s3_bucket_objects.md)

- [aws_sagemaker_prebuilt_ecr_image](./d/aws_sagemaker_prebuilt_ecr_image.md)

- [aws_secretsmanager_secret](./d/aws_secretsmanager_secret.md)

- [aws_secretsmanager_secret_rotation](./d/aws_secretsmanager_secret_rotation.md)

- [aws_secretsmanager_secret_version](./d/aws_secretsmanager_secret_version.md)

- [aws_security_group](./d/aws_security_group.md)

- [aws_security_groups](./d/aws_security_groups.md)

- [aws_serverlessapplicationrepository_application](./d/aws_serverlessapplicationrepository_application.md)

- [aws_servicequotas_service](./d/aws_servicequotas_service.md)

- [aws_servicequotas_service_quota](./d/aws_servicequotas_service_quota.md)

- [aws_sfn_activity](./d/aws_sfn_activity.md)

- [aws_sfn_state_machine](./d/aws_sfn_state_machine.md)

- [aws_signer_signing_job](./d/aws_signer_signing_job.md)

- [aws_signer_signing_profile](./d/aws_signer_signing_profile.md)

- [aws_sns_topic](./d/aws_sns_topic.md)

- [aws_sqs_queue](./d/aws_sqs_queue.md)

- [aws_ssm_document](./d/aws_ssm_document.md)

- [aws_ssm_parameter](./d/aws_ssm_parameter.md)

- [aws_ssm_patch_baseline](./d/aws_ssm_patch_baseline.md)

- [aws_ssoadmin_instances](./d/aws_ssoadmin_instances.md)

- [aws_ssoadmin_permission_set](./d/aws_ssoadmin_permission_set.md)

- [aws_storagegateway_local_disk](./d/aws_storagegateway_local_disk.md)

- [aws_subnet](./d/aws_subnet.md)

- [aws_subnet_ids](./d/aws_subnet_ids.md)

- [aws_transfer_server](./d/aws_transfer_server.md)

- [aws_vpc](./d/aws_vpc.md)

- [aws_vpc_dhcp_options](./d/aws_vpc_dhcp_options.md)

- [aws_vpc_endpoint](./d/aws_vpc_endpoint.md)

- [aws_vpc_endpoint_service](./d/aws_vpc_endpoint_service.md)

- [aws_vpc_peering_connection](./d/aws_vpc_peering_connection.md)

- [aws_vpc_peering_connections](./d/aws_vpc_peering_connections.md)

- [aws_vpcs](./d/aws_vpcs.md)

- [aws_vpn_gateway](./d/aws_vpn_gateway.md)

- [aws_waf_ipset](./d/aws_waf_ipset.md)

- [aws_waf_rate_based_rule](./d/aws_waf_rate_based_rule.md)

- [aws_waf_rule](./d/aws_waf_rule.md)

- [aws_waf_web_acl](./d/aws_waf_web_acl.md)

- [aws_wafregional_ipset](./d/aws_wafregional_ipset.md)

- [aws_wafregional_rate_based_rule](./d/aws_wafregional_rate_based_rule.md)

- [aws_wafregional_rule](./d/aws_wafregional_rule.md)

- [aws_wafregional_web_acl](./d/aws_wafregional_web_acl.md)

- [aws_wafv2_ip_set](./d/aws_wafv2_ip_set.md)

- [aws_wafv2_regex_pattern_set](./d/aws_wafv2_regex_pattern_set.md)

- [aws_wafv2_rule_group](./d/aws_wafv2_rule_group.md)

- [aws_wafv2_web_acl](./d/aws_wafv2_web_acl.md)

- [aws_workspaces_bundle](./d/aws_workspaces_bundle.md)

- [aws_workspaces_directory](./d/aws_workspaces_directory.md)

- [aws_workspaces_image](./d/aws_workspaces_image.md)

- [aws_workspaces_workspace](./d/aws_workspaces_workspace.md)


[top](#index)