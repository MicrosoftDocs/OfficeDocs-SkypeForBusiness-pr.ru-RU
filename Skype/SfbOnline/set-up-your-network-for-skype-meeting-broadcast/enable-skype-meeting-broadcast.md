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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Прежде чем сотрудники вашей организации смогут использовать трансляцию собраний Skype, необходимо включить ее. Для этого вам нужно знать, как использовать Windows PowerShell. Если вы не знаете Windows PowerShell, вы можете сделать это с помощью партнера Майкрософт.
ms.openlocfilehash: 601cef096b032dd387de6d84bb7e676dc08054ec
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739057"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="49f79-105">Включение трансляции собрания Skype</span><span class="sxs-lookup"><span data-stu-id="49f79-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49f79-106">Центр администрирования Microsoft Teams заменяет центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="49f79-106">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="49f79-107">Все параметры, необходимые для управления Skype для бизнеса, теперь находятся в центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="49f79-107">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="49f79-108">Дополнительные сведения можно найти в разделе [Управление параметрами Skype для бизнеса в центре администрирования Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="49f79-108">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="49f79-109">Прежде чем сотрудники вашей организации смогут использовать трансляцию собраний Skype, необходимо включить ее.</span><span class="sxs-lookup"><span data-stu-id="49f79-109">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="49f79-110">Для этого вам нужно знать, как использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49f79-110">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="49f79-111">Если вы не знаете Windows PowerShell, вы можете сделать это с помощью [партнера Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089) .</span><span class="sxs-lookup"><span data-stu-id="49f79-111">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="49f79-112">Включение трансляции собраний Skype с помощью центра администрирования Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="49f79-112">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="49f79-113">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="49f79-113">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="49f79-114">Войдите в систему с помощью учетной записи глобального администратора или учетной записи администратора Skype для бизнеса по адресу [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="49f79-114">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="49f79-115">В центре администрирования перейдите в раздел **центры администрирования**  >  **Teams**.</span><span class="sxs-lookup"><span data-stu-id="49f79-115">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="49f79-116">В **центре администрирования Teams**перейдите к старым собраниям по сети с помощью **портала**  >  **Online meetings**  >  **Broadcast meetings**и выберите **Включить трансляцию собраний Skype**.</span><span class="sxs-lookup"><span data-stu-id="49f79-116">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="49f79-117">Включение трансляции собраний Skype с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="49f79-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="49f79-118">Убедитесь в том, что вы используете версию 3,0 или более позднюю версию Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49f79-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="49f79-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="49f79-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="49f79-120">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="49f79-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="49f79-121">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49f79-121">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="49f79-122">Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="49f79-122">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="49f79-123">При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="49f79-123">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="49f79-p105">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="49f79-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="49f79-127">В **меню Пуск**выберите пункт **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="49f79-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="49f79-128">В окне **Windows PowerShell** подключитесь к службе Microsoft 365 или Office 365, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="49f79-128">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="49f79-129">Подтвердите текущую конфигурацию трансляции собраний Skype, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="49f79-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="49f79-130">Убедитесь, что для параметра  _EnableBroadcastMeeting_ задано значение `False` .</span><span class="sxs-lookup"><span data-stu-id="49f79-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Трансляция собраний Skype с помощью командлета Organization.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="49f79-132">Включите трансляцию собраний Skype для своей организации, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="49f79-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="49f79-133">Вы можете подтвердить, что параметр включен, запустив его  `Get-CsBroadcastMeetingConfiguration` еще раз.</span><span class="sxs-lookup"><span data-stu-id="49f79-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Трансляция собраний Skype с помощью командлета Organization.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="49f79-135">После внесения изменений может вступить в силу на портале трансляции собраний Skype в течение часа.</span><span class="sxs-lookup"><span data-stu-id="49f79-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="49f79-136">Теперь ваши пользователи могут проводить широковещательные собрания с другими пользователями вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="49f79-136">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="49f79-137">Чтобы начать работу, наведите их на то, [что такое трансляция собрания Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="49f79-137">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="49f79-138">Настройка сети для трансляции собраний с внешними участниками</span><span class="sxs-lookup"><span data-stu-id="49f79-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="49f79-139">Если у вас есть брандмауэр и вы хотите хранить широковещательные показы с людьми за пределами вашей организации (которые не являются федеративными организациями), вам нужно настроить сеть, выполнив следующие инструкции: [Настройка сети для трансляции собраний Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="49f79-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="49f79-140">Если вы не сталкивались с настройкой межсетевого экрана, рассматривайте для этого действия [партнера Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089) .</span><span class="sxs-lookup"><span data-stu-id="49f79-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="49f79-141">Чтобы пропустить этот шаг и добавить еще один бизнес в Федерацию, ознакомьтесь с разделом [Разрешить пользователям связываться с внешними пользователями Skype для бизнеса](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="49f79-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="49f79-142">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="49f79-142">Related topics</span></span>

[<span data-ttu-id="49f79-143">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="49f79-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="49f79-144">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="49f79-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
