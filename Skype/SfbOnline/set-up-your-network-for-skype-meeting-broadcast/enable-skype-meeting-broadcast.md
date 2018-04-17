---
title: Включение трансляции собраний Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Чтобы обеспечить доступ пользователей к Широковещательный показ собраний в Skype, ее необходимо включить. Для этого требуются навыки работы с Windows PowerShell. Если вы не имеете опыта работы с Windows PowerShell, мы рекомендуем обратиться для выполнения этих действий к партнеру Майкрософт.
ms.openlocfilehash: f2c95e16a091c79425ea508f557a78f91ce1262f
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="546ca-105">Включение трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="546ca-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="546ca-p102">[] Чтобы обеспечить доступ пользователей к Широковещательный показ собраний в Skype, ее необходимо включить. Для этого требуются навыки работы с Windows PowerShell. Если вы не имеете опыта работы с Windows PowerShell, мы рекомендуем обратиться для выполнения этих действий к [партнеру Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089).</span><span class="sxs-lookup"><span data-stu-id="546ca-p102">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it. To do this, you need to know how to use Windows PowerShell. If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="546ca-p103">Широковещательный показ собраний в Skype по умолчанию отключена, поскольку для передачи мультимедийного контента при трансляции собрания используется сеть доставки содержимого Microsoft Azure (CDN), которая обеспечивает поддержку трансляций с аудиторией до нескольких тысяч человек. Поблочная передача мультимедийного контента через сеть доставки содержимого осуществляется в зашифрованном виде. Кэш сети доставки содержимого имеет ограниченный срок действия. Кроме того, компоненты сети доставки содержимого Azure на данный момент могут отвечать не всем требованиям типовых статей Директивы ЕС о защите данных. Включая эту функцию, вы подтверждаете ознакомление с этим уведомлением.</span><span class="sxs-lookup"><span data-stu-id="546ca-p103">Skype Meeting Broadcast is turned off by default because distribution of the media content of a broadcast meeting uses Microsoft Azure's Content Delivery Network (CDN) to achieve very high scale to support thousands of people watching a broadcast. The chunked media content passing through the CDN is encrypted, and the CDN cache has a limited lifetime. Also, the Azure CDN component may not yet meet all elements of the EU Model Clauses stemming from the EU Data Protection Directive. By enabling this feature, you acknowledge this notice.</span></span> 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="546ca-113">Включение Трансляции собраний Skype с помощью центра администрирования Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="546ca-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

1. <span data-ttu-id="546ca-114">Вход с помощью учетной записи глобального администратора Office 365 в [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="546ca-114">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="546ca-115">В центре администрирования Office 365 перейдите в раздел **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="546ca-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="546ca-116">В **Скайп по центру администрирования бизнеса**, перейдите на **собрания по сети** > **распространения собраний**и выберите команду **Включить Скайп вещания собрания**.</span><span class="sxs-lookup"><span data-stu-id="546ca-116">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="546ca-117">Включение трансляции собраний Skype с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="546ca-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="546ca-118">Проверьте, что у вас установлен Windows PowerShell 3.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="546ca-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
1. <span data-ttu-id="546ca-119">Чтобы узнать, какая у вас версия, перейдите в меню **Пуск** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="546ca-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="546ca-120">Введите  _Get-Host_ в окно **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="546ca-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="546ca-p104">Если у вас более ранняя версия, вам нужно скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="546ca-p104">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="546ca-p105">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="546ca-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
2. <span data-ttu-id="546ca-127">Из меню **Пуск** перейдите к **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="546ca-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="546ca-128">В окне **Windows PowerShell** подключитесь к своей организации Office 365, введя следующее:</span><span class="sxs-lookup"><span data-stu-id="546ca-128">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. <span data-ttu-id="546ca-129">Подтвердите текущую конфигурацию Широковещательный показ собраний в Skype, выполнив следующее:</span><span class="sxs-lookup"><span data-stu-id="546ca-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    <span data-ttu-id="546ca-130">Убедитесь, что для параметра  _EnableBroadcastMeeting_ указано значение `False`.</span><span class="sxs-lookup"><span data-stu-id="546ca-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Командлет для включения трансляции собраний Skype в организации.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. <span data-ttu-id="546ca-132">Подключите функцию Широковещательный показ собраний в Skype, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="546ca-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    <span data-ttu-id="546ca-133">Для подтверждения того, что настройка включена, повторно выполните команду  `Get-CsBroadcastMeetingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="546ca-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Командлет для включения трансляции собраний Skype в организации.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="546ca-135">Чтобы внесенные изменения вступили в силу на портале Широковещательный показ собраний в Skype, может потребоваться до часа.</span><span class="sxs-lookup"><span data-stu-id="546ca-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
6. <span data-ttu-id="546ca-p106">Теперь пользователи могут транслировать собрания для других пользователей вашей организации. Полезные сведения о начале работы пользователи могут найти в разделе [Что такое трансляция собрания Skype?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="546ca-p106">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="546ca-138">Настройка сети для трансляции собраний с внешними участниками</span><span class="sxs-lookup"><span data-stu-id="546ca-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="546ca-139">Если в вашей среде применяется брандмауэр, для проведения трансляций с участниками, не работающими в вашей организации (не являющимися членами федерации), вам необходимо настроить сеть, следуя приведенным ниже инструкциям: [Настройка сети для трансляции собрания Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="546ca-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="546ca-140">Если у вас нет опыта в настройке брандмауэра, мы рекомендуем обратиться для выполнения этих действий к [партнеру Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089).</span><span class="sxs-lookup"><span data-stu-id="546ca-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="546ca-141">Чтобы пропустить этот шаг и добавить другую организацию в вашу федерацию, выполните инструкции в разделе [Разрешите пользователям связываться с внешними пользователями Skype для бизнеса](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="546ca-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="546ca-142">See also</span><span class="sxs-lookup"><span data-stu-id="546ca-142">Related topics</span></span>

[<span data-ttu-id="546ca-143">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="546ca-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="546ca-144">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="546ca-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 