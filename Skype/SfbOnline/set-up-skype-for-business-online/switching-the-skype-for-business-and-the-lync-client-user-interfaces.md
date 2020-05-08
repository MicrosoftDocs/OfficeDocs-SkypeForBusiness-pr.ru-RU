---
title: Переключение между пользовательскими интерфейсами клиентов Skype для бизнеса и Lync
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Сведения о том, как переключаться между пользовательским интерфейсом Skype для бизнеса и клиентом Lync с помощью PowerShell в Microsoft 365 или Office 365 '
ms.openlocfilehash: 02542d11c7315c8f7e183fb78eebf210ead2df94
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164308"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a><span data-ttu-id="8ba4b-103">Переключение между пользовательскими интерфейсами клиентов Skype для бизнеса и Lync</span><span class="sxs-lookup"><span data-stu-id="8ba4b-103">Switching between the Skype for Business and the Lync client user interfaces</span></span>

<span data-ttu-id="8ba4b-104">Для организаций, использующих Skype для бизнеса Online, вы можете использовать удаленную оболочку PowerShell в Microsoft 365 или Office 365, чтобы пользователи Skype для бизнеса могли использовать клиент Skype для бизнеса или пользовательский интерфейс клиента Skype для бизнеса (Lync).</span><span class="sxs-lookup"><span data-stu-id="8ba4b-104">For Skype for Business Online organizations, you can use the Remote PowerShell in Microsoft 365 or Office 365 to enable your Skype for Business users to use the Skype for Business client or the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="8ba4b-105">Параметр по умолчанию предназначен для пользователей, которые используют пользовательский интерфейс клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-105">The default setting is for users to use the Skype for Business client user interface.</span></span> <span data-ttu-id="8ba4b-106">Если вы предпочитаете использовать клиент Lync, вы можете управлять поведением первого запуска клиента, чтобы отобразить пользовательский интерфейс Lync, выполнив действия, описанные ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-106">If you'd prefer to use the Lync client experience, you can manage the first launch client behavior to display the Lync user interface by following the steps later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ba4b-p102">Интерфейс клиента Lync 2013 недоступен для версий Skype для бизнеса 2016. Перед настройкой клиентской среды на использование клиента Lync 2013 убедитесь, что версия клиента не начинается с цифр "16" (например: 16.x.x.x).</span><span class="sxs-lookup"><span data-stu-id="8ba4b-p102">The Lync 2013 client experience isn't an option for Skype for Business 2016 client versions. Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
> [!TIP]
> <span data-ttu-id="8ba4b-109">Если вы хотите просто переключить пользовательский интерфейс и не хотите выполнять инструкции вручную, ознакомьтесь со статьей для упрощения сценария PowerShell в [центре загрузки Майкрософт](https://go.microsoft.com/fwlink/?LinkId=532431) .</span><span class="sxs-lookup"><span data-stu-id="8ba4b-109">If you want to easily switch the user interface and don't want to do the manual steps, see the [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=532431) for a PowerShell script to make it easier.</span></span>
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a><span data-ttu-id="8ba4b-110">Переключение пользовательского интерфейса Skype для бизнеса для пользователей</span><span class="sxs-lookup"><span data-stu-id="8ba4b-110">Switching the Skype for Business user interface for users</span></span>

<span data-ttu-id="8ba4b-p103">Модуль Windows PowerShell для Skype для бизнеса Online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса Online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). Для получения других сведений см. раздел [Настройка компьютера для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=534539).</span><span class="sxs-lookup"><span data-stu-id="8ba4b-p103">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). For other information, see [Configuring your computer for Skype for Business Online management](https://go.microsoft.com/fwlink/?LinkId=534539).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8ba4b-p104">Параметр политики  _Global_ для переключения пользовательского интерфейса не применяется, если пользователь уже применил настраиваемую политику. Чтобы изменить пользовательский интерфейс, необходимо выполнить следующую команду для каждого пользователя, применившего настраиваемую политику:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-p104">The  _Global_ policy setting for switching the user interface won't be applied to a user that already has a custom policy applied. To be able to change the user interface, you will need to run the following for each user that has a custom policy applied:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> <span data-ttu-id="8ba4b-116">Политика  _ClientPolicyEnableSkypeUI_ заменит действующую настраиваемую политику пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-116">The  _ClientPolicyEnableSkypeUI_ policy will replace the existing custom policy setting for the user.</span></span>
  
<span data-ttu-id="8ba4b-117">Чтобы включить клиент Skype для бизнеса для всех пользователей в вашей организации, откройте Remote PowerShell и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-117">To enable all of the users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="8ba4b-118">Если политика настроена правильно, появится следующая запись:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-118">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
<span data-ttu-id="8ba4b-120">Чтобы включить клиент Skype для бизнеса (Lync) для всех пользователей в вашей организации, откройте Remote PowerShell и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-120">To enable all of the users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span> 
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="8ba4b-121">Если политика настроена правильно, появится следующая запись:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-121">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
<span data-ttu-id="8ba4b-123">Чтобы включить клиент Skype для бизнеса для одного пользователя в вашей организации, откройте Remote PowerShell и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-123">To allow a single user in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

<span data-ttu-id="8ba4b-124">Если политика настроена правильно, появится следующая запись:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-124">If you set the policy right, you will see:</span></span>
  
![Skype для бизнеса Online: включение пользовательского интерфейса](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
<span data-ttu-id="8ba4b-126">Чтобы включить клиент Skype для бизнеса (Lync) для одного пользователя в вашей организации, откройте Remote PowerShell и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-126">To allow a single user in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

<span data-ttu-id="8ba4b-127">Если политика настроена правильно, появится следующая запись:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-127">If you set the policy right, you will see:</span></span>
  
![Skype для бизнеса Online: отключение пользовательского интерфейса](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
<span data-ttu-id="8ba4b-129">Чтобы включить клиент Skype для бизнеса для нескольких пользователей в вашей организации, откройте Remote PowerShell и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-129">To allow multiple users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  

```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="8ba4b-130">Чтобы включить клиент Skype для бизнеса (Lync) для нескольких пользователя в вашей организации, откройте Remote PowerShell и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-130">To allow multiple users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="8ba4b-131">Чтобы включить клиент Skype для бизнеса для группы пользователей в вашей организации, откройте Remote PowerShell и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-131">To allow a group of users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="8ba4b-132">Чтобы включить клиент Skype для бизнеса (Lync) для группы пользователей в вашей организации, откройте Remote PowerShell и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-132">To allow a group of users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  <span data-ttu-id="8ba4b-p105">Имя пользователя  это имя учетной записи пользователя, для которой необходимо назначить политику. Имя учетной записи пользователя может быть указано в следующих форматах:>  Адрес SIP пользователя>  Имя участника-пользователя (UPN)>  Домен пользователя\\имя пользователя>  Отображаемое имя Active Directory пользователя</span><span class="sxs-lookup"><span data-stu-id="8ba4b-p105">The user's name is the name of the user's account that the policy should be assigned to. The user's account name can be entered in one of the following formats:>  SIP address of the user>  User Principal name (UPN) of the user>  Domain\\username of the user>  Active Directory display name of the user</span></span>
  
[<span data-ttu-id="8ba4b-135">Использование Windows PowerShell для управления Lync Online</span><span class="sxs-lookup"><span data-stu-id="8ba4b-135">Using Windows PowerShell to manage Lync Online</span></span>](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a><span data-ttu-id="8ba4b-136">Параметры политики Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8ba4b-136">Skype for Business Online policy settings</span></span>

<span data-ttu-id="8ba4b-137">Эта таблица содержит информацию о взаимодействии с пользователем при первом применении политики.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-137">This table shows the user experience when the policy is first applied to users:</span></span>
  
|<span data-ttu-id="8ba4b-138">**Параметр политики администратора**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-138">**Admin policy setting**</span></span>|<span data-ttu-id="8ba4b-139">**Пользовательский интерфейс**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-139">**User interface displayed**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8ba4b-140">Политика не установлена.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-140">The policy isn't set.</span></span> |<span data-ttu-id="8ba4b-141">Пользователь продолжает работать в пользовательском интерфейсе клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-141">The user will continue using the Skype for Business client user interface.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|<span data-ttu-id="8ba4b-142">Пользователь продолжает работать в пользовательском интерфейсе клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-142">The user will continue using the Skype for Business client user interface.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|<span data-ttu-id="8ba4b-143">Пользователю будет предложено переключиться на пользовательский интерфейс клиента Skype для бизнеса (Lync).</span><span class="sxs-lookup"><span data-stu-id="8ba4b-143">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="8ba4b-144">Пользователь может переключиться позже.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-144">They can switch later.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|<span data-ttu-id="8ba4b-145">Пользователь будет использовать пользовательский интерфейс клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-145">The user will be using the Skype for Business client user interface.</span></span> |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|<span data-ttu-id="8ba4b-146">Пользователю будет предложено переключиться на пользовательский интерфейс клиента Skype для бизнеса (Lync).</span><span class="sxs-lookup"><span data-stu-id="8ba4b-146">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="8ba4b-147">В дальнейшем администратор может изменить этот параметр и переключить пользователя на пользовательский интерфейс клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-147">An admin can change the setting in the future that will switch them to the Skype for Business client user interface.</span></span> |
   
<span data-ttu-id="8ba4b-148">Эта таблица содержит информацию о взаимодействии с пользователем при изменении политики.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-148">This table shows the user experience when the policy is changed:</span></span>
  
|<span data-ttu-id="8ba4b-149">**Параметр политики администратора**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-149">**Admin policy setting**</span></span>|<span data-ttu-id="8ba4b-150">**Пользовательский интерфейс Skype для бизнеса (Lync)**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-150">**Skype for Business (Lync) user interface**</span></span>|<span data-ttu-id="8ba4b-151">**Пользовательский интерфейс Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-151">**Skype for Business user interface**</span></span>|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|<span data-ttu-id="8ba4b-152">Пользователю будет предложено переключиться на пользовательский интерфейс клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-152">The user will be asked to switch to the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="8ba4b-153">Пользователь по-прежнему будет использовать пользовательский интерфейс клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-153">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|<span data-ttu-id="8ba4b-154">Пользователь продолжит пользоваться интерфейсом Skype для бизнеса (Lync).</span><span class="sxs-lookup"><span data-stu-id="8ba4b-154">The user will continue to use the Skype for Business (Lync) interface.</span></span>  <br/> |<span data-ttu-id="8ba4b-155">Пользователю будет предложено переключиться на пользовательский интерфейс клиента Skype для бизнеса (Lync).</span><span class="sxs-lookup"><span data-stu-id="8ba4b-155">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span>  <br/> |
|<span data-ttu-id="8ba4b-156">Политика не установлена.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-156">The policy isn't set.</span></span>  <br/> |<span data-ttu-id="8ba4b-157">Пользователи не будут видеть пользовательский интерфейс клиента Skype для бизнеса (Lync), если эта политика не задана.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-157">Users will never see the Skype for Business (Lync) client user interface if the policy is not set.</span></span> <span data-ttu-id="8ba4b-158">Пользователь будет работать только в пользовательском интерфейсе клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-158">They will always use the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="8ba4b-159">Пользователь по-прежнему будет использовать пользовательский интерфейс клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-159">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
   
<span data-ttu-id="8ba4b-p109">В этой таблице приводятся все настраиваемые политики, доступные для Online. Эти новые политики были созданы для того, чтобы предоставить администраторам гибкость и сохранить прежнюю настраиваемую политику при переключении флагов EnableSkypeUI. Чтобы назначить пользователям одну из приведенных ниже политик, используйте указанные выше командлеты.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-p109">This table shows all the Online custom policies available. There are new policies created to give admins flexibility in retaining the old custom policy while switching between the EnableSkypeUI flags. Please use the cmdlets from above to grant one of the below policies to your users.</span></span>
  
|<span data-ttu-id="8ba4b-163">**Название политики**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-163">**Policy name**</span></span>|<span data-ttu-id="8ba4b-164">**EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-164">**EnableSkypeUI**</span></span>|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |<span data-ttu-id="8ba4b-165">False</span><span class="sxs-lookup"><span data-stu-id="8ba4b-165">False</span></span>|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |<span data-ttu-id="8ba4b-166">False</span><span class="sxs-lookup"><span data-stu-id="8ba4b-166">False</span></span>|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |<span data-ttu-id="8ba4b-167">False</span><span class="sxs-lookup"><span data-stu-id="8ba4b-167">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |<span data-ttu-id="8ba4b-168">False</span><span class="sxs-lookup"><span data-stu-id="8ba4b-168">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |<span data-ttu-id="8ba4b-169">False</span><span class="sxs-lookup"><span data-stu-id="8ba4b-169">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|<span data-ttu-id="8ba4b-170">False</span><span class="sxs-lookup"><span data-stu-id="8ba4b-170">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |<span data-ttu-id="8ba4b-171">False</span><span class="sxs-lookup"><span data-stu-id="8ba4b-171">False</span></span>|

   
<span data-ttu-id="8ba4b-172">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-172">To get started with Windows PowerShell, see these topics:</span></span>
  
- [<span data-ttu-id="8ba4b-173">Зачем использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ba4b-173">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [<span data-ttu-id="8ba4b-174">Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ba4b-174">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a><span data-ttu-id="8ba4b-175">Режим работы клиента при первом запуске</span><span class="sxs-lookup"><span data-stu-id="8ba4b-175">First launch client behaviors</span></span>

<span data-ttu-id="8ba4b-176">По умолчанию при первом запуске Skype для бизнеса они всегда будут видеть пользовательский интерфейс Skype для бизнеса, даже если вы выбрали клиентскую политику для клиента Lync (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) в соответствии с описанными выше возможностями.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-176">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the client policy to the Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) as described previously.</span></span> <span data-ttu-id="8ba4b-177">Через несколько минут пользователям будет предложено переключиться в режим Lync.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-177">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="8ba4b-178">Чтобы отобразить интерфейс Lync при первом запуске клиента Skype для бизнеса, выполните следующие действия до того, как клиент будет запущен в первый раз после обновления.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-178">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="8ba4b-179">Выполните действия, описанные выше в этом разделе, и подтвердите, что политика клиента настроена на отключение интерфейса Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-179">Follow the steps earlier in this topic and confirm that the client policy is set to disable the Skype for Business user interface.</span></span>
    
2. <span data-ttu-id="8ba4b-p111">Обновите системный реестр на компьютере пользователя. Это необходимо сделать до первого запуска клиента Skype для бизнеса. Действие выполняется всего один раз. Сведения о создании объекта групповой политики для обновления реестра на присоединенном к домену компьютере см. далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-p111">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="8ba4b-183">В строке **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** создайте новое **бинарное** значение.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-183">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="8ba4b-184">**Имя значения** должно быть **EnableSkypeUI**. Для **данных значения** задайте **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-184">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="8ba4b-185">Строка должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-185">The key should look like the following:</span></span>
    
    <span data-ttu-id="8ba4b-186">[\\HKEY_CURRENT_USERное\\программное обеспечение Microsoft\\Office\\Lync]</span><span class="sxs-lookup"><span data-stu-id="8ba4b-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span></span>
    
    <span data-ttu-id="8ba4b-187">"CanSharePptInCollab" = DWORD: 00000001</span><span class="sxs-lookup"><span data-stu-id="8ba4b-187">"CanSharePptInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="8ba4b-188">"CanShareOneNoteInCollab" = DWORD: 00000001</span><span class="sxs-lookup"><span data-stu-id="8ba4b-188">"CanShareOneNoteInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="8ba4b-189">"CanAppShareInCollab" = DWORD: 00000001</span><span class="sxs-lookup"><span data-stu-id="8ba4b-189">"CanAppShareInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="8ba4b-190">"EnableSkypeUI" = Hex: 00, 00, 00, 00</span><span class="sxs-lookup"><span data-stu-id="8ba4b-190">"EnableSkypeUI"=hex:00,00,00,00</span></span>
    
<span data-ttu-id="8ba4b-191">Теперь интерфейс Lync будет отображаться при первом запуске клиента Skype для бизнеса пользователями.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-191">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="8ba4b-192">Руководство по управлению отображением экрана приветствия</span><span class="sxs-lookup"><span data-stu-id="8ba4b-192">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="8ba4b-193">Когда пользователи открывают клиент Skype для бизнеса, по умолчанию отображается экран приветствия, включающий *семь советов*, которые нужно запросить.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-193">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="8ba4b-194">Вы можете отключить отображение экрана приветствия, но по-прежнему предоставить пользователям доступ к учебнику, добавив следующий параметр реестра на клиентском компьютере:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-194">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="8ba4b-p113">В строке **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** создайте новое **значение DWORD (32-разрядное)**. **Имя значения** должно быть **IsBasicTutorialSeenByUser**. Для **данных значения** задайте **1**.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-p113">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="8ba4b-197">Строка должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-197">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="8ba4b-198">Отключение руководства в клиенте</span><span class="sxs-lookup"><span data-stu-id="8ba4b-198">Turn off the client tutorial</span></span>

<span data-ttu-id="8ba4b-199">Чтобы не показывать пользователям руководство, задайте в реестре следующее значение.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-199">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="8ba4b-p114">В строке **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** создайте новое **значение DWORD (32-разрядное)**. **Имя значения** должно быть **TutorialFeatureEnabled**. Для **данных значения** задайте **0**.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-p114">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
```PowerShell
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="8ba4b-202">Чтобы снова включить руководство, задайте для параметра **Данные значения** значение **1**.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-202">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="8ba4b-203">Создание объекта групповой политики для изменения реестра на компьютере, присоединенном к домену</span><span class="sxs-lookup"><span data-stu-id="8ba4b-203">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="8ba4b-p115">Для отображения интерфейса Lync при первом запуске клиента Skype для бизнеса необходимо только один раз обновить реестр. Если для обновления реестра используется объект групповой политики (GPO), необходимо определить объект для создания нового значения, а не обновлять данные значения. Если при применении GPO новое значение не существует, оно будет создано, а для данных значения будет задано значение 0.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>
  
<span data-ttu-id="8ba4b-p116">В процедуре ниже описывается изменение реестра таким образом, чтобы при первом запуске Skype для бизнеса пользователем отображался интерфейс Lync. С помощью этой процедуры можно также обновить реестр и отключить показ учебного пособия на экране приветствия, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
 <span data-ttu-id="8ba4b-209">**Создание объекта групповой политики**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-209">**To create the GPO**</span></span>
  
1. <span data-ttu-id="8ba4b-210">Запустите **Консоль управления групповыми политиками**.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-210">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="8ba4b-211">Сведения о работе с консолью управления групповыми политиками см. в разделе [Консоль управления групповыми политиками](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="8ba4b-211">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="8ba4b-212">Щелкните правой кнопкой мыши узел **Объекты групповой политики** и выберите в меню пункт **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-212">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="8ba4b-213">В диалоговом окне **Новый объект групповой политики** введите название объекта, напримерMakeLyncDefaultUI, затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-213">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="8ba4b-214">Щелкните правой кнопкой мыши только что созданный объект групповой политики и выберите в меню пункт **Редактировать**.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-214">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="8ba4b-215">В **Редакторе управления групповыми политиками** разверните папки **Конфигурация пользователя**, **Параметры**, **Параметры Windows** и выберите узел **Реестр**.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-215">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="8ba4b-216">Щелкните правой кнопкой мыши на узле **Реестр** и выберите **Создать** > **Элемент реестра**.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-216">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="8ba4b-217">В диалоговом окне **Новые свойства реестра** обновите следующие поля.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-217">On the **New Registry Properties** dialog, update the following:</span></span>
    
|<span data-ttu-id="8ba4b-218">**Поле**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-218">**Field**</span></span>|<span data-ttu-id="8ba4b-219">**Значение для выбора или ввода**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-219">**Value to select or enter**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8ba4b-220">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-220">**Action**</span></span> <br/> |<span data-ttu-id="8ba4b-221">**Создание**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-221">**Create**</span></span> <br/> |
|<span data-ttu-id="8ba4b-222">**Куст**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-222">**Hive**</span></span> <br/> | <span data-ttu-id="8ba4b-223">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="8ba4b-223">HKEY_CURRENT_USER</span></span> <br/> |
|<span data-ttu-id="8ba4b-224">**Путь к разделу**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-224">**Key Path**</span></span> <br/> |<span data-ttu-id="8ba4b-225">Программное\\обеспечение\\\\Microsoft Office Lync</span><span class="sxs-lookup"><span data-stu-id="8ba4b-225">Software\\Microsoft\\Office\\Lync</span></span>  <br/> |
|<span data-ttu-id="8ba4b-226">**Имя значения**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-226">**Value name**</span></span> <br/> |<span data-ttu-id="8ba4b-227">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="8ba4b-227">EnableSkypeUI</span></span>  <br/> |
|<span data-ttu-id="8ba4b-228">**Тип значения**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-228">**Value type**</span></span> <br/> |<span data-ttu-id="8ba4b-229">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="8ba4b-229">REG_BINARY</span></span>  <br/> |
|<span data-ttu-id="8ba4b-230">**Данные значения**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-230">**Value data**</span></span> <br/> |<span data-ttu-id="8ba4b-231">00000001</span><span class="sxs-lookup"><span data-stu-id="8ba4b-231">00000000</span></span>  <br/> |
   
<span data-ttu-id="8ba4b-232">Нажмите кнопку **OK**, чтобы сохранить изменения, затем закройте объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-232">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="8ba4b-233">Далее следует связать созданный объект групповой политики с группой пользователей, которым необходимо назначить политику, например, с подразделением.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-233">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
 <span data-ttu-id="8ba4b-234">**Назначение политики с помощью объекта групповой политики**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-234">**To use the GPO to assign the policy**</span></span>
  
1. <span data-ttu-id="8ba4b-235">В консоли управления групповыми политиками щелкните правой кнопкой мыши на подразделении, которому необходимо назначить групповую политику, и выберите **Связать с существующим объектом групповой политики**.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-235">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="8ba4b-236">В диалоговом окне **Выбор объекта групповой политики** выберите созданный объект групповой политики и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-236">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="8ba4b-237">На целевом компьютере пользователя откройте командную строку и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-237">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="8ba4b-238">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-238">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="8ba4b-p117">При применении объекта групповой политики отобразится сообщение "Обновление политики...". После завершения обновления отобразится сообщение "Обновление политики пользователя завершено успешно".</span><span class="sxs-lookup"><span data-stu-id="8ba4b-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="8ba4b-241">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8ba4b-241">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="8ba4b-242">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="8ba4b-242">**gpresult /r**</span></span>
    
    <span data-ttu-id="8ba4b-243">Ниже отобразится список назначенных объектов групповой политики с именем созданного объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-243">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="8ba4b-p118">Также можно проверить успешное обновление реестра объектом групповой политики на компьютере пользователя, изучив реестр. Откройте редактор реестра и найдите строку **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Если объект групповой политики успешно обновил реестр, будет отображаться значение с именем EnableSkypeUI и значением 0.</span><span class="sxs-lookup"><span data-stu-id="8ba4b-p118">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8ba4b-247">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8ba4b-247">Related topics</span></span>
[<span data-ttu-id="8ba4b-248">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8ba4b-248">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="8ba4b-249">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8ba4b-249">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
