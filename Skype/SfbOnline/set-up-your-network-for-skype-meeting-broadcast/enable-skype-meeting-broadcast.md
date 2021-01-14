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
description: Чтобы пользователи в вашей организации могли использовать трансляцию собраний Skype, необходимо включить ее. Для этого нужно уметь пользоваться Windows PowerShell. Если вы не знаете, Windows PowerShell можете нанять партнера Майкрософт, чтобы сделать это за вас.
ms.openlocfilehash: 1ba8f11913c932d695806ae4fd30db5e8609530f
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865143"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="180ca-105">Включение трансляции собрания Skype</span><span class="sxs-lookup"><span data-stu-id="180ca-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="180ca-106">Skype для бизнеса Online больше не будет работать 31 июля 2021 г., после чего доступ к службе закончится.</span><span class="sxs-lookup"><span data-stu-id="180ca-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="180ca-107">Мы рекомендуем клиентам начать обновление до Microsoft Teams, основного клиента для связи и командной работы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="180ca-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="180ca-108">Чтобы пользователи в вашей организации могли использовать трансляцию собраний Skype, необходимо включить ее.</span><span class="sxs-lookup"><span data-stu-id="180ca-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="180ca-109">Для этого необходимо знать, как использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="180ca-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="180ca-110">Если вы не знаете, Windows PowerShell можете нанять партнера [Майкрософт,](https://go.microsoft.com/fwlink/?linkid=391089) чтобы сделать это за вас.</span><span class="sxs-lookup"><span data-stu-id="180ca-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="180ca-111">Центр администрирования Microsoft Teams заменил Центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="180ca-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="180ca-112">Все параметры управления Skype для бизнеса теперь находятся в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="180ca-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="180ca-113">Чтобы управлять функциями Skype для бизнеса в Центре администрирования Teams, вам должна быть назначена роль администратора [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) глобального администратора или администратор Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="180ca-113">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="180ca-114">Дополнительные сведения см. в статье [Управление параметрами Skype для бизнеса в Центре администрирования Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="180ca-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="180ca-115">Включить трансляцию собраний Skype с помощью Центра администрирования Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="180ca-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="180ca-116">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="180ca-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="180ca-117">Во sign in with your global admin account or Skype for Business admin account [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) at.</span><span class="sxs-lookup"><span data-stu-id="180ca-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="180ca-118">В Центре администрирования перейдите в **Центры администрирования**  >  **Teams.**</span><span class="sxs-lookup"><span data-stu-id="180ca-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="180ca-119">В Центре **администрирования Teams перейдите** на устаревший **портал** портала Online, на который транслируются собрания, а затем выберите "Включить  >    >   **трансляцию собраний Skype".**</span><span class="sxs-lookup"><span data-stu-id="180ca-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="180ca-120">Включить трансляцию собраний Skype с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="180ca-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="180ca-121">Убедитесь, что у вас версия 3.0 или более Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="180ca-121">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="180ca-122">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="180ca-122">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="180ca-123">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="180ca-123">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="180ca-124">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="180ca-124">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="180ca-125">Чтобы [скачать Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) и обновить Windows PowerShell до версии 4.0, см. Windows PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="180ca-125">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="180ca-126">При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="180ca-126">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="180ca-p106">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="180ca-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="180ca-130">В меню **"Пуск"** выберите пункт **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="180ca-130">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="180ca-131">В **окне Windows PowerShell** подключения к Microsoft 365 или Office 365, вы работающим с помощью:</span><span class="sxs-lookup"><span data-stu-id="180ca-131">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="180ca-132">Подтвердите текущую конфигурацию трансляции собраний Skype, выверив данная программа:</span><span class="sxs-lookup"><span data-stu-id="180ca-132">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="180ca-133">Убедитесь, что для _параметра EnableBroadcastMeeting_ задано такое же. `False`</span><span class="sxs-lookup"><span data-stu-id="180ca-133">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet Enable Organization (Включить трансляцию собраний Skype для организации).](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="180ca-135">Чтобы включить трансляцию собраний Skype для вашей организации, с помощью:</span><span class="sxs-lookup"><span data-stu-id="180ca-135">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="180ca-136">Чтобы подтвердить, что параметр включен, повторно за  `Get-CsBroadcastMeetingConfiguration` работы.</span><span class="sxs-lookup"><span data-stu-id="180ca-136">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Cmdlet Enable Organization (Включить трансляцию собраний Skype для организации).](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="180ca-138">После внести изменения на портал трансляции собраний Skype может потребоваться до часа.</span><span class="sxs-lookup"><span data-stu-id="180ca-138">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="180ca-139">Теперь пользователи могут проводить широковещательные собрания с другими пользователями в вашей компании.</span><span class="sxs-lookup"><span data-stu-id="180ca-139">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="180ca-140">Чтобы начать, указать им на что [ведется трансляция собраний Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="180ca-140">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="180ca-141">Настройка сети для трансляции собраний с внешними участниками</span><span class="sxs-lookup"><span data-stu-id="180ca-141">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="180ca-142">Если у вас есть брандмауэр и вы хотите проводить трансляции с людьми за пределами вашей компании (которые не являются федератными), необходимо настроить сеть с помощью указанных здесь инструкций: настройка сети для трансляции собраний [Skype.](set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="180ca-142">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="180ca-143">Если у вас нет опыта в настройке брандмауэра, вы можете нанять партнера Майкрософт, который сделает это за вас. [](https://go.microsoft.com/fwlink/?linkid=391089)</span><span class="sxs-lookup"><span data-stu-id="180ca-143">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="180ca-144">Если вы пропустили этот шаг и вместо этого добавили в вашу федерацию еще одну бизнес-часть, см. вопрос "Разрешить пользователям связываться с внешними пользователями [Skype для бизнеса".](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)</span><span class="sxs-lookup"><span data-stu-id="180ca-144">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="180ca-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="180ca-145">Related topics</span></span>

[<span data-ttu-id="180ca-146">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="180ca-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="180ca-147">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="180ca-147">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
