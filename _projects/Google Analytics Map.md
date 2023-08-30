---
title: Google Analytics Map - UA to GA4
---
(from [Google](https://developers.google.com/analytics/devguides/migration/api/reporting-ua-to-ga4-dims-mets))

| Section | Type | Label | Universal Analytics | Google Analytics 4 |
| ---- |--------- | ------ | ---------| ----------- |
| User | Metrics | Users  | ga:users  | totalUsers |
| User | Metrics | New Users  | ga:newUsers  | newUsers |
| User | Metrics | 1 Day Active Users  | ga:1dayUsers  | active1DayUsers |
| User | Metrics | 7 Day Active Users  | ga:7dayUsers  | active7DayUsers |
| User | Metrics | 28 Day Active Users  | ga:28dayUsers  | active28DayUsers |
| User | Metrics | Number of Sessions per User  | ga:sessionsPerUser  | sessionsPerUser |
| Session | Metrics | Field name  | UA Name  | GA4 equivalent name |
| Session | Metrics | Sessions  | ga:sessions  | sessions |
| Session | Metrics | Session Duration  | ga:sessionDuration  | userEngagementDuration |
| Session | Metrics | Hits  | ga:hits  | eventCount |
| Traffic Sources | Dimensions | Full Referrer  | ga:fullReferrer  | pageReferrer |
| Traffic Sources | Dimensions | Campaign  | ga:campaign  | sessionCampaignName |
| Traffic Sources | Dimensions | Source  | ga:source  | sessionSource |
| Traffic Sources | Dimensions | Medium  | ga:medium  | sessionMedium |
| Traffic Sources | Dimensions | Campaign Code  | ga:campaignCode  | sessionCampaignId |
| Adwords | Dimensions | Ad Format  | ga:adFormat  | adFormat, in combination with adSourceName |
| Adwords | Dimensions | Google Ads: Ad Group  | ga:adGroup  | sessionGoogleAdsAdGroupName |
| Adwords | Dimensions | Ad Distribution Network  | ga:adDistributionNetwork  | sessionGoogleAdsAdNetworkType |
| Adwords | Dimensions | Search Query  | ga:adMatchedQuery  | sessionGoogleAdsQuery |
| Adwords | Dimensions | Google Ads Campaign ID  | ga:adwordsCampaignID  | sessionCampaignId |
| Adwords | Dimensions | Google Ads Ad Group ID  | ga:adwordsAdGroupID  | sessionGoogleAdsAdGroupId |
| Adwords | Dimensions | Google Ads Creative ID  | ga:adwordsCreativeID  | sessionGoogleAdsCreativeId |
| Adwords | Metrics | Advertiser ad clicks  | ga:adClicks  | advertiserAdClicks |
| Adwords | Metrics | Advertiser ad impressions  | ga:impressions  | advertiserAdImpressions |
| Adwords | Metrics | Advertiser ad cost  | ga:adCost  | adveristerAdCost |
| Platform or Device | Dimensions | Browser  | ga:browser  | browser |
| Platform or Device | Dimensions | Operating System  | ga:operatingSystem  | operatingSystem |
| Platform or Device | Dimensions | Operating System Version  | ga:operatingSystemVersion  | operatingSystemVersion |
| Platform or Device | Dimensions | Mobile Device Branding  | ga:mobileDeviceBranding  | mobileDeviceBranding |
| Platform or Device | Dimensions | Mobile Device Model  | ga:mobileDeviceModel  | mobileDeviceModel |
| Platform or Device | Dimensions | Device Category  | ga:deviceCategory  | deviceCategory |
| Platform or Device | Dimensions | Data Source  | ga:dataSource  | platform |
| Geo Network | Dimensions | Country  | ga:country  | country |
| Geo Network | Dimensions | Region  | ga:region  | region |
| Geo Network | Dimensions | City  | ga:city  | city |
| Geo Network | Dimensions | City ID  | ga:cityId  | cityId |
| Geo Network | Dimensions | Country ISO Code  | ga:countryIsoCode  | countryId |
| System | Dimensions | Language  | ga:language  | language |
| System | Dimensions | Screen Resolution  | ga:screenResolution  | screenResolution |
| Page Tracking | Dimensions | Hostname  | ga:hostname  | hostName |
| Page Tracking | Dimensions | Page  | ga:pagePath  | pagePathPlusQueryString |
| Page Tracking | Dimensions | Page Title  | ga:pageTitle  | pageTitle |
| Page Tracking | Metrics | Pageviews  | ga:pageviews  | screenPageViews |
| Page Tracking | Metrics | Time on Page  | ga:timeOnPage  | userEngagementDuration |
| App Tracking | Dimensions | App Version  | ga:appVersion  | appVersion |
| App Tracking | Dimensions | Screen Name  | ga:screenName  | unifiedScreenName |
| App Tracking | Metrics | Screen Views  | ga:screenviews  | screenPageViews |
| Event Tracking | Dimensions | Event Label  | ga:eventLabel  | eventName |
| Event Tracking | Metrics | Total Events  | ga:totalEvents  | eventCount |
| Event Tracking | Metrics | Event Value  | ga:eventValue  | eventValue |
| Ecommerce | Dimensions | Item Brand  | ga:productBrand  | itemBrand |
| Ecommerce | Dimensions | Item Category  | ga:productCategory  | itemCategory |
| Ecommerce | Dimensions | Item Category (Enhanced Ecommerce)  | ga:productCategoryHierarchy  | itemCategory, itemCategory2, itemCategory3, itemCategory4, itemCategory5 |
| Ecommerce | Dimensions | Item ID  | ga:productSku  | itemId |
| Ecommerce | Dimensions | Item list name  | ga:productListName  | itemListName |
| Ecommerce | Dimensions | Item name  | ga:productName  | itemName |
| Ecommerce | Dimensions | Item promotion creative name  | ga:internalPromotionCreative  | itemPromotionCreativeName |
| Ecommerce | Dimensions | Item promotion ID  | ga:internalPromotionId  | itemPromotionId |
| Ecommerce | Dimensions | Item promotion name  | ga:internalPromotionName  | itemPromotionName |
| Ecommerce | Dimensions | Order Coupon Code  | ga:orderCouponCode  | orderCoupon |
| Ecommerce | Dimensions | Transaction ID  | ga:transactionId  | transactionId |
| Ecommerce | Metrics | Add-to-carts  | ga:productAddsToCart  | addToCarts |
| Ecommerce | Metrics | Cart-to-view rate  | ga:cartToDetailRate  | cartToViewRate |
| Ecommerce | Metrics | Checkouts  | ga:productCheckouts  | checkouts |
| Ecommerce | Metrics | Ecommerce purchases  | ga:uniquePurchases  | ecommercePurchases |
| Ecommerce | Metrics | Item list click through rate  | ga:productListCTR  | itemListClickThroughRate |
| Ecommerce | Metrics | Item list clicks  | ga:productListClicks  | itemListClicks |
| Ecommerce | Metrics | Item list views  | ga:productListViews  | itemListViews |
| Ecommerce | Metrics | Item promotion click through rate  | ga:internalPromotionCTR  | itemPromotionClickThroughRate |
| Ecommerce | Metrics | Item promotion clicks  | ga:internalPromotionClicks  | itemPromotionClicks |
| Ecommerce | Metrics | Item promotion views  | ga:internalPromotionViews  | itemPromotionViews |
| Ecommerce | Metrics | Item purchase quantity  | ga:itemQuantity  | itemPurchaseQuantity |
| Ecommerce | Metrics | Item revenue  | ga:itemRevenue  | itemRevenue |
| Ecommerce | Metrics | Item views  | ga:productDetailViews  | itemViews |
| Time | Dimensions | Date  | ga:date  | date |
| Time | Dimensions | Year  | ga:year  | year |
| Time | Dimensions | Month of the year  | ga:month  | month |
| Time | Dimensions | Week of the Year  | ga:week  | week |
| Time | Dimensions | Day of the month  | ga:day  | day |
| Time | Dimensions | Hour  | ga:hour  | hour |
| Time | Dimensions | Minute  | ga:minute  | minute |
| Time | Dimensions | Month Index  | ga:nthMonth  | nthMonth |
| Time | Dimensions | Week Index  | ga:nthWeek  | nthWeek |
| Time | Dimensions | Day Index  | ga:nthDay  | nthDay |
| Time | Dimensions | Minute Index  | ga:nthMinute  | nthMinute |
| Time | Dimensions | Day of Week  | ga:dayOfWeek  | dayOfWeek |
| Time | Dimensions | Hour of Day  | ga:dateHour  | dateHour |
| Time | Dimensions | Date Hour and Minute  | ga:dateHourMinute  | dateHourMinute |
| Time | Dimensions | Hour Index  | ga:nthHour  | nthHour |
| Audience | Dimensions | Age  | ga:userAgeBracket  | userAgeBracket |
| Audience | Dimensions | Gender  | ga:userGender  | userGender |
| Audience | Dimensions | In-Market Segment  | ga:interestInMarketCategory  | brandingInterest |
| Lifetime Value and Cohorts | Dimensions | Acquisition Campaign  | ga:acquisitionCampaign  | firstUserCampaignName |
| Lifetime Value and Cohorts | Dimensions | Acquisition Medium  | ga:acquisitionMedium  | firstUserMedium |
| Lifetime Value and Cohorts | Dimensions | Acquisition Source  | ga:acquisitionSource  | firstUserSource |
| Lifetime Value and Cohorts | Dimensions | Cohort  | ga:cohort  | cohort |
| Lifetime Value and Cohorts | Dimensions | Day  | ga:cohortNthDay  | cohortNthDay |
| Lifetime Value and Cohorts | Dimensions | Month  | ga:cohortNthMonth  | cohortNthMonth |
| Lifetime Value and Cohorts | Dimensions | Week  | ga:cohortNthWeek  | cohortNthWeek |
| Lifetime Value and Cohorts | Metrics | Users  | ga:cohortActiveUsers  | cohortActiveUsers |
| Lifetime Value and Cohorts | Metrics | Total Users  | ga:cohortTotalUsers  | cohortTotalUsers |
| Channel Grouping | Dimensions | Default Channel Grouping  | ga:channelGrouping  | sessionDefaultChannelGrouping |