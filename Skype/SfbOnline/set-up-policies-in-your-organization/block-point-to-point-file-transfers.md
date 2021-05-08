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
description: В Skype для бизнеса Online вы можете управлять передачей файлов "точка-точка" (P2P) в рамках существующих параметров политики веб-услуг. Однако это позволяет или блокирует передачу файлов для пользователей независимо от того, передают ли они файлы пользователю, который находится в той же организации, или федераированному пользователю из другой организации. Вы можете заблокировать передачу файлов P2P федера организации или партнерам.
ms.openlocfilehash: e20cf0d5ff7a884e81fe2ee5de57ed026c53552e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240178"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="edd38-105">Блокировка передачи файлов точка-точка</span><span class="sxs-lookup"><span data-stu-id="edd38-105">Block Point-to-Point file transfers</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="edd38-106">В Skype для бизнеса Online вы можете управлять передачей файлов "точка-точка" (P2P) в рамках существующих параметров политики веб-услуг.</span><span class="sxs-lookup"><span data-stu-id="edd38-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="edd38-107">Однако это позволяет или блокирует передачу файлов для пользователей независимо от того, передают ли они файлы пользователю, который находится в той же организации, или федераированному пользователю из другой организации.</span><span class="sxs-lookup"><span data-stu-id="edd38-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="edd38-108">Вы можете заблокировать передачу файлов P2P федера организации или партнерам.</span><span class="sxs-lookup"><span data-stu-id="edd38-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="edd38-109">Очень распространенный сценарий — разрешить внутренним пользователям использовать передачу P2P-файлов, но заблокировать передачу файлов федератов.</span><span class="sxs-lookup"><span data-stu-id="edd38-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="edd38-110">Для этого сценария вам потребуется сделать:</span><span class="sxs-lookup"><span data-stu-id="edd38-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="edd38-111">Назначьте политику conferencing, включив передачу P2P-файлов _(EnableP2PFileTransfer_ для _true)_ для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="edd38-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="edd38-112">Создайте глобальный набор политики связи с внешними пользователями, чтобы заблокировать передачу внешних P2P-файлов _(EnableP2PFileTransfer_ с инициативой _False)_ и назначьте ее пользователю в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="edd38-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="edd38-113">Дополнительные информацию об этих параметрах можно [найти](/previous-versions//mt228132(v=technet.10))здесь.</span><span class="sxs-lookup"><span data-stu-id="edd38-113">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="edd38-114">Если федераированный пользователь за пределами организации попытается отправить файл пользователю, в котором была применена политика, он получит сообщение об ошибке Перенос **с ошибкой.**</span><span class="sxs-lookup"><span data-stu-id="edd38-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="edd38-115">А если пользователь попытается отправить файл, он получит сообщение об ошибке Передачу **файла.**</span><span class="sxs-lookup"><span data-stu-id="edd38-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="edd38-116">Для этого пользователю необходимо использовать поддерживаемую версию приложения "нажми и работай" версии 2016 Skype для бизнеса, которое ее поддерживает.</span><span class="sxs-lookup"><span data-stu-id="edd38-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="edd38-117">Требуется следующая минимальная версия Skype для бизнеса версии 2016 "нажми и работы":</span><span class="sxs-lookup"><span data-stu-id="edd38-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="edd38-118">**Тип**</span><span class="sxs-lookup"><span data-stu-id="edd38-118">**Type**</span></span>|<span data-ttu-id="edd38-119">**Дата выпуска**</span><span class="sxs-lookup"><span data-stu-id="edd38-119">**Release date**</span></span>|<span data-ttu-id="edd38-120">**Версия**</span><span class="sxs-lookup"><span data-stu-id="edd38-120">**Version**</span></span>|<span data-ttu-id="edd38-121">**Построить**</span><span class="sxs-lookup"><span data-stu-id="edd38-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="edd38-122">First Release for Current Channel</span><span class="sxs-lookup"><span data-stu-id="edd38-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="edd38-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="edd38-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="edd38-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="edd38-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="edd38-125">Версия 1611 (сборка 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="edd38-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="edd38-126">Current Channel</span><span class="sxs-lookup"><span data-stu-id="edd38-126">Current Channel</span></span>  <br/> |<span data-ttu-id="edd38-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="edd38-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="edd38-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="edd38-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="edd38-129">Версия 1611 (сборка 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="edd38-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="edd38-130">Deferred Channel</span><span class="sxs-lookup"><span data-stu-id="edd38-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="edd38-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="edd38-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="edd38-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="edd38-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="edd38-133">Версия 1609 (сборка 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="edd38-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="edd38-134">Пользователи, использующие более старые версии Skype для бизнеса Windows приложений или клиентов Mac, по-прежнему смогут передавать файлы.</span><span class="sxs-lookup"><span data-stu-id="edd38-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="edd38-135">Начните Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="edd38-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="edd38-136">Skype для бизнеса В настоящее время Online Connector является частью последней версии Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="edd38-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="edd38-137">Если вы используете последний общедоступный Teams PowerShell, вам не нужно устанавливать Skype для бизнеса Online Connector.</span><span class="sxs-lookup"><span data-stu-id="edd38-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="edd38-138">Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="edd38-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="edd38-139">Откройте Windows PowerShell командную команду и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="edd38-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="edd38-140">Дополнительные сведения о запуске Windows PowerShell см. в Подключение всех службах Microsoft 365 или [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или Настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="edd38-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="edd38-141">Отключение переноса P2P-файлов для организации</span><span class="sxs-lookup"><span data-stu-id="edd38-141">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="edd38-142">По умолчанию _enableP2PFileTransfer_ включен в глобальной политике организации.</span><span class="sxs-lookup"><span data-stu-id="edd38-142">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="edd38-143">При ее создания пользователям была назначена политика _BposSAllModality._</span><span class="sxs-lookup"><span data-stu-id="edd38-143">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="edd38-144">Чтобы разрешить передачу P2P внутри организации, но заблокировать передачу внешних файлов в другую организацию, достаточно изменить ее на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="edd38-144">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="edd38-145">Для этого запустите:</span><span class="sxs-lookup"><span data-stu-id="edd38-145">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="edd38-146">Отключение передачи P2P-файлов для пользователя</span><span class="sxs-lookup"><span data-stu-id="edd38-146">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="edd38-147">Вы можете применить эту политику к пользователю, создав новую политику и надав ее этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="edd38-147">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="edd38-148">Для этого запустите:</span><span class="sxs-lookup"><span data-stu-id="edd38-148">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="edd38-149">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="edd38-149">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="edd38-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="edd38-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="edd38-151">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="edd38-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="edd38-152">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="edd38-152">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="edd38-153">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="edd38-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="edd38-154">Зачем нужна Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="edd38-154">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="edd38-155">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="edd38-155">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="edd38-156">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="edd38-156">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="edd38-157">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="edd38-157">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="edd38-158">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="edd38-158">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="edd38-159">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="edd38-159">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="edd38-160">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="edd38-160">Related topics</span></span>
[<span data-ttu-id="edd38-161">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="edd38-161">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="edd38-162">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="edd38-162">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="edd38-163">Настройка политик conferencing в организации</span><span class="sxs-lookup"><span data-stu-id="edd38-163">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
