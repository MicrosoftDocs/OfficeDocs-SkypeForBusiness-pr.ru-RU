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
ms.openlocfilehash: fed56c850d1d909bdd72bda0eb8c1dcd24df0f10
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568895"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="24bdc-105">Включение трансляции собрания Skype</span><span class="sxs-lookup"><span data-stu-id="24bdc-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24bdc-106">Skype для бизнеса Online больше не будет работать 31 июля 2021 г., после чего доступ к службе закончится.</span><span class="sxs-lookup"><span data-stu-id="24bdc-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="24bdc-107">Мы рекомендуем клиентам начать обновление до Microsoft Teams, основного клиента для связи и командной работы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24bdc-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="24bdc-108">Чтобы пользователи в вашей организации могли использовать трансляцию собраний Skype, необходимо включить ее.</span><span class="sxs-lookup"><span data-stu-id="24bdc-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="24bdc-109">Для этого нужно уметь пользоваться Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24bdc-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="24bdc-110">Если вы не знаете, Windows PowerShell можете нанять партнера [Майкрософт,](https://go.microsoft.com/fwlink/?linkid=391089) чтобы сделать это за вас.</span><span class="sxs-lookup"><span data-stu-id="24bdc-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="24bdc-111">Центр администрирования Microsoft Teams заменил Центр администрирования Skype для бизнеса (устаревший портал).</span><span class="sxs-lookup"><span data-stu-id="24bdc-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="24bdc-112">Все параметры управления Skype для бизнеса теперь находятся в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="24bdc-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="24bdc-113">Чтобы управлять функциями Skype для бизнеса в Центре администрирования Teams, вам должна быть назначена роль администратора [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) глобального администратора или администратор Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="24bdc-113">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="24bdc-114">Дополнительные сведения см. в статье [Управление параметрами Skype для бизнеса в Центре администрирования Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="24bdc-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="24bdc-115">Включить трансляцию собраний Skype с помощью Центра администрирования Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="24bdc-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="24bdc-116">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="24bdc-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="24bdc-117">Во sign in with your global admin account or Skype for Business admin account [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) at.</span><span class="sxs-lookup"><span data-stu-id="24bdc-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="24bdc-118">В Центре администрирования перейдите в **Центры администрирования**  >  **Teams.**</span><span class="sxs-lookup"><span data-stu-id="24bdc-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="24bdc-119">В Центре **администрирования Teams перейдите** на устаревший **портал** портала Online, на который можно транслировать собрания, а затем выберите "Включить  >    >   **трансляцию собраний Skype".**</span><span class="sxs-lookup"><span data-stu-id="24bdc-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="24bdc-120">Включить трансляцию собраний Skype с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="24bdc-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="24bdc-121">Установите модуль [Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="24bdc-121">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="24bdc-122">Откройте Windows PowerShell и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="24bdc-122">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. <span data-ttu-id="24bdc-123">Подтвердите текущую конфигурацию трансляции собраний Skype, выверив:</span><span class="sxs-lookup"><span data-stu-id="24bdc-123">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="24bdc-124">Убедитесь, что параметр  _EnableBroadcastMeeting_ имеет заданное для `False` параметра .</span><span class="sxs-lookup"><span data-stu-id="24bdc-124">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet Enable Organization (Включить трансляцию собраний Skype для организации).](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="24bdc-126">Чтобы включить трансляцию собраний Skype для вашей организации, с помощью:</span><span class="sxs-lookup"><span data-stu-id="24bdc-126">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="24bdc-127">Чтобы подтвердить, что параметр включен, повторно за  `Get-CsBroadcastMeetingConfiguration` работы.</span><span class="sxs-lookup"><span data-stu-id="24bdc-127">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     !["Включить трансляцию собраний Skype для организации".](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="24bdc-129">После внести изменения на портал трансляции собраний Skype может потребоваться до часа.</span><span class="sxs-lookup"><span data-stu-id="24bdc-129">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="24bdc-130">Теперь пользователи могут проводить широковещательные собрания с другими пользователями в вашей компании.</span><span class="sxs-lookup"><span data-stu-id="24bdc-130">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="24bdc-131">Чтобы начать, указать им на что [ведется трансляция собраний Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="24bdc-131">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="24bdc-132">Настройка сети для трансляции собраний с внешними участниками</span><span class="sxs-lookup"><span data-stu-id="24bdc-132">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="24bdc-133">Если у вас есть брандмауэр и вы хотите проводить трансляции с людьми за пределами вашей компании (которые не являются федератными), необходимо настроить сеть с помощью указанных здесь инструкций: настройка сети для трансляции собраний [Skype.](set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="24bdc-133">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="24bdc-134">Если у вас нет опыта в настройке брандмауэра, вы можете нанять партнера Майкрософт, который сделает это за вас. [](https://go.microsoft.com/fwlink/?linkid=391089)</span><span class="sxs-lookup"><span data-stu-id="24bdc-134">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="24bdc-135">Чтобы пропустить этот шаг и добавить в вашу федерацию еще один бизнес, см. вопрос "Разрешить пользователям связываться с внешними пользователями [Skype для бизнеса".](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)</span><span class="sxs-lookup"><span data-stu-id="24bdc-135">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="24bdc-136">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="24bdc-136">Related topics</span></span>

[<span data-ttu-id="24bdc-137">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="24bdc-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="24bdc-138">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="24bdc-138">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
