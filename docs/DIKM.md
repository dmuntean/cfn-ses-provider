# Custom::DKIM
The `Custom::DKIM` creates DomainKeys Identified Email (DKIM) verification record.

## Syntax
To declare this entity in your AWS CloudFormation template, use the following syntax:

```json
{
  "Type" : "Custom::DKIM",
  "Properties" : {
    "HostedZoneId": String,
    "Region": String,
    "ServiceToken" : String
  }
}

It will create a `_amazonses` TXT record and a number of `_domainkey` records in the
hosted zone pointed to by `HostedZoneId`.

```
## Properties
You can specify the following properties:

    "HostedZoneId" - in which to create the DKIM verification records  (required).
    "Region" - from which to send emails (default: "eu-west-1")
    "ServiceToken" - pointing to the function implementing this (required)

## Return values
With 'Fn::GetAtt' the following values are available:

- `ChangeId` - The Route53 ChangeId

For more information about using Fn::GetAtt, see [Fn::GetAtt](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-getatt.html).
