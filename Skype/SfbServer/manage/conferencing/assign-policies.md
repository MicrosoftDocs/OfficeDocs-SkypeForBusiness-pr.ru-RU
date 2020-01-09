---
title: Назначение политик конференц-связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Сводка: Научитесь назначать политики конференций в Skype для бизнеса Server.'
ms.openlocfilehash: f5e88e14c9516785cb3c45b5682bac13865b20ae
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991914"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="f9c72-103">Назначение политик конференц-связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f9c72-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="f9c72-104">**Сводка:** Сведения о назначении политик конференц-связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f9c72-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="f9c72-105">Вы можете назначать политики Конференции пользователям с помощью командной консоли Skype для бизнеса Server и командлета **Grant-ксконференЦингполици** .</span><span class="sxs-lookup"><span data-stu-id="f9c72-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f9c72-106">Назначение политик конференц-связи с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f9c72-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f9c72-107">В примере ниже клиентская политика SalesConferencingPolicy назначается пользователю с идентификатором "Ken Myer".</span><span class="sxs-lookup"><span data-stu-id="f9c72-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="f9c72-p101">В следующем примере политика конференций FinanceConferencingPolicy назначается всем пользователям, имеющим учетные записи в подразделении Finance (Финансы). Чтобы назначить одну политику всем пользователям в указанном подразделении, сначала вызывается командлет Get-CsUser, который извлекает все учетные записи в этом подразделении. После извлечения учетных записей пользователей они передаются командлету Grant-CsConferencingPolicy, который назначает политику FinanceConferencingPolicy каждому элементу в коллекции.</span><span class="sxs-lookup"><span data-stu-id="f9c72-p101">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit. To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU. After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="f9c72-111">Дополнительные сведения, в том числе полный синтаксис и список параметров, приведены в разделе [Grant-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f9c72-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

