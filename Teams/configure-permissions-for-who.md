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
Set_Free_Tag: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20b556395c655d5052c328416d0f5ea64aee71ec
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015839"
---
<a name="configure-permissions-for-who"></a><span data-ttu-id="8d690-103">Настройка разрешений для приложения Who</span><span class="sxs-lookup"><span data-stu-id="8d690-103">Configure permissions for Who</span></span>
=============================

<span data-ttu-id="8d690-104">Приложение Who, используемое с Microsoft Teams, позволяет задавать вопросы и находить сотрудников организации в зависимости от того, над какими проектами и вместе с кем они работают.</span><span class="sxs-lookup"><span data-stu-id="8d690-104">Users can use the Who app with Microsoft Teams to help them ask questions and find anyone in the organization based on what they're working on and who they work with.</span></span>

<span data-ttu-id="8d690-105">Чтобы использовать все возможности Who, включите следующие разрешения для участников в Microsoft Graph:</span><span class="sxs-lookup"><span data-stu-id="8d690-105">To ensure users get the most out of Who, you must turn on the following member permissions in Microsoft Graph.</span></span>

- <span data-ttu-id="8d690-106">Calendars.Read</span><span class="sxs-lookup"><span data-stu-id="8d690-106">Calendars.Read</span></span>

- <span data-ttu-id="8d690-107">Calendars.Read.Shared</span><span class="sxs-lookup"><span data-stu-id="8d690-107">Calendars.Read.Shared</span></span>

- <span data-ttu-id="8d690-108">Mail.Read</span><span class="sxs-lookup"><span data-stu-id="8d690-108">Mail.Read</span></span>

- <span data-ttu-id="8d690-109">MailboxSettings.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8d690-109">MailboxSettings.ReadWrite</span></span>

- <span data-ttu-id="8d690-110">People.Read</span><span class="sxs-lookup"><span data-stu-id="8d690-110">People.Read</span></span>

- <span data-ttu-id="8d690-111">People.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d690-111">People.Read.All</span></span>

- <span data-ttu-id="8d690-112">Sites.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d690-112">Sites.Read.All</span></span>

- <span data-ttu-id="8d690-113">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d690-113">User.Read.All</span></span>

<span data-ttu-id="8d690-114">Дополнительные сведения об управлении областями разрешений Microsoft Graph: [Permission scopes](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes) (Области разрешений).</span><span class="sxs-lookup"><span data-stu-id="8d690-114">For more information about how to manage Microsoft Graph permission scopes, see [Permission scopes](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes).</span></span>
 
<span data-ttu-id="8d690-115">Дополнительные сведения о разрешениях Microsoft Graph: [Справочник по разрешениям Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="8d690-115">For more information about Microsoft Graph permissions, see [Microsoft Graph permissions reference](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span>