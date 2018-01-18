---
title: "Включение Скайп собрания вещания"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Перед людей в организации можно использовать Скайп вещания собрания, необходимо включить его. Для этого необходимо знать, как с помощью Windows PowerShell. Если вы не знаете Windows PowerShell, рассмотрите возможность найма партнера корпорации Майкрософт, чтобы выполнить это действие для вас."
ms.openlocfilehash: 975f0304f2053e23375c5eabc62ec224bedc02e7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="f378e-105">Включение Скайп собрания вещания</span><span class="sxs-lookup"><span data-stu-id="f378e-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="f378e-106">Перед людей в организации можно использовать Скайп вещания собрания, необходимо включить его.</span><span class="sxs-lookup"><span data-stu-id="f378e-106">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="f378e-107">Для этого необходимо знать, как с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f378e-107">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="f378e-108">Если вы не знаете Windows PowerShell, рассмотрите возможность найма [партнера корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089) для выполнения этого шага для вас.</span><span class="sxs-lookup"><span data-stu-id="f378e-108">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f378e-109">Скайп собрания вещания отключена по умолчанию из-за распределения контента мультимедиа вещания собрания использует Microsoft Azure сети доставки содержимого (CDN) для достижения очень высокий масштаба для поддержки тысячи людей, просмотра вещания.</span><span class="sxs-lookup"><span data-stu-id="f378e-109">Skype Meeting Broadcast is turned off by default because distribution of the media content of a broadcast meeting uses Microsoft Azure's Content Delivery Network (CDN) to achieve very high scale to support thousands of people watching a broadcast.</span></span> <span data-ttu-id="f378e-110">Частям мультимедийного содержимого, проходящих через CDN шифруются и кэш CDN имеет ограничения времени жизни.</span><span class="sxs-lookup"><span data-stu-id="f378e-110">The chunked media content passing through the CDN is encrypted, and the CDN cache has a limited lifetime.</span></span> <span data-ttu-id="f378e-111">Кроме того компонент Azure CDN, могут не еще не отвечать все элементы типовыми статьями ЕС, возникающих из-за директивы защиты данных ЕС.</span><span class="sxs-lookup"><span data-stu-id="f378e-111">Also, the Azure CDN component may not yet meet all elements of the EU Model Clauses stemming from the EU Data Protection Directive.</span></span> <span data-ttu-id="f378e-112">Эта функция включена, подтвердить это Примечание.</span><span class="sxs-lookup"><span data-stu-id="f378e-112">By enabling this feature, you acknowledge this notice.</span></span> 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="f378e-113">Включение Скайп собрания вещания с помощью Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="f378e-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

1. <span data-ttu-id="f378e-114">Войдите с использованием учетной записи глобального администратора Office 365 по адресу [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="f378e-114">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="f378e-115">В центре администрирования Office 365 перейдите на **центры администрирования** > **Скайп для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="f378e-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f378e-116">В **Скайп по центру администрирования бизнеса**, перейдите на **собрания по сети** > **распространения собраний**и выберите команду **Включить Скайп вещания собрания**.</span><span class="sxs-lookup"><span data-stu-id="f378e-116">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="f378e-117">Включение Скайп собрания вещания с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f378e-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="f378e-118">Убедитесь, что запущена версия 3.0 или более поздней версии для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f378e-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
1. <span data-ttu-id="f378e-119">Чтобы убедиться, что выполняется версия 3.0 или более поздней версии: **Меню "Пуск"** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f378e-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="f378e-120">Проверьте версию, введя в окне **Windows PowerShell** команду _Get-Host_.</span><span class="sxs-lookup"><span data-stu-id="f378e-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="f378e-p104">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="f378e-p104">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="f378e-p105">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="f378e-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
2. <span data-ttu-id="f378e-127">В **Меню "Пуск"**выберите команду **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f378e-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="f378e-128">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f378e-128">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. <span data-ttu-id="f378e-129">Подтверждение текущей конфигурации Скайп собрания вещания с помощью:</span><span class="sxs-lookup"><span data-stu-id="f378e-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    <span data-ttu-id="f378e-130">Убедитесь, что параметр _EnableBroadcastMeeting_ `False`.</span><span class="sxs-lookup"><span data-stu-id="f378e-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Командлет Скайп вещания Включение организации собраний.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. <span data-ttu-id="f378e-132">Включение Скайп собрания вещания для вашей организации, выполнив:</span><span class="sxs-lookup"><span data-stu-id="f378e-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    <span data-ttu-id="f378e-133">Убедитесь, что этот параметр включен, выполнив `Get-CsBroadcastMeetingConfiguration` еще раз.</span><span class="sxs-lookup"><span data-stu-id="f378e-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Скайп собрания вещания включите командлет организации.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="f378e-135">После внесения изменений, он может занять час вступили в силу на портале Скайп собрания вещания.</span><span class="sxs-lookup"><span data-stu-id="f378e-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
6. <span data-ttu-id="f378e-136">Пользователи теперь могут содержать вещания встречи с другими пользователями в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="f378e-136">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="f378e-137">По началу работы, укажите их [возможности собраний Скайп, вещание?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="f378e-137">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="f378e-138">Настройка сети для вещания собрания с внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="f378e-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="f378e-139">Брандмауэр, и требуется для хранения вещании с людьми за ее пределами бизнеса (пользователей, которые не являются федеративными бизнеса), требуется ли настройка сети с использованием эти инструкции: [Настройка сети для Скайп собрания вещания](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="f378e-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="f378e-140">Если вы опытный с Настройка брандмауэра, рассмотрите возможность найма [партнера корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089) для выполнения этого шага для вас.</span><span class="sxs-lookup"><span data-stu-id="f378e-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="f378e-141">Пропустите этот шаг и вместо этого добавьте другой компании вашей федерации см [Разрешить пользователям включать поддержку для связи внешних Скайп для коммерческих пользователей](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="f378e-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="f378e-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="f378e-142">Related topics</span></span>

[<span data-ttu-id="f378e-143">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f378e-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="f378e-144">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f378e-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

