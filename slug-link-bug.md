<!--
title: Your First Data
meta_title: Your First Data | Getting Started | Telerik Analytics
slug: getting-started-your-first-data
tags: Features, Application Analytics, Feature Tracking, Feature Usage
publish: true
-->

This article will describe how to get your application's very first data into the Analytics dashboard.

The article will also describe reasons for the data not appearing.

## Seeing your first data

So, you have [created a Telerik Analytics project]({{slug:getting-started-your-application}}). You have logged into your account using the [analytics client]({{slug:client-introduction}}) and you have clicked on the [dashboard]({{slug:client-reports-dashboard}}). But instead of seeing colorful graphs you are being treated to a set of empty boxes, proclaming you have "No data yet":

![Seeing "No data yet" in the Analytics Dashboard](images/your-first-data-no-data.png)
<!-- https://docs.google.com/a/linkage.dk/drawings/d/1nvkPHRTwz9pbNMS2Pu9TAeezBTFD6xSBEmVhCCJIuGs/edit -->

What is going on? And what can you do about it?

Let us revisit every single step of how analytics data comes into the dashboard:

![The Telerik Analytics service at a glance](images/analytics-overview.png)

1. You create an Analytics project and get a unique product key, like "b1bd264....be34c"
2. You **integrate** the monitor into your application, calling `Start` and `Stop`
3. You **run** your application once
4. You **wait** up to five minutes

If you are seeing the "No data yet" message then obviously you have already completed step 1. Congratulations, you are almost there - now let us tackle steps 2-4.

### Step 2: Integrate the monitor

To receive data from an application you must surely first integrate Analytics into that application. This is a job for software developers. They can follow these [monitor integration guidelines]({{slug:integration-introduction}}) and only need the unique product key from step 1 to get started. Custom tracking can be added in abundance later, but initially we recommend just calling `Start` when your application starts and `Stop` when it stops.

### Step 3: Run the application

For the monitor to be activated and submit data, you need to run it at least once. And you need to run it on a device or machine that is online, connected to the internet. What happens if you are not online? Then the gathered statistics is stored locally on the device until you eventually run the application while online. What happens if you kill the application before `Stop` is called? Then statistics may fail to be submitted, but it will be submitted at next application start-up.

### Step 4: Wait

Data from the monitor may be processed for up to about 5 minutes in the Analytics service before appearing on the dashboard.

## I still don't see any data

You data may have arrived to the server, but still not be displayed. Here are some things to check:

* **Refresh**: By default, the dashboard does *not* refresh itself automatically, but you can manually click the refresh-button or enable autorefresh. Those options are in the upper-right corner in the dashboard:
![Dashboard refresh options](images/dashboard-refresh-options.png)

* **Live mode**: If you are waiting for new data to appear then make sure you have turned on *live mode*. This is the default viewing mode for new projects, but you may have inadvertedly turned it off. In live mode data is shown as soon at it makes it through the 5-minute processing step; otherwise, data from today is not shown at all. The view mode is toggled below tht period selector. If you are seeing the indicator below then you are in live mode:
![Viewing data in "Live Mode"](images/your-first-data-live-mode.png)

* **Global filter**: You may have applied a global filter that does not match the incoming data. For instance, you may have selected to view only internal sessions or data coming from a specific country. If incoming data does not match that filter then it will not be shown:
![Using global filtering for your data](images/your-first-data-filtering.png)

* **Invalid data**: Data may be rejected at the server if it 

* **No data sent**: The monitor in your application may not be submitting data to the Telerik Analytics server. In that case it is no wonder that you no data is received. Please refer to this [troubleshooting guide]({{slug:integration-troubleshooting-introduction}}) for guidance.


## Inspecting incoming session data

Using the Analytics Client you can even inspect incoming data sessions in details and see precisely what is coming in, even delving into the specific statistics data that is reported in each session - feature tracking, exceptions, etc. The [live report]({{slug:client-reports-live}}) will show you that:

![Viweing specific live incoming data sessions](images/your-first-data-live-report.png)


## See Also
[Troubleshooting]({{slug:integration-troubleshooting-introduction}})
[The Analytics Client]({{slug:client-introduction}})
[Filtering]({{slug:client-filtering-introduction}})