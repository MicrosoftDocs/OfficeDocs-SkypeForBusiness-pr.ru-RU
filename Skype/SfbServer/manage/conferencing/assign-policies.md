---
title: Назначение политик для видеоконференций в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: Сводка. Узнайте, как назначать политики в Skype для бизнеса Server.
ms.openlocfilehash: d13710d2cc4f6edf1cee16cbc9aa77799ceec8a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806479"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="bfba7-103">Назначение политик для видеоконференций в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bfba7-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="bfba7-104">**Сводка:** Learn how to assign conferencing policies in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bfba7-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="bfba7-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bfba7-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="bfba7-106">Assign conferencing policies by using Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="bfba7-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="bfba7-107">В следующем примере политика SalesConferencingPolicy назначена пользователю с удостоверением "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="bfba7-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="bfba7-108">В следующем примере политика conferencing FinanceConferencingPolicy назначена всем пользователям, у которых есть учетные записи в финансовом подразделении.</span><span class="sxs-lookup"><span data-stu-id="bfba7-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="bfba7-109">Чтобы назначить одну политику всем пользователям в указанном подразделении, сначала вызывается командлет Get-CsUser, который извлекает все учетные записи в этом подразделении.</span><span class="sxs-lookup"><span data-stu-id="bfba7-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="bfba7-110">После извлечения учетных записей пользователей эта информация передается в Grant-CsConferencingPolicy, который назначает политику FinanceConferencingPolicy каждому пользователю в коллекции:</span><span class="sxs-lookup"><span data-stu-id="bfba7-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="bfba7-111">Дополнительные сведения, включая полный синтаксис и список параметров, см. в поле [Grant-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="bfba7-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

