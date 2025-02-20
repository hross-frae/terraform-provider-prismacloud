---
page_title: "Prisma Cloud: prismacloud_integration"
---

# prismacloud_integration

Retrieves integration information.

## Example Usage

```hcl
data "prismacloud_integration" "example" {
    name = "myIntegration"
}
```

## Argument Reference

One of the following must be specified:

* `name` - Name of the integration.
* `integration_id` - Integration ID.

## Attribute Reference

* `description` - Description.
* `integration_type` - Integration type.
* `enabled` - (bool) Enabled.
* `created_by` - Created by.
* `created_ts` - (int) Created on.
* `last_modified_by` - Last modified by.
* `last_modified_ts` - (int) Last modified timestamp.
* `status` - Status.
* `valid` - (bool) Valid.
* `reason` - Model for the integration status details, as defined [below](#reason).
* `integration_config` - Integration configuration, the values depend on the integration type, as defined [below](#integration-config).

### Reason

* `last_updated` - (int) Last updated.
* `error_type` - Error type.
* `message` - Message.
* `details` - Model for message details, as defined [below](#details).

### Details

* `status_code` - (int) Status code.
* `subject` - Subject.
* `message` - Internationalization key.

### Integration Config

* `queue_url` - The Queue URL you used when you configured Prisma Cloud in Amazon SQS or Azure Service Bus Queue.
* `login` - (Qualys/ServiceNow) Login.
* `base_url` - Qualys Security Operations Center server API URL (without "http(s)")
* `password` - (Qualys/ServiceNow) Password.
* `api_key` - Demisto Api Key.
* `host_url` - ServiceNow URL/Demisto URL.
* `secret_key` - Secret Key for Tenable.
* `access_key` - Access Key for Tenable.
* `tables` - (Map of bools) Key/value pairs that identify the ServiceNow module tables with which to integrate (e.g. - incident, sn_si_incident, or em_event).
* `version` - ServiceNow release version.
* `url` - Webhook URL or Splunk HTTP event collector URL.
* `headers` - Webhook headers, as defined [below](#headers).
* `auth_token` - PagerDuty/Splunk authentication token for the event collector.
* `integration_key` - PagerDuty integration key.
* `source_id` - GCP Source ID for Google CSCC integration.
* `org_id` - GCP Organization ID for Google CSCC integration.
* `account_id` - AWS/Azure account ID for AWS Security Hub/Azure Service Bus Queue integration.
* `connection_string` - Connection string for Azure Service Bus Queue integration.
* `domain` - Okta Domain.
* `api_token` - Okta API token.
* `user_name` - Snowflake username.
* `pipe_name` - Snowflake pipename.
* `pass_phrase` - Snowflake PassPhrase.
* `private_key` - Snowflake Private Key.
* `roll_up_interval` - File roll up time in minutes for AWS S3 integration and for snowflake integration.  
* `staging_integration_id` - Amazon s3 integration ID for Snowflake integration.
* `regions` - List of AWS regions for AWS Security Hub integration, as defined [below](#regions).
* `s3_uri` - AWS S3 URI for Amazon S3 integration.
* `region` - AWS region for Amazon S3 integration.
* `role_arn` - AWS role ARN for Amazon S3 integration.
* `external_id` - AWS external ID for Amazon S3 integration.
* `source_type` - Source type for splunk integration.

### Headers

* `key` - Header name.
* `value` - Header value.
* `secure` - (bool) Secure.
* `read_only` - (bool) Read-only.

### Regions

* `name` - AWS region name.
* `api_identifier` - AWS region code.
* `cloud_type` - Cloud Type.
