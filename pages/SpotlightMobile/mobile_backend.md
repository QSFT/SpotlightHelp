---
title: Backend Deployment of Spotlight Mobile
summary: "Spotlight Mobile connects to the components of a Spotlight Enterprise deployment."
sidebar: p_mobile_sidebar
permalink: mobile_backend.html
folder: SpotlightMobile
---



## Interfaces to Spotlight Enterprise

### Spotlight Client

Use a Spotlight Client to configure Spotlight. For example, a Spotlight Client is used to add and remove the connections monitored through Spotlight. A Spotlight Client is used to configure alarms, to configure the collection schedules and other operational configurations of the deployment. This cannot be done in Spotlight Mobile.

The Spotlight Client is a core component of Spotlight Enterprise.

## Data Collection and Storage

### Spotlight Diagnostic Server and the Spotlight Cloud

The Spotlight Diagnostic Server is at the core of the Spotlight Enterprise architecture. All data from monitored connections passes through the Spotlight Diagnostic Server.

The Spotlight Diagnostic Server is a Windows service. It runs under Windows credentials. To use Spotlight Mobile, the Spotlight Diagnostic Server must have access to the Internet and must be configured to upload to the Spotlight Cloud. Ensure:

* The Spotlight Diagnostic Server is configured to upload data to the Spotlight Cloud.
* The Spotlight Diagnostic Server has access to the Internet.
* Port TCP 443 on the Spotlight Diagnostic Server is open.

### Spotlight Playback Database

Recent history is stored in the Playback Database. There is one Playback Database per Spotlight Diagnostic Server. Spotlight Mobile views data from the Playback Database from the Playback display. Spotlight Mobile cannot be used to configure the Playback Database. Use a Spotlight Client to configure the Playback Database.

### Spotlight Statistics Repository

Long term history for reporting and trending is stored in the Spotlight Statistics Repository. The Spotlight Statistics Repository is inaccessible to Spotlight Mobile. Use a Spotlight Client to access the Spotlight Statistics Repository. Note that deployment of the Spotlight Statistics Repository is optional per Spotlight Diagnostic Server.



{% include links.html %}