---
title: Блокировка передачи файлов точка-точка
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: В Skype для бизнеса Online вы можете управлять передачей файлов точка-точка (P2P) в рамках существующих параметров политики веб-услуг. Однако это позволяет или блокирует передачу файлов пользователям вне зависимости от того, передают ли они файлы пользователю, который находится в той же организации, или федерален пользователю из другой организации. Вы можете заблокировать передачу файлов P2P федера организации или партнерам, вы предприняв действия ниже.
ms.openlocfilehash: e2a0bb2f250f89433c09566197df7a56efa7f64f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100625"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="8399b-105">Блокировка передачи файлов точка-точка</span><span class="sxs-lookup"><span data-stu-id="8399b-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="8399b-106">В Skype для бизнеса Online вы можете управлять передачей файлов точка-точка (P2P) как часть существующих параметров политики веб-услуг.</span><span class="sxs-lookup"><span data-stu-id="8399b-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="8399b-107">Однако при этом для пользователей разрешается или блокируется передача файлов независимо от того, передаются ли они пользователям, которые находятся в той же организации или федератном пользователе из другой организации.</span><span class="sxs-lookup"><span data-stu-id="8399b-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="8399b-108">Вы можете заблокировать передачу файлов P2P федера организации или партнерам, вы предприняв действия ниже.</span><span class="sxs-lookup"><span data-stu-id="8399b-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="8399b-109">Очень распространенный сценарий — разрешить внутренним пользователям использовать передачу файлов P2P, но заблокировать передачу файлов федератным партнерам.</span><span class="sxs-lookup"><span data-stu-id="8399b-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="8399b-110">В этом сценарии вам потребуется сделать:</span><span class="sxs-lookup"><span data-stu-id="8399b-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="8399b-111">Назначьте политику conferencing с включенным переносом P2P-файлов _(EnableP2PFileTransfer_ set to _True)_ пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8399b-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="8399b-112">Создайте глобальный набор внешней политики связи пользователей, задав для блокировки передачи внешних P2P-файлов _(EnableP2PFileTransfer_ задайте для этого _false)_ и назначьте ее пользователю в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8399b-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="8399b-113">Дополнительные информацию об этих параметрах можно [найти](/previous-versions//mt228132(v=technet.10))здесь.</span><span class="sxs-lookup"><span data-stu-id="8399b-113">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="8399b-114">Если федераированный пользователь за пределами вашей организации попытается отправить файл пользователю, к котором применена политика, он получит сообщение об ошибке с ошибкой **передачи.**</span><span class="sxs-lookup"><span data-stu-id="8399b-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="8399b-115">Если пользователь попытается отправить файл, он получит сообщение об ошибке "Передача **файла отключена".**</span><span class="sxs-lookup"><span data-stu-id="8399b-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="8399b-116">Для этой работы пользователь должен использовать поддерживаемую версию приложения Skype для бизнеса версии 2016 "нажми и работай", которая ее поддерживает.</span><span class="sxs-lookup"><span data-stu-id="8399b-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="8399b-117">Необходима следующая минимальная версия клиента Skype для бизнеса 2016 "нажми и работы":</span><span class="sxs-lookup"><span data-stu-id="8399b-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="8399b-118">**Тип**</span><span class="sxs-lookup"><span data-stu-id="8399b-118">**Type**</span></span>|<span data-ttu-id="8399b-119">**Дата выпуска**</span><span class="sxs-lookup"><span data-stu-id="8399b-119">**Release date**</span></span>|<span data-ttu-id="8399b-120">**Версия**</span><span class="sxs-lookup"><span data-stu-id="8399b-120">**Version**</span></span>|<span data-ttu-id="8399b-121">**Сборка**</span><span class="sxs-lookup"><span data-stu-id="8399b-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8399b-122">First Release for Current Channel</span><span class="sxs-lookup"><span data-stu-id="8399b-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="8399b-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="8399b-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="8399b-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="8399b-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="8399b-125">Версия 1611 (сборка 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="8399b-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="8399b-126">Current Channel</span><span class="sxs-lookup"><span data-stu-id="8399b-126">Current Channel</span></span>  <br/> |<span data-ttu-id="8399b-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="8399b-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="8399b-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="8399b-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="8399b-129">Версия 1611 (сборка 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="8399b-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="8399b-130">Deferred Channel</span><span class="sxs-lookup"><span data-stu-id="8399b-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="8399b-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="8399b-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="8399b-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="8399b-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="8399b-133">Версия 1609 (сборка 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="8399b-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="8399b-134">Пользователи, которые используют более старые версии приложений Skype для бизнеса для Windows или клиентов Mac, по-прежнему смогут передавать файлы.</span><span class="sxs-lookup"><span data-stu-id="8399b-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="8399b-135">Начать Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8399b-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="8399b-136">Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8399b-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="8399b-137">Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="8399b-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="8399b-138">Установите модуль [Teams PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="8399b-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="8399b-139">Откройте Windows PowerShell и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="8399b-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="8399b-140">Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8399b-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="8399b-141">Отключение передач P2P-файлов для организации</span><span class="sxs-lookup"><span data-stu-id="8399b-141">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="8399b-142">По умолчанию _enableP2PFileTransfer_ включена в глобальной политике организации.</span><span class="sxs-lookup"><span data-stu-id="8399b-142">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="8399b-143">После создания пользователю была назначена политика _BposSAllModality._</span><span class="sxs-lookup"><span data-stu-id="8399b-143">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="8399b-144">Чтобы разрешить передачу P2P-файлов внутри организации, но заблокировать передачу внешних файлов в другую организацию, достаточно изменить ее на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="8399b-144">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="8399b-145">Для этого запустите 3</span><span class="sxs-lookup"><span data-stu-id="8399b-145">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="8399b-146">Отключение передачи файлов P2P для пользователя</span><span class="sxs-lookup"><span data-stu-id="8399b-146">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="8399b-147">Вы можете применить эту политику к пользователю, создав новую политику и надав ее этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="8399b-147">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="8399b-148">Для этого запустите 3</span><span class="sxs-lookup"><span data-stu-id="8399b-148">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="8399b-149">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="8399b-149">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="8399b-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="8399b-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8399b-151">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="8399b-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="8399b-152">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="8399b-152">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8399b-153">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8399b-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="8399b-154">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8399b-154">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="8399b-155">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="8399b-155">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="8399b-156">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="8399b-156">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="8399b-157">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="8399b-157">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="8399b-158">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8399b-158">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="8399b-159">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8399b-159">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="8399b-160">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8399b-160">Related topics</span></span>
[<span data-ttu-id="8399b-161">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="8399b-161">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="8399b-162">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="8399b-162">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="8399b-163">Настройка политик для организации</span><span class="sxs-lookup"><span data-stu-id="8399b-163">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
