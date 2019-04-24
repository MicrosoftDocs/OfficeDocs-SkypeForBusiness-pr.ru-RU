---
title: Включение трансляции собрания Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Перед людей в организации можно использовать Скайп вещания собрания, необходимо включить его. Для этого необходимо знать, как с помощью Windows PowerShell. Если вы не знаете Windows PowerShell, рассмотрите возможность найма партнера корпорации Майкрософт, чтобы выполнить это действие для вас.
ms.openlocfilehash: 699b82af07b263331ee5508326bf3e7ed015848e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226822"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="a6f2e-105">Включение трансляции собрания Skype</span><span class="sxs-lookup"><span data-stu-id="a6f2e-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="a6f2e-106">Перед людей в организации можно использовать Скайп вещания собрания, необходимо включить его.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-106">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="a6f2e-107">Для этого необходимо знать, как с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-107">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="a6f2e-108">Если вы не знаете Windows PowerShell, рассмотрите возможность найма [партнера корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089) для выполнения этого шага для вас.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-108">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="a6f2e-109">Включение Скайп собрания вещания с помощью Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="a6f2e-109">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="a6f2e-110">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="a6f2e-110">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="a6f2e-111">Вход с помощью учетной записи глобального администратора Office 365 в [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="a6f2e-111">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="a6f2e-112">В центре администрирования Office 365 перейдите на **центры администрирования** > **Скайп для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-112">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a6f2e-113">В **Скайп по центру администрирования бизнеса**, перейдите на **собрания по сети** > **распространения собраний**и выберите команду **Включить Скайп вещания собрания**.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-113">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="a6f2e-114">Включение Скайп собрания вещания с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6f2e-114">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="a6f2e-115">Убедитесь, что запущена версия 3.0 или более поздней версии для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-115">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="a6f2e-116">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-116">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="a6f2e-117">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-117">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="a6f2e-p103">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="a6f2e-p104">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="a6f2e-124">В **Меню "Пуск"** выберите команду **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-124">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="a6f2e-125">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a6f2e-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   ```
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="a6f2e-126">Подтверждение текущей конфигурации Скайп собрания вещания с помощью:</span><span class="sxs-lookup"><span data-stu-id="a6f2e-126">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="a6f2e-127">Убедитесь, что параметр _EnableBroadcastMeeting_ `False`.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-127">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Командлет Скайп вещания Включение организации собраний.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="a6f2e-129">Включение Скайп собрания вещания для вашей организации, выполнив:</span><span class="sxs-lookup"><span data-stu-id="a6f2e-129">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="a6f2e-130">Убедитесь, что этот параметр включен, выполнив `Get-CsBroadcastMeetingConfiguration` еще раз.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-130">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Скайп собрания вещания включите командлет организации.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="a6f2e-132">После внесения изменений, он может занять час вступили в силу на портале Скайп собрания вещания.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-132">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="a6f2e-133">Пользователи теперь могут содержать вещания встречи с другими пользователями в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-133">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="a6f2e-134">По началу работы, укажите их [возможности собраний Скайп, вещание?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="a6f2e-134">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="a6f2e-135">Настройка сети для вещания собрания с внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="a6f2e-135">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="a6f2e-136">Брандмауэр, и требуется для хранения вещании с людьми за ее пределами бизнеса (пользователей, которые не являются федеративными бизнеса), требуется ли настройка сети с использованием эти инструкции: [Настройка сети для Скайп собрания вещания](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="a6f2e-136">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="a6f2e-137">Если вы опытный с Настройка брандмауэра, рассмотрите возможность найма [партнера корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089) для выполнения этого шага для вас.</span><span class="sxs-lookup"><span data-stu-id="a6f2e-137">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="a6f2e-138">Пропустите этот шаг и вместо этого добавьте другой компании вашей федерации см [Разрешить пользователям включать поддержку для связи внешних Скайп для коммерческих пользователей](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="a6f2e-138">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="a6f2e-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a6f2e-139">Related topics</span></span>

[<span data-ttu-id="a6f2e-140">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a6f2e-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="a6f2e-141">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a6f2e-141">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 