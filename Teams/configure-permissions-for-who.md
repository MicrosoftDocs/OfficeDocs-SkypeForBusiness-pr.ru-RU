---
title: Настройка разрешений для приложения Who
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Практическое руководство по развертыванию функций облачной голосовой связи в Microsoft Teams.
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc8fe9a21cdfa4d1df0bf3f11631d103a13fe94b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860217"
---
<a name="configure-permissions-for-who"></a><span data-ttu-id="e2a57-103">Настройка разрешений для приложения Who</span><span class="sxs-lookup"><span data-stu-id="e2a57-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="e2a57-104">Приложение Who, используемое с Microsoft Teams, позволяет задавать вопросы и находить сотрудников организации в зависимости от того, над какими проектами и вместе с кем они работают.</span><span class="sxs-lookup"><span data-stu-id="e2a57-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="e2a57-105">Чтобы использовать все возможности Who, включите следующие разрешения для участников в Microsoft Graph:</span><span class="sxs-lookup"><span data-stu-id="e2a57-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="e2a57-106">Calendars.Read</span><span class="sxs-lookup"><span data-stu-id="e2a57-106">Calendars.Read</span></span>

- <span data-ttu-id="e2a57-107">Calendars.Read.Shared</span><span class="sxs-lookup"><span data-stu-id="e2a57-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="e2a57-108">Mail.Read</span><span class="sxs-lookup"><span data-stu-id="e2a57-108">Mail.Read</span></span>

- <span data-ttu-id="e2a57-109">MailboxSettings.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e2a57-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="e2a57-110">People.Read</span><span class="sxs-lookup"><span data-stu-id="e2a57-110">People.Read</span></span>

- <span data-ttu-id="e2a57-111">People.Read.All</span><span class="sxs-lookup"><span data-stu-id="e2a57-111">People.Read.All</span></span>

- <span data-ttu-id="e2a57-112">Sites.Read.All</span><span class="sxs-lookup"><span data-stu-id="e2a57-112">Sites.Read.All</span></span>

- <span data-ttu-id="e2a57-113">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="e2a57-113">User.Read.All</span></span>

<span data-ttu-id="e2a57-114">Дополнительные сведения об управлении областями разрешений Microsoft Graph: [Permission scopes](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes) (Области разрешений).</span><span class="sxs-lookup"><span data-stu-id="e2a57-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="e2a57-115">Дополнительные сведения о разрешениях Microsoft Graph: [Справочник по разрешениям Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="e2a57-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span>