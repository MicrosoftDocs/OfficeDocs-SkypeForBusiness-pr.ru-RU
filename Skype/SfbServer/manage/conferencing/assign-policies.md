---
title: Назначение политик конференц-связи в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Сводка: Узнайте, как назначение политик конференц-связи в Скайп для Business Server 2015.'
ms.openlocfilehash: 22e82ef12c8ec6dc0c9029c0c8f2861fd5578509
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568809"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="b6679-103">Назначение политик конференц-связи в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b6679-103">Assign conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b6679-104">**Сводка:** Узнайте, как назначение политик конференц-связи в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b6679-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b6679-105">Политики конференц-связи можно назначать пользователей с помощью Скайп для консоли Business Server и командлета **Grant-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="b6679-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b6679-106">Назначение политики конференц-связи с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="b6679-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b6679-107">В примере ниже клиентская политика SalesConferencingPolicy назначается пользователю с идентификатором "Ken Myer".</span><span class="sxs-lookup"><span data-stu-id="b6679-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="b6679-p101">В следующем примере политика конференций FinanceConferencingPolicy назначается всем пользователям, имеющим учетные записи в подразделении Finance (Финансы). Чтобы назначить одну политику всем пользователям в указанном подразделении, сначала вызывается командлет Get-CsUser, который извлекает все учетные записи в этом подразделении. После извлечения учетных записей пользователей они передаются командлету Grant-CsConferencingPolicy, который назначает политику FinanceConferencingPolicy каждому элементу в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b6679-p101">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit. To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU. After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="b6679-111">Дополнительные сведения, включая полный синтаксис и список параметров можно [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b6679-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

