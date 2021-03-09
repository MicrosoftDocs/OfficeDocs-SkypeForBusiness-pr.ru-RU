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
description: Skype для бизнеса Online позволяет создавать дополнительные политики внешнего доступа. В отличие от политик клиента или conferencing, где можно использовать несколько комбинаций, существует три предопределенной политики внешнего доступа, которые могут охватывать большинство сценариев.
ms.openlocfilehash: 22477a54e0c709aa1c01bcfbd6c3bd6aacbb02e0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569135"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="21deb-104">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="21deb-104">Create custom external access policies</span></span>

<span data-ttu-id="21deb-105">Skype для бизнеса Online позволяет создавать дополнительные политики внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="21deb-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="21deb-106">В отличие от политик клиента или conferencing, где можно использовать несколько комбинаций, существует три предопределенной политики внешнего доступа, которые могут охватывать большинство сценариев.</span><span class="sxs-lookup"><span data-stu-id="21deb-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="21deb-107">Это:</span><span class="sxs-lookup"><span data-stu-id="21deb-107">These are:</span></span>
  
- <span data-ttu-id="21deb-108">Нет федераций или потребительского доступа Skype _(Tag:NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="21deb-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="21deb-109">Только федераированный доступ _(Tag:FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="21deb-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="21deb-110">Federated and Consumer Access _(FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="21deb-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="21deb-111">Настраиваемые внешние политики позволяют создавать дополнительные политики, не влияемые на параметры выше.</span><span class="sxs-lookup"><span data-stu-id="21deb-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="21deb-112">После создания политики вам потребуется настроить все необходимые параметры и изменить их позднее будет невозможно.</span><span class="sxs-lookup"><span data-stu-id="21deb-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="21deb-113">Создание настраиваемых политик позволяет управлять такими функциями, как доступ к skype для потребителей или политика отключения общедоступных облачных аудио- и видеофайлов (то есть неопределяемых параметров).</span><span class="sxs-lookup"><span data-stu-id="21deb-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="21deb-114">Настраиваемые политики внешнего доступа придерживаются того же синтаксиса, что и политики клиента, мобильности и conferencing.</span><span class="sxs-lookup"><span data-stu-id="21deb-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="21deb-115">Дополнительные информацию об этих параметрах можно [найти](https://technet.microsoft.com/library/mt228132.aspx)здесь.</span><span class="sxs-lookup"><span data-stu-id="21deb-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="21deb-116">Для этой работы пользователь должен использовать поддерживаемую версию приложения Skype для бизнеса версии 2016 "нажми и работай", которая ее поддерживает.</span><span class="sxs-lookup"><span data-stu-id="21deb-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="21deb-117">Необходима следующая минимальная версия клиента Skype для бизнеса 2016 "нажми и работы":</span><span class="sxs-lookup"><span data-stu-id="21deb-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="21deb-118">**Тип**</span><span class="sxs-lookup"><span data-stu-id="21deb-118">**Type**</span></span>|<span data-ttu-id="21deb-119">**Дата выпуска**</span><span class="sxs-lookup"><span data-stu-id="21deb-119">**Release date**</span></span>|<span data-ttu-id="21deb-120">**Версия**</span><span class="sxs-lookup"><span data-stu-id="21deb-120">**Version**</span></span>|<span data-ttu-id="21deb-121">**Сборка**</span><span class="sxs-lookup"><span data-stu-id="21deb-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="21deb-122">First Release for Current Channel</span><span class="sxs-lookup"><span data-stu-id="21deb-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="21deb-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="21deb-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="21deb-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="21deb-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="21deb-125">Версия 1611 (сборка 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="21deb-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="21deb-126">Current Channel</span><span class="sxs-lookup"><span data-stu-id="21deb-126">Current Channel</span></span>  <br/> |<span data-ttu-id="21deb-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="21deb-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="21deb-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="21deb-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="21deb-129">Версия 1611 (сборка 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="21deb-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="21deb-130">Deferred Channel</span><span class="sxs-lookup"><span data-stu-id="21deb-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="21deb-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="21deb-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="21deb-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="21deb-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="21deb-133">Версия 1609 (сборка 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="21deb-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="21deb-134">Пользователи, которые используют более старые версии приложений Skype для бизнеса для Windows или клиентов Mac, по-прежнему смогут передавать файлы.</span><span class="sxs-lookup"><span data-stu-id="21deb-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="21deb-135">Начать Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="21deb-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="21deb-136">Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21deb-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="21deb-137">Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="21deb-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="21deb-138">Установите модуль [Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="21deb-138">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="21deb-139">Откройте Windows PowerShell и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="21deb-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="21deb-140">Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21deb-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="21deb-141">Создание настраиваемой политики внешнего доступа для пользователя</span><span class="sxs-lookup"><span data-stu-id="21deb-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="21deb-142">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="21deb-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="21deb-143">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="21deb-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="21deb-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="21deb-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="21deb-145">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="21deb-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="21deb-146">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="21deb-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="21deb-147">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="21deb-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="21deb-148">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="21deb-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="21deb-149">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="21deb-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="21deb-150">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="21deb-150">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="21deb-151">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="21deb-151">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="21deb-152">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="21deb-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="21deb-153">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="21deb-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="21deb-154">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="21deb-154">Related topics</span></span>
[<span data-ttu-id="21deb-155">Блокировать передачу файлов по точкам</span><span class="sxs-lookup"><span data-stu-id="21deb-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="21deb-156">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="21deb-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="21deb-157">Настройка политик для организации</span><span class="sxs-lookup"><span data-stu-id="21deb-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
