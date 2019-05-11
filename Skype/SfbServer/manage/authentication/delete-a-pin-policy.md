---
title: Удаление политики ПИН-код в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Сводка: Удаление пользователя телефонных конференций ПИН-кода для Скайп для Business Server.'
ms.openlocfilehash: b281716c2e0560936ea2f94b773c8191f3e8987e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919649"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="c6a62-103">Удаление политики ПИН-код в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c6a62-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="c6a62-104">**Сводка:** Удаление пользователя телефонных конференций ПИН-кода для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="c6a62-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="c6a62-105">Чтобы удалить политику персональных идентификационных номеров (политику ПИН-кодов), выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="c6a62-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6a62-106">Глобальную политику ПИН-кодов удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="c6a62-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="c6a62-107">Удаление политики ПИН-код в Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="c6a62-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c6a62-108">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server .</span><span class="sxs-lookup"><span data-stu-id="c6a62-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c6a62-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c6a62-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c6a62-110">В левой панели навигации последовательно выберите пункты **Безопасность** и **Политика ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="c6a62-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="c6a62-111">На странице **Политика ПИН-кода** в поле поиска полностью или частично введите имя политики, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="c6a62-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="c6a62-112">В списке политик выберите необходимую политику, щелкните **Правка**, затем выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c6a62-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="c6a62-113">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c6a62-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c6a62-114">Удаление политик ПИН-кода с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6a62-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c6a62-115">Политики ПИН-код можно удалить с помощью Windows PowerShell и командлет Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="c6a62-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="c6a62-116">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6a62-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c6a62-117">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="c6a62-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c6a62-118">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="c6a62-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="c6a62-119">Удаление определенной политики ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="c6a62-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="c6a62-120">Эта команда удаляет политику ПИН-кода с идентификатором RedmondPinPolicy:</span><span class="sxs-lookup"><span data-stu-id="c6a62-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="c6a62-121">Порядок применения всех политик ПИН-кода, применяемых на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="c6a62-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="c6a62-122">Эта команда удаляет все политики ПИН-кода, настроенные в области действия сайта:</span><span class="sxs-lookup"><span data-stu-id="c6a62-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="c6a62-123">Удаление всех политик ПИН-кодов, позволяющих использовать общие шаблоны</span><span class="sxs-lookup"><span data-stu-id="c6a62-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="c6a62-124">А эта команда удаляет все политики ПИН-кодов, допускающие использование общих шаблонов:</span><span class="sxs-lookup"><span data-stu-id="c6a62-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="c6a62-125">Для получения дополнительных сведений см раздел справки для командлета [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c6a62-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  

