---
title: Просмотр сведений о политике ПИН-код в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Сводка: Просмотр сведений политики ПИН-кода пользователя для Скайп для Business Server.'
ms.openlocfilehash: 37bb66dfb3d899057d1679c2438fd7e695349629
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919677"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="89ec6-103">Просмотр сведений о политике ПИН-код в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="89ec6-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="89ec6-104">**Сводка:** Просмотр сведений политики ПИН-кода пользователя для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="89ec6-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="89ec6-105">Для представления персонального идентификационного номера (ПИН-кода) проверки подлинности пользователей, которым подключаются к Скайп для бизнеса с IP-телефонов вкладка **Политики ПИН-кода** .</span><span class="sxs-lookup"><span data-stu-id="89ec6-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="89ec6-106">Чтобы использовать проверку подлинности по ПИН-коду, необходимо установить флажок **Разрешить проверку подлинности на основе ПИН-кода** в настройках веб-службы.</span><span class="sxs-lookup"><span data-stu-id="89ec6-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="89ec6-107">Выполните следующие действия, чтобы изменить политику ПИН-кода на уровне пользователя или узла.</span><span class="sxs-lookup"><span data-stu-id="89ec6-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="89ec6-108">Для просмотра сведений о политике ПИН-код в Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="89ec6-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="89ec6-109">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server .</span><span class="sxs-lookup"><span data-stu-id="89ec6-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="89ec6-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="89ec6-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="89ec6-111">В левой панели навигации последовательно выберите пункты **Безопасность** и **Политика ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="89ec6-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="89ec6-112">На странице **Политика ПИН-кода** выберите политику, нажмите кнопку **Правка**, а затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="89ec6-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="89ec6-113">Просмотр политик ПИН-кода с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89ec6-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="89ec6-114">Можно также просмотреть политики ПИН-кода с помощью командлета Get-CsPinPolicy и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89ec6-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="89ec6-115">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89ec6-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="89ec6-116">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="89ec6-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="89ec6-117">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="89ec6-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="89ec6-118">Просмотр политик ПИН-кодов</span><span class="sxs-lookup"><span data-stu-id="89ec6-118">To view PIN policies</span></span>

<span data-ttu-id="89ec6-119">Чтобы просмотреть сведения обо всех политиках ПИН-кода, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="89ec6-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsPinPolicy
  ```

<span data-ttu-id="89ec6-120">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="89ec6-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="89ec6-121">Для получения дополнительных сведений см раздел справки для командлета [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="89ec6-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="89ec6-122">См. также</span><span class="sxs-lookup"><span data-stu-id="89ec6-122">See also</span></span>

[<span data-ttu-id="89ec6-123">Создание новой политики ПИН-код в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="89ec6-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
