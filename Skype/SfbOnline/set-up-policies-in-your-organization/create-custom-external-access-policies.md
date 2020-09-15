---
title: Создание настраиваемых политик внешнего доступа
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
- Setup
description: Skype для бизнеса Online позволяет создавать дополнительные политики внешнего доступа. В отличие от политик клиентов и конференций, где вы можете использовать несколько сочетаний, есть три стандартные политики внешнего доступа, которые могут охватывать большинство сценариев.
ms.openlocfilehash: 9ec8fbe2e2d1a0d0882a0115bb201021fbbc1a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814198"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="9bed6-104">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="9bed6-104">Create custom external access policies</span></span>

<span data-ttu-id="9bed6-105">Skype для бизнеса Online позволяет создавать дополнительные политики внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="9bed6-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="9bed6-106">В отличие от политик клиентов и конференций, где вы можете использовать несколько сочетаний, есть три стандартные политики внешнего доступа, которые могут охватывать большинство сценариев.</span><span class="sxs-lookup"><span data-stu-id="9bed6-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="9bed6-107">Ниже указаны указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="9bed6-107">These are:</span></span>
  
- <span data-ttu-id="9bed6-108">Нет доступа к Федеративной или Skype для потребителей (_тег: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="9bed6-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="9bed6-109">Только для федеративного доступа (_Tag: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="9bed6-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="9bed6-110">Федеративные и доступ к потребителям (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="9bed6-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="9bed6-111">Пользовательские внешние политики позволяют создавать дополнительные политики, не охваченные приведенными выше параметрами.</span><span class="sxs-lookup"><span data-stu-id="9bed6-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="9bed6-112">После создания политики вам потребуется настроить все необходимые параметры, и вы не сможете изменить их позже.</span><span class="sxs-lookup"><span data-stu-id="9bed6-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="9bed6-113">Создание настраиваемых политик позволяет управлять такими функциями, как доступ к потребителю Skype или политика для отключения общедоступного облака аудио-и видеофайлов, что не было охвачено предопределенными параметрами.</span><span class="sxs-lookup"><span data-stu-id="9bed6-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="9bed6-114">Пользовательские политики внешнего доступа следуют тем же синтаксису, что и политики клиента, мобильных устройств и конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="9bed6-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="9bed6-115">Дополнительные сведения об этих параметрах можно найти [здесь](https://technet.microsoft.com/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bed6-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="9bed6-116">Для выполнения этой задачи пользователю необходима поддерживаемая версия 2016 "нажми и работай" приложения Skype для бизнеса, поддерживающего это приложение.</span><span class="sxs-lookup"><span data-stu-id="9bed6-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="9bed6-117">Требуется следующая минимальная версия клиента "нажми и работай" Skype для бизнеса 2016:</span><span class="sxs-lookup"><span data-stu-id="9bed6-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="9bed6-118">**Тип**</span><span class="sxs-lookup"><span data-stu-id="9bed6-118">**Type**</span></span>|<span data-ttu-id="9bed6-119">**Дата выпуска**</span><span class="sxs-lookup"><span data-stu-id="9bed6-119">**Release date**</span></span>|<span data-ttu-id="9bed6-120">**Версия**</span><span class="sxs-lookup"><span data-stu-id="9bed6-120">**Version**</span></span>|<span data-ttu-id="9bed6-121">**Разработки**</span><span class="sxs-lookup"><span data-stu-id="9bed6-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9bed6-122">Первый выпуск для текущего канала</span><span class="sxs-lookup"><span data-stu-id="9bed6-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="9bed6-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="9bed6-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="9bed6-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="9bed6-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="9bed6-125">Версия 1611 (сборка 7571,2006)</span><span class="sxs-lookup"><span data-stu-id="9bed6-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="9bed6-126">Текущий канал</span><span class="sxs-lookup"><span data-stu-id="9bed6-126">Current Channel</span></span>  <br/> |<span data-ttu-id="9bed6-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="9bed6-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="9bed6-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="9bed6-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="9bed6-129">Версия 1611 (сборка 7571,2072)</span><span class="sxs-lookup"><span data-stu-id="9bed6-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="9bed6-130">Отложенный канал</span><span class="sxs-lookup"><span data-stu-id="9bed6-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="9bed6-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="9bed6-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="9bed6-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="9bed6-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="9bed6-133">Версия 1609 (сборка 7369,2118)</span><span class="sxs-lookup"><span data-stu-id="9bed6-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="9bed6-134">Пользователи, использующие более ранние версии приложений Skype для бизнеса для Windows или Mac, по-прежнему смогут передавать файлы.</span><span class="sxs-lookup"><span data-stu-id="9bed6-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="9bed6-135">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bed6-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="9bed6-136">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="9bed6-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="9bed6-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9bed6-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9bed6-138">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="9bed6-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="9bed6-139">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9bed6-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="9bed6-140">Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://www.microsoft.com/download/details.aspx?id=40855) .</span><span class="sxs-lookup"><span data-stu-id="9bed6-140">See [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="9bed6-141">При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="9bed6-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="9bed6-142">Кроме того, вам потребуется установить модуль Windows PowerShell для Teams, который позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="9bed6-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="9bed6-143">Дополнительные сведения можно найти в разделе [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="9bed6-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="9bed6-144">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9bed6-144">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="9bed6-145">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9bed6-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9bed6-146">В окне **Windows PowerShell** подключитесь к службе Microsoft 365 или Office 365, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9bed6-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="9bed6-147">Skype для бизнеса Online уже входит в состав последнего модуля PowerShell для Teams.</span><span class="sxs-lookup"><span data-stu-id="9bed6-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="9bed6-148">Если вы используете последнюю версию [общедоступной оболочки для Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="9bed6-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business  Online Connector.</span></span>

   ```PowerShell      
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="9bed6-149">Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или [Настройка компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="9bed6-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="9bed6-150">Создание настраиваемой политики внешнего доступа для пользователя</span><span class="sxs-lookup"><span data-stu-id="9bed6-150">Create a custom external access policy for a user</span></span>

<span data-ttu-id="9bed6-151">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="9bed6-151">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9bed6-152">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9bed6-152">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="9bed6-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="9bed6-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9bed6-154">С помощью Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач.</span><span class="sxs-lookup"><span data-stu-id="9bed6-154">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9bed6-155">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="9bed6-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9bed6-156">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9bed6-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="9bed6-157">Зачем использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bed6-157">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="9bed6-158">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="9bed6-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9bed6-159">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9bed6-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="9bed6-160">Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bed6-160">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="9bed6-161">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9bed6-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9bed6-162">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9bed6-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="9bed6-163">См. также</span><span class="sxs-lookup"><span data-stu-id="9bed6-163">Related topics</span></span>
[<span data-ttu-id="9bed6-164">Блокировка передачи файлов между точками</span><span class="sxs-lookup"><span data-stu-id="9bed6-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="9bed6-165">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="9bed6-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="9bed6-166">Настройка политик конференц-связи в Организации</span><span class="sxs-lookup"><span data-stu-id="9bed6-166">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
