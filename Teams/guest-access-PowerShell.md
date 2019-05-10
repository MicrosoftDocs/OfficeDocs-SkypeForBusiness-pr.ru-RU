---
title: Использование PowerShell для управления гостевым доступом в команде
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
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
ms.openlocfilehash: 7ca05e48d28986a944debe150d5dbf25129ca73c
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827671"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="ee046-103">Использование PowerShell для управления гостевым доступом в команде</span><span class="sxs-lookup"><span data-stu-id="ee046-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="ee046-104">Кроме Центра администрирования Office 365 и портала Azure Active Directory, для управления гостевым доступом вы можете использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee046-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="ee046-105">PowerShell предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="ee046-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="ee046-106">Разрешение или запрет гостевого доступа для всех команд и групп Office 365</span><span class="sxs-lookup"><span data-stu-id="ee046-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
- <span data-ttu-id="ee046-107">Разрешение добавления гостей во все команды и группы Office 365</span><span class="sxs-lookup"><span data-stu-id="ee046-107">Allow guests to be added to all teams and Office 365 groups</span></span>
      
- <span data-ttu-id="ee046-108">Разрешение или блокировка гостевых пользователей из определенной команды или группы Office 365</span><span class="sxs-lookup"><span data-stu-id="ee046-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
<span data-ttu-id="ee046-109">Для получения дополнительных сведений обратитесь к разделу «Использование PowerShell для управления доступом Гость» на вкладке Управление [гостевого доступа в Office 365 групп](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="ee046-109">For details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="ee046-110">Вы также можете использовать PowerShell, чтобы разрешить или заблокировать гостевого пользователя по его домену.</span><span class="sxs-lookup"><span data-stu-id="ee046-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="ee046-111">Например, предположим, что ваша организация (Contoso) сотрудничает с другой организацией (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="ee046-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="ee046-112">Вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавлять этих гостей в свои группы.</span><span class="sxs-lookup"><span data-stu-id="ee046-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="ee046-113">Дополнительные сведения см. в статье [Разрешение и блокировка гостевого доступа к группам Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="ee046-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="ee046-114">Если требуется заблокировать гости в группах и по-прежнему требуется разрешить им доступ к сайтам SharePoint, можно использовать командлеты Windows Azure Active Directory Powershell отключить параметр AllowGuestsToAccessGroups на объекте компании при условии, что внешний общий доступ для включено Сайты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ee046-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="ee046-115">Доступ в качестве гостя и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="ee046-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
