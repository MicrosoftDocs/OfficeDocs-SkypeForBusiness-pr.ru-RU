---
title: Просмотр сведений о политике контактов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Сводка: Просмотр сведений о политике PIN-кода пользователя в Skype для бизнеса Server.'
ms.openlocfilehash: c61c55f97abc661558089c1d26ee4f5537fcf36b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991954"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="ff8ea-103">Просмотр сведений о политике контактов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ff8ea-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="ff8ea-104">**Сводка:** Просмотр сведений о политике PIN-кода пользователя в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ff8ea-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="ff8ea-105">С помощью вкладки " **политика закрепления** " можно просмотреть персональный идентификационный номер (PIN) пользователей, которые подключаются к Skype для бизнеса с помощью IP-телефонов.</span><span class="sxs-lookup"><span data-stu-id="ff8ea-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="ff8ea-106">Чтобы использовать проверку подлинности по ПИН-коду, необходимо установить флажок **Разрешить проверку подлинности на основе ПИН-кода** в настройках веб-службы.</span><span class="sxs-lookup"><span data-stu-id="ff8ea-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="ff8ea-107">Выполните следующие действия, чтобы изменить политику ПИН-кода на уровне пользователя или узла.</span><span class="sxs-lookup"><span data-stu-id="ff8ea-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="ff8ea-108">Просмотр сведений о политике закрепления на панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ff8ea-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="ff8ea-109">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="ff8ea-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="ff8ea-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ff8ea-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ff8ea-111">В левой панели навигации последовательно выберите пункты **Безопасность** и **Политика ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="ff8ea-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="ff8ea-112">На странице **Политика ПИН-кода** выберите политику, нажмите кнопку **Правка**, а затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="ff8ea-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ff8ea-113">Просмотр политик ПИН-кода с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff8ea-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ff8ea-114">Вы также можете просматривать политики ПИН с помощью Windows PowerShell и командлета Get-Кспинполици.</span><span class="sxs-lookup"><span data-stu-id="ff8ea-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="ff8ea-115">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff8ea-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ff8ea-116">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="ff8ea-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="ff8ea-117">Этот процесс одинаков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ff8ea-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="ff8ea-118">Просмотр политик ПИН-кодов</span><span class="sxs-lookup"><span data-stu-id="ff8ea-118">To view PIN policies</span></span>

<span data-ttu-id="ff8ea-119">Чтобы просмотреть сведения обо всех политиках для ПИН-кода, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="ff8ea-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy
  ```

<span data-ttu-id="ff8ea-120">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="ff8ea-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="ff8ea-121">Дополнительные сведения можно найти в разделе справки по командлету [Get-кспинполици](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="ff8ea-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff8ea-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ff8ea-122">See also</span></span>

[<span data-ttu-id="ff8ea-123">Создание новой политики ПИН-кода в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ff8ea-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
