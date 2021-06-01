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
description: Skype для бизнеса В Интернете можно создавать дополнительные политики внешнего доступа. В отличие от политик клиента или conferencing, где можно использовать несколько комбинаций, существует три предопределенной политики внешнего доступа, которые могут охватывать большинство сценариев.
ms.openlocfilehash: f9d99789bdb400cee9b7597bfcdc4079c1d3612d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240148"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="5f533-104">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="5f533-104">Create custom external access policies</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="5f533-105">Skype для бизнеса В Интернете можно создавать дополнительные политики внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="5f533-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="5f533-106">В отличие от политик клиента или conferencing, где можно использовать несколько комбинаций, существует три предопределенной политики внешнего доступа, которые могут охватывать большинство сценариев.</span><span class="sxs-lookup"><span data-stu-id="5f533-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="5f533-107">Это:</span><span class="sxs-lookup"><span data-stu-id="5f533-107">These are:</span></span>
  
- <span data-ttu-id="5f533-108">Нет федераций и Skype доступа для потребителей (_Tag:NoFederationAndpIC_ )</span><span class="sxs-lookup"><span data-stu-id="5f533-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="5f533-109">Только федераированный доступ (_Tag:FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="5f533-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="5f533-110">Federated and Consumer Access _(FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="5f533-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="5f533-111">Настраиваемые внешние политики позволяют создавать дополнительные политики, которые не охватывают параметры выше.</span><span class="sxs-lookup"><span data-stu-id="5f533-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="5f533-112">После создания политики вам потребуется настроить все необходимые параметры, и вы не сможете изменить их позже.</span><span class="sxs-lookup"><span data-stu-id="5f533-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="5f533-113">Создание новых настраиваемых политик позволяет управлять такими функциями, как доступ Skype или политика для отключения общедоступных облачных аудио- и видеофайлов , которые не были заранее озвучиты.</span><span class="sxs-lookup"><span data-stu-id="5f533-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="5f533-114">Настраиваемые политики внешнего доступа имеют тот же синтаксис, что и политики клиентского, мобильного доступа иконок.</span><span class="sxs-lookup"><span data-stu-id="5f533-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="5f533-115">Дополнительные информацию об этих параметрах можно [найти](/previous-versions//mt228132(v=technet.10))здесь.</span><span class="sxs-lookup"><span data-stu-id="5f533-115">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="5f533-116">Для этого пользователю необходимо использовать поддерживаемую версию версии 2016 "нажми и работай" Skype для бизнеса, которая ее поддерживает.</span><span class="sxs-lookup"><span data-stu-id="5f533-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="5f533-117">Требуется следующая минимальная версия клиента Skype для бизнеса версии 2016 "нажми и работы":</span><span class="sxs-lookup"><span data-stu-id="5f533-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="5f533-118">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5f533-118">**Type**</span></span>|<span data-ttu-id="5f533-119">**Дата выпуска**</span><span class="sxs-lookup"><span data-stu-id="5f533-119">**Release date**</span></span>|<span data-ttu-id="5f533-120">**Версия**</span><span class="sxs-lookup"><span data-stu-id="5f533-120">**Version**</span></span>|<span data-ttu-id="5f533-121">**Построить**</span><span class="sxs-lookup"><span data-stu-id="5f533-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f533-122">First Release for Current Channel</span><span class="sxs-lookup"><span data-stu-id="5f533-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="5f533-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="5f533-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="5f533-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="5f533-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="5f533-125">Версия 1611 (сборка 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="5f533-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="5f533-126">Current Channel</span><span class="sxs-lookup"><span data-stu-id="5f533-126">Current Channel</span></span>  <br/> |<span data-ttu-id="5f533-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="5f533-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="5f533-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="5f533-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="5f533-129">Версия 1611 (сборка 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="5f533-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="5f533-130">Deferred Channel</span><span class="sxs-lookup"><span data-stu-id="5f533-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="5f533-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="5f533-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="5f533-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="5f533-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="5f533-133">Версия 1609 (сборка 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="5f533-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="5f533-134">Пользователи, использующие более старые версии Skype для бизнеса Windows приложений или клиентов Mac, по-прежнему смогут передавать файлы.</span><span class="sxs-lookup"><span data-stu-id="5f533-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="5f533-135">Начните Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f533-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="5f533-136">Skype для бизнеса Online Connector в настоящее время является частью последней версии Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f533-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="5f533-137">Если вы используете последнюю версию Teams PowerShell, вам не нужно устанавливать Skype для бизнеса Online Connector.</span><span class="sxs-lookup"><span data-stu-id="5f533-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="5f533-138">Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="5f533-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="5f533-139">Откройте Windows PowerShell командную команду и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="5f533-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="5f533-140">Дополнительные сведения о запуске Windows PowerShell см. в Подключение всех службах Microsoft 365 или [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или Настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f533-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="5f533-141">Создание настраиваемой политики внешнего доступа для пользователя</span><span class="sxs-lookup"><span data-stu-id="5f533-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="5f533-142">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="5f533-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5f533-143">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5f533-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="5f533-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="5f533-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5f533-145">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="5f533-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5f533-146">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="5f533-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5f533-147">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5f533-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5f533-148">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f533-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="5f533-149">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="5f533-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5f533-150">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="5f533-150">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="5f533-151">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5f533-151">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="5f533-152">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5f533-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5f533-153">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5f533-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="5f533-154">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5f533-154">Related topics</span></span>
[<span data-ttu-id="5f533-155">Блокировка передачи файлов по точкам</span><span class="sxs-lookup"><span data-stu-id="5f533-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="5f533-156">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="5f533-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="5f533-157">Настройка политик conferencing в организации</span><span class="sxs-lookup"><span data-stu-id="5f533-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
