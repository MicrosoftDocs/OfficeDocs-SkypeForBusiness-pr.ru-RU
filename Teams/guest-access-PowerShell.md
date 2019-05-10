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
ms.openlocfilehash: 0efb3a8054008d179b9d2e7e674b3482fe62a32c
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865092"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="4e965-103">Использование PowerShell для управления гостевым доступом в команде</span><span class="sxs-lookup"><span data-stu-id="4e965-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="4e965-104">С помощью центра администрирования Microsoft 365 и Azure Active Directory портала, можно использовать Windows PowerShell для управления доступом гостя.</span><span class="sxs-lookup"><span data-stu-id="4e965-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="4e965-105">PowerShell предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="4e965-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="4e965-106">Разрешение или запрет гостевого доступа для всех команд и групп Office 365</span><span class="sxs-lookup"><span data-stu-id="4e965-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
- <span data-ttu-id="4e965-107">Разрешение добавления гостей во все команды и группы Office 365</span><span class="sxs-lookup"><span data-stu-id="4e965-107">Allow guests to be added to all teams and Office 365 groups</span></span>
      
- <span data-ttu-id="4e965-108">Разрешение или блокировка гостевых пользователей из определенной команды или группы Office 365</span><span class="sxs-lookup"><span data-stu-id="4e965-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
<span data-ttu-id="4e965-109">Для получения дополнительных сведений обратитесь к разделу «Использование PowerShell для управления доступом Гость» на вкладке Управление [гостевого доступа в Office 365 групп](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="4e965-109">For details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="4e965-110">Вы также можете использовать PowerShell, чтобы разрешить или заблокировать гостевого пользователя по его домену.</span><span class="sxs-lookup"><span data-stu-id="4e965-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="4e965-111">Например, предположим, что ваша организация (Contoso) сотрудничает с другой организацией (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="4e965-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="4e965-112">Вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавлять этих гостей в свои группы.</span><span class="sxs-lookup"><span data-stu-id="4e965-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="4e965-113">Дополнительные сведения см. в статье [Разрешение и блокировка гостевого доступа к группам Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="4e965-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="4e965-114">Если требуется заблокировать гости в группах и по-прежнему требуется разрешить им доступ к сайтам SharePoint, можно использовать командлеты Windows Azure Active Directory Powershell отключить параметр AllowGuestsToAccessGroups на объекте компании при условии, что внешний общий доступ для включено Сайты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4e965-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="4e965-115">Доступ в качестве гостя и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="4e965-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
