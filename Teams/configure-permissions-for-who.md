---
title: "Настройка разрешений для приложения Who"
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "Практическое руководство по развертыванию функций облачной голосовой связи в Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 629a732b178f6702f5ba308c6d0effe069019091
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
<a name="configure-permissions-for-who"></a><span data-ttu-id="9aca3-103">Настройка разрешений для приложения Who</span><span class="sxs-lookup"><span data-stu-id="9aca3-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="9aca3-104">Приложение Who, используемое с Microsoft Teams, позволяет задавать вопросы и находить сотрудников организации в зависимости от того, над какими проектами и вместе с кем они работают.</span><span class="sxs-lookup"><span data-stu-id="9aca3-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="9aca3-105">Чтобы использовать все возможности Who, включите следующие разрешения для участников в Microsoft Graph:</span><span class="sxs-lookup"><span data-stu-id="9aca3-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="9aca3-106">Calendars.Read</span><span class="sxs-lookup"><span data-stu-id="9aca3-106">Calendars.Read</span></span>

- <span data-ttu-id="9aca3-107">Calendars.Read.Shared</span><span class="sxs-lookup"><span data-stu-id="9aca3-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="9aca3-108">Mail.Read</span><span class="sxs-lookup"><span data-stu-id="9aca3-108">Mail.Read</span></span>

- <span data-ttu-id="9aca3-109">MailboxSettings.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9aca3-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="9aca3-110">People.Read</span><span class="sxs-lookup"><span data-stu-id="9aca3-110">People.Read</span></span>

- <span data-ttu-id="9aca3-111">People.Read.All</span><span class="sxs-lookup"><span data-stu-id="9aca3-111">People.Read.All</span></span>

- <span data-ttu-id="9aca3-112">Sites.Read.All</span><span class="sxs-lookup"><span data-stu-id="9aca3-112">Sites.Read.All</span></span>

- <span data-ttu-id="9aca3-113">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="9aca3-113">User.Read.All</span></span>

<span data-ttu-id="9aca3-114">Дополнительные сведения об управлении областями разрешений Microsoft Graph: [Permission scopes](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes) (Области разрешений).</span><span class="sxs-lookup"><span data-stu-id="9aca3-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="9aca3-115">Дополнительные сведения о разрешениях Microsoft Graph: [Справочник по разрешениям Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="9aca3-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span>