---
title: Просмотр сведений о политике ПИН-кода в Skype для бизнеса Server
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
description: Сводка. Просмотр сведений о ПИН-коде пользователя для Skype для бизнес-сервера.
ms.openlocfilehash: 80383ce7e78ba8806119121f8c27c6e469363003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119538"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="953b2-103">Просмотр сведений о политике ПИН-кода в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="953b2-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="953b2-104">**Сводка:** Просмотр сведений о ПИН-коде пользователя для Skype для бизнес-сервера.</span><span class="sxs-lookup"><span data-stu-id="953b2-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="953b2-105">Вы можете использовать **вкладку PIN-политики** для просмотра проверки подлинности личного идентификационного номера (ПИН-кода) пользователей, подключающихся к Skype для бизнеса с ПОМОЩЬЮ IP-телефонов.</span><span class="sxs-lookup"><span data-stu-id="953b2-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="953b2-106">Чтобы использовать проверку подлинности на основе ПИН-кодов, необходимо установить флажок **Enable PIN Authentication (Включить проверку подлинности на основе ПИН-кодов)** в параметрах веб-службы.</span><span class="sxs-lookup"><span data-stu-id="953b2-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="953b2-107">Чтобы изменить политику ПИН-кода на уровне пользователя или сайта, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="953b2-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="953b2-108">Просмотр сведений о политике ПИН-кода в панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="953b2-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="953b2-109">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="953b2-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="953b2-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="953b2-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="953b2-111">На панели навигации слева выберите **Безопасность** и нажмите **Политика ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="953b2-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="953b2-112">На странице **Политика ПИН-кода** щелкните политику, выберите **Изменить** и нажмите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="953b2-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="953b2-113">Просмотр политик ПИН-кода с помощью Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="953b2-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="953b2-114">Политики ПИН-кода можно также просматривать с помощью Windows PowerShell и Get-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="953b2-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="953b2-115">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="953b2-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="953b2-116">Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell".</span><span class="sxs-lookup"><span data-stu-id="953b2-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="953b2-117">В Skype для бизнеса Server этот процесс является одинаковым.</span><span class="sxs-lookup"><span data-stu-id="953b2-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="953b2-118">Просмотр политик PIN-кода</span><span class="sxs-lookup"><span data-stu-id="953b2-118">To view PIN policies</span></span>

<span data-ttu-id="953b2-119">Чтобы просмотреть сведения обо всех политиках ПИН-кода, введите следующую команду в командной оболочке Skype для бизнес-серверов и нажмите кнопку ENTER:</span><span class="sxs-lookup"><span data-stu-id="953b2-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy
  ```

<span data-ttu-id="953b2-120">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="953b2-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="953b2-121">Дополнительные сведения см. в разделе Справка для [cmdlet Get-CsPinPolicy.](/powershell/module/skype/get-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="953b2-121">For more information, see the help topic for the [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="953b2-122">См. также</span><span class="sxs-lookup"><span data-stu-id="953b2-122">See also</span></span>

[<span data-ttu-id="953b2-123">Создание новой политики ПИН-кода в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="953b2-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)