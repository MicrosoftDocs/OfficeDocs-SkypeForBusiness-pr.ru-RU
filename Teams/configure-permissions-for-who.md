---
title: "Настройка разрешений для приложения Who"
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "Практическое руководство по развертыванию функций облачной голосовой связи в Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5afb795e98accc1e441572d5fc56da16cb4d75
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2018
---
<a name="configure-permissions-for-who"></a>Настройка разрешений для приложения Who
=============================

Приложение Who, используемое с Microsoft Teams, позволяет задавать вопросы и находить сотрудников организации в зависимости от того, над какими проектами и вместе с кем они работают.

Чтобы использовать все возможности Who, включите следующие разрешения для участников в Microsoft Graph:

- Calendars.Read

- Calendars.Read.Shared

- Mail.Read

- MailboxSettings.ReadWrite

- People.Read

- People.Read.All

- Sites.Read.All

- User.Read.All

Дополнительные сведения об управлении областями разрешений Microsoft Graph: [Permission scopes](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes) (Области разрешений).
 
Дополнительные сведения о разрешениях Microsoft Graph: [Справочник по разрешениям Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).