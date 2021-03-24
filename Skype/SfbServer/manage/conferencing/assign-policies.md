---
title: Назначение политик conferencing в Skype для бизнеса Server
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
description: Сводка. Сведения о назначении политик конференций в Skype для бизнеса Server.
ms.openlocfilehash: 61082a9189b085c852e7593207fc86dcc6509139
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099165"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="7f612-103">Назначение политик conferencing в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7f612-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="7f612-104">**Сводка:** Узнайте, как назначить политики конференциинга в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7f612-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="7f612-105">Политики конференции можно назначить пользователям с помощью команды Управления Skype для бизнес-серверов и команды **Grant-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="7f612-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7f612-106">Назначение политик conferencing с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="7f612-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="7f612-107">В следующем примере политика SalesConferencingPolicy назначена пользователю с удостоверением "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="7f612-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="7f612-108">В следующем примере политика conferencing FinanceConferencingPolicy назначена всем пользователям, у которых есть учетные записи в организационном подразделении Finance.</span><span class="sxs-lookup"><span data-stu-id="7f612-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="7f612-109">Чтобы назначить одну политику всем пользователям в указанном подразделении, сначала вызывается командлет Get-CsUser, который извлекает все учетные записи в этом подразделении.</span><span class="sxs-lookup"><span data-stu-id="7f612-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="7f612-110">После получения учетных записей пользователей эта информация передается в Grant-CsConferencingPolicy, который назначает политику FinanceConferencingPolicy каждому пользователю в коллекции:</span><span class="sxs-lookup"><span data-stu-id="7f612-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="7f612-111">Дополнительные сведения, включая полный синтаксис и список параметров, см. в [обзоре Grant-CsConferencingPolicy.](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7f612-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
