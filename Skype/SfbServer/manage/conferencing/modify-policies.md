---
title: Изменение политики конференц-связи в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Сводка: Узнайте, как для изменения политики конференц-связи в Скайп для Business Server.'
ms.openlocfilehash: 5883af04310f671e536460dbd466ce583cb52ebd
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970242"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="ab116-103">Изменение политики конференц-связи в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="ab116-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="ab116-104">**Сводка:** Узнайте, как для изменения политики конференц-связи в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="ab116-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="ab116-105">Политики конференц-связи можно изменить с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="ab116-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ab116-106">Изменение политик конференц-связи с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="ab116-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ab116-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ab116-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="ab116-108">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="ab116-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ab116-109">На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="ab116-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="ab116-110">В списке политик конференций выберите политику, которую нужно изменить, нажмите кнопку **Изменить**, а затем **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="ab116-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ab116-111">В области **Изменение конфигурации собрания** измените любые параметры политики за исключением имени, которое нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="ab116-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="ab116-112">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="ab116-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ab116-113">Изменение политик конференц-связи с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="ab116-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ab116-114">Для изменения политики конференц-связи, используйте командлет **Set-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="ab116-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="ab116-115">В следующем примере показано изменение значения свойства политики конференц-связи SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="ab116-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="ab116-116">Команда присваивает свойству AllowConferenceRecording значение False:</span><span class="sxs-lookup"><span data-stu-id="ab116-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="ab116-117">Дополнительные сведения, включая полный синтаксис и список параметров [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)см.</span><span class="sxs-lookup"><span data-stu-id="ab116-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

