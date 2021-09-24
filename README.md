Cloudtrail
==========

Ensure CloudTrail is enabled in all regions.

CIS Amazon Web Services Foundations Benchmark

Check CloudTrail is enabled for "ALL" region capturing all types of Management Events

## Perform the following to enable global (Multi-region) CloudTrail logging:

### Via the management Console

1. Sign in to the AWS Management Console and open the CloudTrail console at https://console.aws.amazon.com/cloudtrail
2. Click on Trails on the left navigation pane
3. Click Get Started Now, if presented

### Click Create trail

Enter a trail name in the Trail name box
Set the Apply trail to all regions option to Yes
Specify an S3 bucket name in the S3 bucket box
Click Create
4. If 1 or more trails already exist, select the target trail to enable for global logging
5. Click the edit icon (pencil) next to Apply trail to all regions, Click Yes and Click Save.
6. Click the edit icon (pencil) next to Management Events click All for setting Read/Write Events and Click Save.

## Via CLI

# aws cloudtrail create-trail --name [trail_name] --bucket-name [s3_bucket_for_cloudtrail] --is-multi-region-trail

# aws cloudtrail update-trail --name [trail_name] --is-multi-region-trail

**Note**: Creating CloudTrail via CLI without providing any overriding options configures Management Events to set All type of Read/Writes by default.

## Evidence

arn:aws:cloudtrail:us-east-1:012345678900:trail/management-events

```
{"Management Events Value":[{"readWriteType":"All","includeManagementEvents":true,"dataResources":[],"excludeManagementEventSources":[]}],"Cloudtrail Logging Status":"true"}
```
