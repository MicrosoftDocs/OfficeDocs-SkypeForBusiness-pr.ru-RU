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
<a name="configure-permissions-for-who"></a><span data-ttu-id="9521e-103">Настройка разрешений для приложения Who</span><span class="sxs-lookup"><span data-stu-id="9521e-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="9521e-104">Приложение Who, используемое с Microsoft Teams, позволяет задавать вопросы и находить сотрудников организации в зависимости от того, над какими проектами и вместе с кем они работают.</span><span class="sxs-lookup"><span data-stu-id="9521e-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="9521e-105">Чтобы использовать все возможности Who, включите следующие разрешения для участников в Microsoft Graph:</span><span class="sxs-lookup"><span data-stu-id="9521e-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="9521e-106">Calendars.Read</span><span class="sxs-lookup"><span data-stu-id="9521e-106">Calendars.Read</span></span>

- <span data-ttu-id="9521e-107">Calendars.Read.Shared</span><span class="sxs-lookup"><span data-stu-id="9521e-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="9521e-108">Mail.Read</span><span class="sxs-lookup"><span data-stu-id="9521e-108">Mail.Read</span></span>

- <span data-ttu-id="9521e-109">MailboxSettings.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9521e-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="9521e-110">People.Read</span><span class="sxs-lookup"><span data-stu-id="9521e-110">People.Read</span></span>

- <span data-ttu-id="9521e-111">People.Read.All</span><span class="sxs-lookup"><span data-stu-id="9521e-111">People.Read.All</span></span>

- <span data-ttu-id="9521e-112">Sites.Read.All</span><span class="sxs-lookup"><span data-stu-id="9521e-112">Sites.Read.All</span></span>

- <span data-ttu-id="9521e-113">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="9521e-113">User.Read.All</span></span>

<span data-ttu-id="9521e-114">Дополнительные сведения об управлении областями разрешений Microsoft Graph: [Permission scopes](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes) (Области разрешений).</span><span class="sxs-lookup"><span data-stu-id="9521e-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/en-us/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="9521e-115">Дополнительные сведения о разрешениях Microsoft Graph: [Справочник по разрешениям Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="9521e-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).</span></span>