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
description: В Skype для бизнеса Online вы можете управлять передачей файлов с точки зрения (P2P) в составе существующих параметров политики конференц-связи. Тем не менее, это позволяет или блокирует передачу файлов для пользователей вне зависимости от того, передается ли они пользователям, которые находятся в той же организации или на федеративных пользователей из другой организации. Следуя приведенным ниже инструкциям, вы можете заблокировать передачу файлов P2P с федеративными организациями или партнерами.
ms.openlocfilehash: 773feaa97a888bd2063710de9e72f8c7b465a813
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164728"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="78ece-105">Блокировка передачи файлов точка-точка</span><span class="sxs-lookup"><span data-stu-id="78ece-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="78ece-106">В Skype для бизнеса Online вы можете управлять передачей файлов с точки зрения (P2P) в составе существующих параметров политики конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="78ece-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="78ece-107">Тем не менее, это позволяет или блокирует передачу файлов для пользователей вне зависимости от того, передается ли они пользователям, которые находятся в той же организации или на федеративных пользователей из другой организации.</span><span class="sxs-lookup"><span data-stu-id="78ece-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="78ece-108">Следуя приведенным ниже инструкциям, вы можете заблокировать передачу файлов P2P с федеративными организациями или партнерами.</span><span class="sxs-lookup"><span data-stu-id="78ece-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="78ece-109">Очень распространенный сценарий, который позволяет внутренним пользователям использовать передачу файлов P2P, но блокировать передачу файлов с помощью федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="78ece-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="78ece-110">Для этого сценария необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="78ece-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="78ece-111">Назначьте политику конференций с включенной поддержкой передачи файлов P2P (для_EnableP2PFileTransfer_ установлено значение _true_) для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="78ece-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="78ece-112">Создайте глобальную политику связи внешних пользователей, которая блокирует передачу внешних файлов P2P (для_EnableP2PFileTransfer_ установлено значение _false_), и назначьте ее пользователю в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="78ece-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="78ece-113">Дополнительные сведения об этих параметрах можно найти [здесь](https://technet.microsoft.com/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="78ece-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="78ece-114">Если федеративный пользователь за пределами вашей организации пытается отправить файл пользователю, на котором она была применена, она получит сообщение об ошибке " **не удалось передать** ".</span><span class="sxs-lookup"><span data-stu-id="78ece-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="78ece-115">Если пользователь попытается отправить файл, он получит сообщение об ошибке " **Передача файлов** отключена".</span><span class="sxs-lookup"><span data-stu-id="78ece-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="78ece-116">Для выполнения этой задачи пользователь должен использовать поддерживаемую версию 2016 "нажми и работай" приложения Skype для бизнеса, поддерживающего это приложение.</span><span class="sxs-lookup"><span data-stu-id="78ece-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="78ece-117">Требуется следующая минимальная версия клиента "нажми и работай" Skype для бизнеса 2016:</span><span class="sxs-lookup"><span data-stu-id="78ece-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="78ece-118">**Тип**</span><span class="sxs-lookup"><span data-stu-id="78ece-118">**Type**</span></span>|<span data-ttu-id="78ece-119">**Дата выпуска**</span><span class="sxs-lookup"><span data-stu-id="78ece-119">**Release date**</span></span>|<span data-ttu-id="78ece-120">**Версия**</span><span class="sxs-lookup"><span data-stu-id="78ece-120">**Version**</span></span>|<span data-ttu-id="78ece-121">**Разработки**</span><span class="sxs-lookup"><span data-stu-id="78ece-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="78ece-122">Первый выпуск для текущего канала</span><span class="sxs-lookup"><span data-stu-id="78ece-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="78ece-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="78ece-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="78ece-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="78ece-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="78ece-125">Версия 1611 (сборка 7571,2006)</span><span class="sxs-lookup"><span data-stu-id="78ece-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="78ece-126">Текущий канал</span><span class="sxs-lookup"><span data-stu-id="78ece-126">Current Channel</span></span>  <br/> |<span data-ttu-id="78ece-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="78ece-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="78ece-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="78ece-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="78ece-129">Версия 1611 (сборка 7571,2072)</span><span class="sxs-lookup"><span data-stu-id="78ece-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="78ece-130">Отложенный канал</span><span class="sxs-lookup"><span data-stu-id="78ece-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="78ece-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="78ece-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="78ece-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="78ece-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="78ece-133">Версия 1609 (сборка 7369,2118)</span><span class="sxs-lookup"><span data-stu-id="78ece-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="78ece-134">Пользователи, использующие более ранние версии приложений Skype для бизнеса для Windows или Mac, по-прежнему смогут передавать файлы.</span><span class="sxs-lookup"><span data-stu-id="78ece-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="78ece-135">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78ece-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="78ece-136">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="78ece-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="78ece-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="78ece-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="78ece-138">Проверьте версию, введя _Get-Host_ в окне **Windows PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="78ece-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="78ece-139">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78ece-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="78ece-140">Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="78ece-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="78ece-141">При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="78ece-141">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="78ece-p107">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="78ece-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="78ece-145">Дополнительные сведения можно найти в разделе [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="78ece-145">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="78ece-146">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="78ece-146">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="78ece-147">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="78ece-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="78ece-148">В окне **Windows PowerShell** подключитесь к службе Microsoft 365 или Office 365, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="78ece-148">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="78ece-149">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="78ece-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="78ece-150">Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или [Настройка компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="78ece-150">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="78ece-151">Отключение передачи файлов P2P для Организации</span><span class="sxs-lookup"><span data-stu-id="78ece-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="78ece-152">По умолчанию _EnableP2PFileTransfer_ включена в глобальной политике Организации.</span><span class="sxs-lookup"><span data-stu-id="78ece-152">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="78ece-153">После создания пользователи назначили политику _BposSAllModality_ .</span><span class="sxs-lookup"><span data-stu-id="78ece-153">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="78ece-154">Чтобы разрешить передачу P2P в рамках вашей организации, но заблокировать передачу внешних файлов в другую организацию, вам нужно просто изменить ее на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="78ece-154">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="78ece-155">Для этого выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="78ece-155">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="78ece-156">Отключение передачи файлов P2P для пользователя</span><span class="sxs-lookup"><span data-stu-id="78ece-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="78ece-157">Вы можете применить это к пользователю, создав новую политику и предоставив ее для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="78ece-157">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="78ece-158">Для этого выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="78ece-158">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="78ece-159">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="78ece-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="78ece-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="78ece-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="78ece-161">С помощью Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач.</span><span class="sxs-lookup"><span data-stu-id="78ece-161">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="78ece-162">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="78ece-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="78ece-163">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="78ece-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="78ece-164">Зачем использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="78ece-164">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="78ece-165">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="78ece-165">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="78ece-166">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="78ece-166">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="78ece-167">Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78ece-167">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="78ece-168">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="78ece-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="78ece-169">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="78ece-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="78ece-170">См. также</span><span class="sxs-lookup"><span data-stu-id="78ece-170">Related topics</span></span>
[<span data-ttu-id="78ece-171">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="78ece-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="78ece-172">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="78ece-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="78ece-173">Настройка политик конференц-связи в Организации</span><span class="sxs-lookup"><span data-stu-id="78ece-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
