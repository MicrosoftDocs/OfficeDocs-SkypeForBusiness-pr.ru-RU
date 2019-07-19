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
f1keywords: None
ms.custom:
- Setup
description: Skype для бизнеса Online позволяет создавать дополнительные политики внешнего доступа. В отличие от политик клиентов и конференций, где вы можете использовать несколько сочетаний, есть три стандартные политики внешнего доступа, которые могут охватывать большинство сценариев.
ms.openlocfilehash: 7f3edac77af8d9948ef7118c0f94b1ec9c3ae6c1
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792488"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="bd659-104">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="bd659-104">Create custom external access policies</span></span>

<span data-ttu-id="bd659-105">Skype для бизнеса Online позволяет создавать дополнительные политики внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="bd659-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="bd659-106">В отличие от политик клиентов и конференций, где вы можете использовать несколько сочетаний, есть три стандартные политики внешнего доступа, которые могут охватывать большинство сценариев.</span><span class="sxs-lookup"><span data-stu-id="bd659-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="bd659-107">Ниже указаны указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="bd659-107">These are:</span></span>
  
- <span data-ttu-id="bd659-108">Нет доступа к Федеративной или Skype для потребителей (_тег: нофедератионандпик_ )</span><span class="sxs-lookup"><span data-stu-id="bd659-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="bd659-109">Только для федеративного доступа (_Tag: федератиононли_ )</span><span class="sxs-lookup"><span data-stu-id="bd659-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="bd659-110">Федеративные и доступ к потребителям (_федератионандпикдефаулт_)</span><span class="sxs-lookup"><span data-stu-id="bd659-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="bd659-111">Пользовательские внешние политики позволяют создавать дополнительные политики, не охваченные приведенными выше параметрами.</span><span class="sxs-lookup"><span data-stu-id="bd659-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="bd659-112">После создания политики вам потребуется настроить все необходимые параметры, и вы не сможете изменить их позже.</span><span class="sxs-lookup"><span data-stu-id="bd659-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="bd659-113">Создание настраиваемых политик позволяет управлять такими функциями, как доступ к потребителю Skype или политика для отключения общедоступного облака аудио-и видеофайлов, что не было охвачено предопределенными параметрами.</span><span class="sxs-lookup"><span data-stu-id="bd659-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="bd659-114">Пользовательские политики внешнего доступа следуют тем же синтаксису, что и политики клиента, мобильных устройств и конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="bd659-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="bd659-115">Дополнительные сведения об этих параметрах можно найти [здесь](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="bd659-115">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="bd659-116">Для выполнения этой задачи пользователю необходима поддерживаемая версия 2016 "нажми и работай" приложения Skype для бизнеса, поддерживающего это приложение.</span><span class="sxs-lookup"><span data-stu-id="bd659-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="bd659-117">Требуется следующая минимальная версия клиента "нажми и работай" Skype для бизнеса 2016:</span><span class="sxs-lookup"><span data-stu-id="bd659-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="bd659-118">**Тип**</span><span class="sxs-lookup"><span data-stu-id="bd659-118">**Type**</span></span>|<span data-ttu-id="bd659-119">**Дата выпуска**</span><span class="sxs-lookup"><span data-stu-id="bd659-119">**Release date**</span></span>|<span data-ttu-id="bd659-120">**Версия**</span><span class="sxs-lookup"><span data-stu-id="bd659-120">**Version**</span></span>|<span data-ttu-id="bd659-121">**Разработки**</span><span class="sxs-lookup"><span data-stu-id="bd659-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd659-122">Первый выпуск для текущего канала</span><span class="sxs-lookup"><span data-stu-id="bd659-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="bd659-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="bd659-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="bd659-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="bd659-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="bd659-125">Версия 1611 (сборка 7571,2006)</span><span class="sxs-lookup"><span data-stu-id="bd659-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="bd659-126">Текущий канал</span><span class="sxs-lookup"><span data-stu-id="bd659-126">Current Channel</span></span>  <br/> |<span data-ttu-id="bd659-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="bd659-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="bd659-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="bd659-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="bd659-129">Версия 1611 (сборка 7571,2072)</span><span class="sxs-lookup"><span data-stu-id="bd659-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="bd659-130">Отложенный канал</span><span class="sxs-lookup"><span data-stu-id="bd659-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="bd659-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="bd659-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="bd659-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="bd659-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="bd659-133">Версия 1609 (сборка 7369,2118)</span><span class="sxs-lookup"><span data-stu-id="bd659-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="bd659-134">Пользователи, использующие более ранние версии приложений Skype для бизнеса для Windows или Mac, по-прежнему смогут передавать файлы.</span><span class="sxs-lookup"><span data-stu-id="bd659-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="bd659-135">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd659-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="bd659-136">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="bd659-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="bd659-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bd659-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="bd659-138">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="bd659-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="bd659-139">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd659-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="bd659-140">Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) .</span><span class="sxs-lookup"><span data-stu-id="bd659-140">See [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="bd659-141">При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="bd659-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="bd659-p106">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="bd659-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="bd659-145">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="bd659-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="bd659-146">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="bd659-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="bd659-147">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bd659-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="bd659-148">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bd659-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bd659-149">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="bd659-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="bd659-150">Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [Настройка компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="bd659-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="bd659-151">Создание настраиваемой политики внешнего доступа для пользователя</span><span class="sxs-lookup"><span data-stu-id="bd659-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="bd659-152">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="bd659-152">To do this, run:</span></span>
  
> 
>   ```
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bd659-153">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bd659-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="bd659-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="bd659-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bd659-155">С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="bd659-155">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="bd659-156">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="bd659-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bd659-157">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="bd659-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bd659-158">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="bd659-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="bd659-159">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="bd659-159">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="bd659-160">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="bd659-160">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="bd659-161">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd659-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="bd659-162">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="bd659-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bd659-163">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="bd659-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="bd659-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bd659-164">Related topics</span></span>
[<span data-ttu-id="bd659-165">Блокировка передачи файлов между точками</span><span class="sxs-lookup"><span data-stu-id="bd659-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="bd659-166">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="bd659-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="bd659-167">Настройка политик конференц-связи в Организации</span><span class="sxs-lookup"><span data-stu-id="bd659-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
