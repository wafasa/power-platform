---
title: "Release notes and latest version of the CoE starter kit Core components | MicrosoftDocs"
description: "Release notes and latest version of the CoE Starter Kit."
author: manuelap-msft
manager: devkeydet
ms.service: power-platform
ms.component: pa-admin
ms.topic: conceptual
ms.date: 04/10/2020
ms.author: mapichle
ms.reviewer: jimholtz
search.audienceType: 
  - admin
search.app: 
  - D365CE
  - PowerApps
  - Powerplatform
---

# Released version Core Components 1.52

## Introduction

Version 1.52 for the CoE Starter Kit Core Components is now available. This article describes the updates, including the new features and the fixes to existing functionality, included in this release. This version was first made available on July 8, 2020.

## Power Virtual Agents inventory

This version introduces inventory information for Power Virtual Agents. A new Admin | Sync Flows v2 (Chatbots) has been added to sync Power Virtual Agent information to the new Chatbot, Chatbot Component and Chatbot Component Flow entities. The Power Platform Admin View has been updated to include Chatbot information, and the CoE Starter Kit Power BI Dashboard has been updated to include a Virtual Agents overview and Virtual Agents detail page.

Information available for chatbots:

- ID
- Name
- Environment
- Created by/on
- Modified by/on
- State (Published,...)
- Last launched
- Number of sessions
- Number of components, plus component details
- Number of flows

![Power Platform Admin View - View who an app is shared with](../media/pb-pva.png "Power Platform Admin View - View who an app is shared with")

## Power Apps (canvas apps) "shared with" information

This version introduces new entities that hold information on who a canvas app is shared with. A new Admin | Sync Flow v2 (Power Apps User Shared With) has been added to retrieve role assignments per app and store that information in the Power Platform User and Power Platform User Role entities. The Power Platform User Role entity has a 1:n relationship with both Power Platform User and PowerApps App, as in one user has one role (owner, edit, view) per app, and one role is tied to one app.
If an app is shared with an Azure AD Group, information on group size is retrieved via the Azure AD connector and stored in the entity.

Information available for who an app is shared with:

- User Name
- Role (Owner, Editor, Viewer)
- Type (User, Group, Tenant)
- Group Size

The Power Platform Admin View has been updated to show this information on the PowerApps App form:

![Power Platform Admin View - View who an app is shared with](../media/coe-mda2.png "Power Platform Admin View - View who an app is shared with")

## Set App Permissions and Set Flow Permissions

This version renames the Set New App Owner app to Set App Permissions, and introduces the capability to search by environment, by maker and by orphaned app. Additionally, it is now possible to change app owners, add new editors and viewers as well as remove app permissions with this app.

This version also introduces a new Set Flow Permissions app that allows admins to search by environment, by maker and by orphaned flows and add new users to those flows.

## Admin | Sync Template v2 (Flow Action Details)

This flow contained a bug due to which new actions and triggers were not captured. This has been fixed in this version.

## Admin | Sync Template v2 (Check Deleted)

This flow runs weekly, and compares CoE to the tenant to determine if any objects were deleted since last run. Either just marks them as deleted.

