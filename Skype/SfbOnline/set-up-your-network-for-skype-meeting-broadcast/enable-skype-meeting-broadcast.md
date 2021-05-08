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
description: Чтобы люди в вашей организации могли Skype трансляцию собраний, необходимо включить ее. Для этого необходимо знать, как использовать Windows PowerShell. Если вы не знаете, Windows PowerShell, вы можете нанять партнера Майкрософт, который сделает это за вас.
ms.openlocfilehash: 6cdd7f12483025697b139203907f87f9cd3dc764
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237015"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="fd604-105">Включение трансляции собрания Skype</span><span class="sxs-lookup"><span data-stu-id="fd604-105">Enable Skype Meeting Broadcast</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="fd604-106">Skype для бизнеса 31 июля 2021 г. заканчивается доступ к службе Online.</span><span class="sxs-lookup"><span data-stu-id="fd604-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="fd604-107">Мы рекомендуем клиентам начать обновление до Microsoft Teams , основного клиента для связи и командной работы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd604-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="fd604-108">Чтобы люди в вашей организации могли Skype трансляцию собраний, необходимо включить ее.</span><span class="sxs-lookup"><span data-stu-id="fd604-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="fd604-109">Для этого необходимо знать, как использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd604-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="fd604-110">Если вы не знаете, Windows PowerShell, возможно, [](https://go.microsoft.com/fwlink/?linkid=391089) вы нанимаете партнера Майкрософт, который сделает это за вас.</span><span class="sxs-lookup"><span data-stu-id="fd604-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="fd604-111">Центр Microsoft Teams администрирования заменил центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="fd604-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="fd604-112">Все параметры управления Skype для бизнеса теперь находятся в Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="fd604-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="fd604-113">Чтобы управлять функциями Skype для бизнеса Teams в Центре администрирования azure [AD,](/azure/active-directory/roles/permissions-reference) вам должна быть назначена роль администратора Azure AD глобальный администратор Skype для бизнеса администратор.</span><span class="sxs-lookup"><span data-stu-id="fd604-113">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="fd604-114">Дополнительные сведения см. в статье [Управление параметрами Skype для бизнеса в Центре администрирования Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="fd604-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="fd604-115">Включить Skype собрания с помощью центра Skype для бизнеса администрирования</span><span class="sxs-lookup"><span data-stu-id="fd604-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="fd604-116">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="fd604-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="fd604-117">Во sign in with your global admin account or Skype для бизнеса admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="fd604-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="fd604-118">В Центре администрирования перейдите **в** центр администрирования Teams  >  .</span><span class="sxs-lookup"><span data-stu-id="fd604-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="fd604-119">В Центре **Teams администрирования** перейдите на устаревший портал Онлайн-собрания Трансляция собраний , а затем выберите Включить  >    >   **Skype трансляцию собраний**.</span><span class="sxs-lookup"><span data-stu-id="fd604-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="fd604-120">Включить Skype собрания с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd604-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="fd604-121">Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="fd604-121">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="fd604-122">Откройте Windows PowerShell командную команду и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="fd604-122">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. <span data-ttu-id="fd604-123">Подтвердите текущую конфигурацию Skype трансляции собрания с помощью:</span><span class="sxs-lookup"><span data-stu-id="fd604-123">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="fd604-124">Убедитесь, что параметр  _EnableBroadcastMeeting_ имеет заданное для `False` параметра .</span><span class="sxs-lookup"><span data-stu-id="fd604-124">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype Cmdlet Enable Organization (Включить трансляцию собраний).](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="fd604-126">В Skype трансляцию собраний для организации можно включить:</span><span class="sxs-lookup"><span data-stu-id="fd604-126">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="fd604-127">Вы можете подтвердить, что этот параметр включен, повторно  `Get-CsBroadcastMeetingConfiguration` заверив его.</span><span class="sxs-lookup"><span data-stu-id="fd604-127">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype "Включить трансляцию собраний" для организации.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="fd604-129">После внести изменения на портале широковещательного Skype может потребоваться до часа.</span><span class="sxs-lookup"><span data-stu-id="fd604-129">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="fd604-130">Теперь пользователи могут проводить широковещательные собрания с другими пользователями в вашей компании.</span><span class="sxs-lookup"><span data-stu-id="fd604-130">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="fd604-131">Чтобы начать, наведя на них указатель на пункт Что такое [Skype трансляции собрания?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="fd604-131">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="fd604-132">Настройка сети для трансляции собраний с внешними участниками</span><span class="sxs-lookup"><span data-stu-id="fd604-132">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="fd604-133">Если у вас есть брандмауэр и вы хотите проводить трансляции с людьми за пределами вашей компании (которые не являются федератными), необходимо настроить сеть с помощью указанных здесь инструкций: Настройка сети для [Skype](set-up-your-network-for-skype-meeting-broadcast.md)трансляции собраний .</span><span class="sxs-lookup"><span data-stu-id="fd604-133">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="fd604-134">Если у вас нет опыта настройки брандмауэра, [](https://go.microsoft.com/fwlink/?linkid=391089) вы можете нанять партнера Майкрософт, который сделает это за вас.</span><span class="sxs-lookup"><span data-stu-id="fd604-134">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="fd604-135">Чтобы пропустить этот шаг и вместо этого добавить в вашу федерацию другую бизнес-федерацию, см. разрешение пользователям связываться с внешними Skype для бизнеса [пользователями.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)</span><span class="sxs-lookup"><span data-stu-id="fd604-135">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="fd604-136">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fd604-136">Related topics</span></span>

[<span data-ttu-id="fd604-137">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="fd604-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[<span data-ttu-id="fd604-138">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="fd604-138">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
