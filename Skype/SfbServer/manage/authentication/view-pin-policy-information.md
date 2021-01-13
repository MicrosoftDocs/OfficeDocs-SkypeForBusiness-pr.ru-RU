---
title: Просмотр сведений о политике ПИН-кодов в Skype для бизнеса Server
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
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: Сводка. Просмотр сведений о политике ПИН-кодов для Skype для бизнеса Server.
ms.openlocfilehash: 4c223d5736df7f5f8ee1dbee11401a9fef2237cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806529"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="a83ec-103">Просмотр сведений о политике ПИН-кодов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a83ec-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="a83ec-104">**Сводка:** Просмотр сведений о политике ПИН-кодов для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a83ec-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="a83ec-105">Вкладку "Политика ПИН-кодов" можно использовать для просмотра проверки подлинности пользователей, подключающихся к Skype для бизнеса с ПОМОЩЬЮ IP-телефонов. </span><span class="sxs-lookup"><span data-stu-id="a83ec-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="a83ec-106">Чтобы использовать проверку подлинности на основе ПИН-кодов, необходимо установить флажок **Enable PIN Authentication (Включить проверку подлинности на основе ПИН-кодов)** в параметрах веб-службы.</span><span class="sxs-lookup"><span data-stu-id="a83ec-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="a83ec-107">Чтобы изменить политику ПИН-кода на уровне пользователя или сайта, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a83ec-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a83ec-108">Просмотр сведений о политике ПИН-кодов на панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a83ec-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a83ec-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a83ec-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a83ec-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a83ec-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a83ec-111">На панели навигации слева выберите **Безопасность** и нажмите **Политика ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="a83ec-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="a83ec-112">На странице **Политика ПИН-кода** щелкните политику, выберите **Изменить** и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="a83ec-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a83ec-113">Просмотр политик ПИН-кодов с помощью Windows PowerShell-кодов</span><span class="sxs-lookup"><span data-stu-id="a83ec-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a83ec-114">Политики ПИН-кодов также можно просмотреть с помощью Windows PowerShell и Get-CsPinPolicy управления.</span><span class="sxs-lookup"><span data-stu-id="a83ec-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="a83ec-115">Этот cmdlet можно запустить в оболочке управления Skype для бизнеса Server или в удаленном сеансе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a83ec-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a83ec-116">Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell".</span><span class="sxs-lookup"><span data-stu-id="a83ec-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a83ec-117">В Skype для бизнеса Server этот процесс тот же.</span><span class="sxs-lookup"><span data-stu-id="a83ec-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="a83ec-118">Просмотр политик ПИН-кодов</span><span class="sxs-lookup"><span data-stu-id="a83ec-118">To view PIN policies</span></span>

<span data-ttu-id="a83ec-119">Чтобы просмотреть сведения обо всех политиках ПИН-кодов, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="a83ec-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy
  ```

<span data-ttu-id="a83ec-120">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="a83ec-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="a83ec-121">Дополнительные сведения см. в разделе справки по [cmdlet Get-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a83ec-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a83ec-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a83ec-122">See also</span></span>

[<span data-ttu-id="a83ec-123">Создание новой политики ПИН-кодов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a83ec-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
