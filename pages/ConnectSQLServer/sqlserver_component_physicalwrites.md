---
title: ﻿Physical Writes
last_updated: July 29, 2016
summary: "This flow represents data/index pages written to disk."
sidebar: c_sqlserver_sidebar
permalink: sqlserver_component_physicalwrites.html
id: flwSyncWrites
folder: ConnectSQLServer
---


Normally SQL users don't have to wait for database write operations to complete.

Most modifications to database pages are made in the Buffer Cache, and, once the change has been recorded in the Log, the user can continue without having to wait for the modified pages to be written to disk.

{% include links.html %}
