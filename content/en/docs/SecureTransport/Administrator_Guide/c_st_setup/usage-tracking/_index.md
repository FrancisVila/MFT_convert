{
    "title": "Usage reporting for subscription-based licenses",
    "linkTitle": "Usage reporting for subscription-based licenses",
    "weight": "200"
}This topic describes the concepts and logic in usage tracking and why you might need to enable it for your on-premises Axway product.

## What is usage tracking?

Usage tracking identifies how Axway measures the subscription services you use on a monthly basis. Axway measures your usage to make sure it is within the prescribed thresholds specified in your subscription and determine whether overages require billing adjustments. See [About subscription usage tracking](https://docs.axway.com/bundle/subusage_en/page/about_subscription_usage_tracking.html) for more information.

## Must I enable usage tracking?

You must enable usage tracking if you use an Axway on-premises product on a subscription basis. You do not need to use usage tracking if you have a perpetual license. See [Supported products and services for subscriptions](https://docs.axway.com/bundle/subusage_en/page/about_subscription_usage_tracking.html).

If you have an AMPLIFY account, you can log on to the [AMPLIFY Platform](https://platform.axway.com/) and look up information about your subscriptions and service entitlements. If you don't have an AMPLIFY account, most likely you are using products under licenses and do not have any subscriptions. However, if you are unsure whether usage tracking applies to you, contact your Axway representative or [Axway support](https://support.axway.com/).

## What if I don't enable usage tracking?

Your subscription agreement with Axway requires usage tracking. If you don't enable usage tracking for an on-premises product used under a subscription, you might be in violation of your agreement and, as a consequence, be subject to penalties. It's in your best interest to enable usage tracking because it ensures are using the services you are entitled to.

## How do I enable usage tracking?

SecureTransport offers two options for usage reporting:

-   *Automatic* for MFT environments using the AMPLIFY Edge Agent  
    See the [AMPLIFY subscription usage and reporting](https://docs.axway.com/bundle/subusage_en/page/amplify_subscription_usage_and_reporting.html) guide. This guide has information for installing and configuring an agent that collects data from your on-premises product and uploads usage reports to the AMPLIFY platform. See [Set up usage reporting](st-edge_agent).
-   *Manual* for SecureTransport deployments only  
    This option is only applicable to environments with SecureTransport only (without Transfer CFT or other MFT products). See [Usage and Deployment information](generate_usage_report).
