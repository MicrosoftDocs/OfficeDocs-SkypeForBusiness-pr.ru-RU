---
title: Использование PowerShell для управления гостевым доступом в команде
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Используйте PowerShell, чтобы разрешить или блокировать гостевой доступ к командам в Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b429d4e2411e697c4e3357ebd7b5fc66ab27376
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "35220888"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="f2604-103">Использование PowerShell для управления гостевым доступом в команде</span><span class="sxs-lookup"><span data-stu-id="f2604-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="f2604-104">Кроме того, чтобы использовать центр администрирования Microsoft 365 и портал Azure Active Directory (Azure AD), вы можете управлять гостевым доступом с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2604-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="f2604-105">PowerShell предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="f2604-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="f2604-106">Разрешение и блокирование гостевого доступа ко всем группам и Office 365</span><span class="sxs-lookup"><span data-stu-id="f2604-106">Allow or block guest access to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="f2604-107">Разрешение на добавление гостей ко всем группам и Office 365</span><span class="sxs-lookup"><span data-stu-id="f2604-107">Allow guests to be added to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="f2604-108">Разрешение или блокировка гостевых пользователей из определенной команды или группы Office 365</span><span class="sxs-lookup"><span data-stu-id="f2604-108">Allow or block guest users from a specific team or Office 365 group</span></span>

<span data-ttu-id="f2604-109">Дополнительные сведения можно найти в разделе "Использование PowerShell для управления гостевым доступом" на панели [управления доступом гостей в группах Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span><span class="sxs-lookup"><span data-stu-id="f2604-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>
  
<span data-ttu-id="f2604-110">Вы также можете использовать PowerShell, чтобы разрешить или заблокировать гостевого пользователя по его домену.</span><span class="sxs-lookup"><span data-stu-id="f2604-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="f2604-111">Например, предположим, что ваша организация (Contoso) сотрудничает с другой организацией (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="f2604-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="f2604-112">Вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавлять этих гостей в свои группы.</span><span class="sxs-lookup"><span data-stu-id="f2604-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="f2604-113">Дополнительные сведения можно найти [в разделе разрешение и блокирование гостевого доступа для групп Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="f2604-113">For more information, see [Allow/Block guest access to Office 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="f2604-114">Если вы хотите заблокировать гостей в Teams и по-прежнему хотите разрешить им доступ к сайтам SharePoint, можно использовать командлеты Azure AD PowerShell, чтобы отключить параметр Алловгуестстоакцессграупс для объекта Company, предполагая, что внешний общий доступ включен для сайтов SharePoint. .</span><span class="sxs-lookup"><span data-stu-id="f2604-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="f2604-115">Гостевой доступ и внешний доступ</span><span class="sxs-lookup"><span data-stu-id="f2604-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
