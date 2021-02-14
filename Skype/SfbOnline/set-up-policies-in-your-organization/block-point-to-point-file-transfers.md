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
description: В Skype для бизнеса Online вы можете управлять передачей файлов точка-точка (P2P) в рамках существующих параметров политики веб-услуг. Однако при этом для пользователей разрешается или блокируется передача файлов независимо от того, передаются ли они пользователям, которые находятся в той же организации или федератном пользователе из другой организации. Вы можете заблокировать передачу файлов P2P федера организации или партнерам, вы предприняв действия ниже.
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814638"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="7ae47-105">Блокировка передачи файлов точка-точка</span><span class="sxs-lookup"><span data-stu-id="7ae47-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="7ae47-106">В Skype для бизнеса Online вы можете управлять передачей файлов точка-точка (P2P) в рамках существующих параметров политики веб-услуг.</span><span class="sxs-lookup"><span data-stu-id="7ae47-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="7ae47-107">Однако при этом для пользователей разрешается или блокируется передача файлов независимо от того, передаются ли они пользователям, которые находятся в той же организации или федератном пользователе из другой организации.</span><span class="sxs-lookup"><span data-stu-id="7ae47-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="7ae47-108">Вы можете заблокировать передачу файлов P2P федера организации или партнерам, вы предприняв действия ниже.</span><span class="sxs-lookup"><span data-stu-id="7ae47-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="7ae47-109">Очень распространенный сценарий — разрешить внутренним пользователям использовать передачу файлов P2P, но заблокировать передачу файлов федератным партнерам.</span><span class="sxs-lookup"><span data-stu-id="7ae47-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="7ae47-110">В этом сценарии вам потребуется сделать:</span><span class="sxs-lookup"><span data-stu-id="7ae47-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="7ae47-111">Назначьте политику для conferencing с включенной передачей файлов P2P _(EnableP2PFileTransfer_ set to _True)_ пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7ae47-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="7ae47-112">Создайте глобальный набор внешней политики связи пользователей, задав для блокировки передачи внешних P2P-файлов _(EnableP2PFileTransfer_ задайте для этого _false)_ и назначьте ее пользователю в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7ae47-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="7ae47-113">Дополнительные информацию об этих параметрах можно [найти](https://technet.microsoft.com/library/mt228132.aspx)здесь.</span><span class="sxs-lookup"><span data-stu-id="7ae47-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="7ae47-114">Если федераированный пользователь за пределами вашей организации попытается отправить файл пользователю, к котором применена политика, он получит сообщение об ошибке с ошибкой **передачи.**</span><span class="sxs-lookup"><span data-stu-id="7ae47-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="7ae47-115">Если пользователь попытается отправить файл, он получит сообщение об ошибке "Передача **файла отключена".**</span><span class="sxs-lookup"><span data-stu-id="7ae47-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="7ae47-116">Для этого пользователь должен использовать поддерживаемую версию приложения Skype для бизнеса версии 2016 "нажми и работай", которая ее поддерживает.</span><span class="sxs-lookup"><span data-stu-id="7ae47-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="7ae47-117">Необходима следующая минимальная версия клиента Skype для бизнеса 2016 "нажми и работы":</span><span class="sxs-lookup"><span data-stu-id="7ae47-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="7ae47-118">**Тип**</span><span class="sxs-lookup"><span data-stu-id="7ae47-118">**Type**</span></span>|<span data-ttu-id="7ae47-119">**Дата выпуска**</span><span class="sxs-lookup"><span data-stu-id="7ae47-119">**Release date**</span></span>|<span data-ttu-id="7ae47-120">**Версия**</span><span class="sxs-lookup"><span data-stu-id="7ae47-120">**Version**</span></span>|<span data-ttu-id="7ae47-121">**Сборка**</span><span class="sxs-lookup"><span data-stu-id="7ae47-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ae47-122">First Release for Current Channel</span><span class="sxs-lookup"><span data-stu-id="7ae47-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="7ae47-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="7ae47-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="7ae47-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="7ae47-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="7ae47-125">Версия 1611 (сборка 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="7ae47-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="7ae47-126">Current Channel</span><span class="sxs-lookup"><span data-stu-id="7ae47-126">Current Channel</span></span>  <br/> |<span data-ttu-id="7ae47-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="7ae47-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="7ae47-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="7ae47-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="7ae47-129">Версия 1611 (сборка 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="7ae47-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="7ae47-130">Deferred Channel</span><span class="sxs-lookup"><span data-stu-id="7ae47-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="7ae47-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="7ae47-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="7ae47-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="7ae47-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="7ae47-133">Версия 1609 (сборка 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="7ae47-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="7ae47-134">Пользователи, которые используют более старые версии приложений Skype для бизнеса для Windows или клиентов Mac, по-прежнему смогут передавать файлы.</span><span class="sxs-lookup"><span data-stu-id="7ae47-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="7ae47-135">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ae47-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="7ae47-136">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="7ae47-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="7ae47-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7ae47-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="7ae47-138">Проверьте версию, введя _get-Host_ в **Windows PowerShell** окне.</span><span class="sxs-lookup"><span data-stu-id="7ae47-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="7ae47-139">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ae47-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="7ae47-140">Чтобы [скачать Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) и обновить Windows PowerShell до версии 4.0, см. Windows PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="7ae47-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="7ae47-141">При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="7ae47-141">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="7ae47-142">Вам также потребуется установить модуль Windows PowerShell для Teams, который позволяет создавать удаленные сеансы Windows PowerShell подключения к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="7ae47-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="7ae47-143">Если вам нужно узнать больше, см. подключение к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx)в одном окне Windows PowerShell окна.</span><span class="sxs-lookup"><span data-stu-id="7ae47-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="7ae47-144">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7ae47-144">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="7ae47-145">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7ae47-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="7ae47-146">В **окне Windows PowerShell** подключения к Microsoft 365 или Office 365, вы работающим с помощью:</span><span class="sxs-lookup"><span data-stu-id="7ae47-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="7ae47-147">Соединитель Skype для бизнеса Online сейчас является частью последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ae47-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
        >
        > <span data-ttu-id="7ae47-148">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="7ae47-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="7ae47-149">Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ae47-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="7ae47-150">Отключение передач файлов P2P для организации</span><span class="sxs-lookup"><span data-stu-id="7ae47-150">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="7ae47-151">По умолчанию _enableP2PFileTransfer_ включена в глобальной политике организации.</span><span class="sxs-lookup"><span data-stu-id="7ae47-151">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="7ae47-152">После создания пользователю была назначена политика _BposSAllModality._</span><span class="sxs-lookup"><span data-stu-id="7ae47-152">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="7ae47-153">Чтобы разрешить передачу P2P-файлов внутри организации, но заблокировать передачу внешних файлов в другую организацию, достаточно изменить ее на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="7ae47-153">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="7ae47-154">Для этого запустите 3</span><span class="sxs-lookup"><span data-stu-id="7ae47-154">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="7ae47-155">Отключение передачи файлов P2P для пользователя</span><span class="sxs-lookup"><span data-stu-id="7ae47-155">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="7ae47-156">Вы можете применить эту политику к пользователю, создав новую политику и надав ее этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="7ae47-156">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="7ae47-157">Для этого запустите 3</span><span class="sxs-lookup"><span data-stu-id="7ae47-157">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7ae47-158">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7ae47-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="7ae47-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="7ae47-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7ae47-160">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="7ae47-160">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="7ae47-161">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="7ae47-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7ae47-162">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7ae47-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="7ae47-163">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ae47-163">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="7ae47-164">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="7ae47-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="7ae47-165">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="7ae47-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="7ae47-166">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ae47-166">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="7ae47-167">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7ae47-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7ae47-168">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7ae47-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="7ae47-169">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7ae47-169">Related topics</span></span>
[<span data-ttu-id="7ae47-170">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="7ae47-170">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="7ae47-171">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="7ae47-171">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="7ae47-172">Настройка политик для организации</span><span class="sxs-lookup"><span data-stu-id="7ae47-172">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
