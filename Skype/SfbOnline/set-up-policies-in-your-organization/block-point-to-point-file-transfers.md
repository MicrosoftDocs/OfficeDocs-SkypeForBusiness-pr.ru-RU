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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: В Скайп для бизнеса в Интернет у вас есть возможность управления передачу файлов между узлами (P2P) как часть существующие параметры политики конференц-связи. Тем не менее это позволяет или передача для пользователей, ли они передачу файлов, пользователь, который находится в пределах той же организации или федеративного пользователя из другой организации файлов блоки. Следующие шаги можно заблокировать P2P передачи файлов с федеративными организациями или партнеров.
ms.openlocfilehash: 9b7d229c7f0ea0565dc3174286b4117984a2b606
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883246"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="128b2-105">Блокировка передачи файлов точка-точка</span><span class="sxs-lookup"><span data-stu-id="128b2-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="128b2-106">В Скайп для бизнеса в Интернет у вас есть возможность управления передачу файлов между узлами (P2P) как часть существующие параметры политики конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="128b2-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="128b2-107">Тем не менее это позволяет или передача для пользователей, ли они передачу файлов, пользователь, который находится в пределах той же организации или федеративного пользователя из другой организации файлов блоки.</span><span class="sxs-lookup"><span data-stu-id="128b2-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="128b2-108">Следующие шаги можно заблокировать P2P передачи файлов с федеративными организациями или партнеров.</span><span class="sxs-lookup"><span data-stu-id="128b2-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="128b2-109">Весьма распространенного сценария — Если вы хотите разрешить внутренние пользователи могли использовать P2P передачи файлов, но блока передачи файлов с помощью федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="128b2-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="128b2-110">Для этого сценария необходимо выполнить:</span><span class="sxs-lookup"><span data-stu-id="128b2-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="128b2-111">Назначение политики конференц-связи с поддержкой передачи файлов P2P (_EnableP2PFileTransfer_ присвоено _значение True_) для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="128b2-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="128b2-112">Создайте политики связи глобальной внешних пользователей, задайте для блокировки передачи файлов внешних P2P (_EnableP2PFileTransfer_ значение _False_) и назначить пользователю в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="128b2-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="128b2-113">Дополнительную информацию по эти параметры можно найти [здесь](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="128b2-113">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="128b2-114">Если федеративных пользователей за пределами организации пытается отправить файл пользователю, где была ли применена политика, они получат ошибка **Передачи произошел сбой** .</span><span class="sxs-lookup"><span data-stu-id="128b2-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="128b2-115">И при попытке отправить файл появляется ошибка **передачи файлов отключена** .</span><span class="sxs-lookup"><span data-stu-id="128b2-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="128b2-116">Чтобы выполнить эту операцию, пользователя необходимо включить поддерживаемая версия Скайп Click-to-Run 2016 для бизнес-приложение, которое поддерживает его.</span><span class="sxs-lookup"><span data-stu-id="128b2-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="128b2-117">Следующие Минимальная версия Скайп для клиента Business 2016 Click-to-Run является обязательным:</span><span class="sxs-lookup"><span data-stu-id="128b2-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="128b2-118">**Тип**</span><span class="sxs-lookup"><span data-stu-id="128b2-118">**Type**</span></span>|<span data-ttu-id="128b2-119">**Дата выпуска**</span><span class="sxs-lookup"><span data-stu-id="128b2-119">**Release date**</span></span>|<span data-ttu-id="128b2-120">**Версия**</span><span class="sxs-lookup"><span data-stu-id="128b2-120">**Version**</span></span>|<span data-ttu-id="128b2-121">**Построение**</span><span class="sxs-lookup"><span data-stu-id="128b2-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="128b2-122">Первый выпуск для текущего канала</span><span class="sxs-lookup"><span data-stu-id="128b2-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="128b2-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="128b2-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="128b2-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="128b2-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="128b2-125">Версия 1611 (сборка 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="128b2-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="128b2-126">Текущая платформа канала</span><span class="sxs-lookup"><span data-stu-id="128b2-126">Current Channel</span></span>  <br/> |<span data-ttu-id="128b2-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="128b2-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="128b2-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="128b2-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="128b2-129">Версия 1611 (сборка 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="128b2-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="128b2-130">Отложенная канала</span><span class="sxs-lookup"><span data-stu-id="128b2-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="128b2-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="128b2-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="128b2-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="128b2-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="128b2-133">Версия 1609 (сборка 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="128b2-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="128b2-134">Пользователи, работающие с более ранними версиями Скайп для приложения для бизнеса Windows или Mac клиентов по-прежнему будут иметь возможность передавать файлы.</span><span class="sxs-lookup"><span data-stu-id="128b2-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="128b2-135">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="128b2-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="128b2-136">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="128b2-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="128b2-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="128b2-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="128b2-138">Проверка версии с помощью следующей команды _Get-узел_ в окне **Windows PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="128b2-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="128b2-p106">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="128b2-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="128b2-p107">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="128b2-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="128b2-145">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="128b2-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="128b2-146">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="128b2-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="128b2-147">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="128b2-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="128b2-148">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="128b2-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="128b2-149">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="128b2-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="128b2-150">Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [настроить компьютер для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="128b2-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="128b2-151">Отключение P2P передачу файлов для вашей организации</span><span class="sxs-lookup"><span data-stu-id="128b2-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="128b2-152">По умолчанию _EnableP2PFileTransfer_ включена на глобальную политику в организации.</span><span class="sxs-lookup"><span data-stu-id="128b2-152">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="128b2-153">При его создании, пользователи были назначена политика _BposSAllModality_ .</span><span class="sxs-lookup"><span data-stu-id="128b2-153">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="128b2-154">Только что, чтобы разрешить передачу P2P для внутри вашей организации, но блока передачи внешнего файла на другой организации, необходимо изменить на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="128b2-154">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="128b2-155">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="128b2-155">To do that, run:</span></span>
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="128b2-156">Отключение P2P передачи файлов для пользователя</span><span class="sxs-lookup"><span data-stu-id="128b2-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="128b2-157">Можно применить это пользователь, создав новую политику и предоставление данному пользователю.</span><span class="sxs-lookup"><span data-stu-id="128b2-157">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="128b2-158">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="128b2-158">To do that, run:</span></span> 
> 
>   ```
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="128b2-159">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="128b2-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="128b2-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="128b2-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="128b2-161">С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="128b2-161">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="128b2-162">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="128b2-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="128b2-163">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="128b2-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="128b2-164">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="128b2-164">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="128b2-p112">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="128b2-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="128b2-167">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="128b2-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="128b2-168">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="128b2-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="128b2-169">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="128b2-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="128b2-170">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="128b2-170">Related topics</span></span>
[<span data-ttu-id="128b2-171">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="128b2-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="128b2-172">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="128b2-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="128b2-173">Настройка политик конференц-связи в вашей организации</span><span class="sxs-lookup"><span data-stu-id="128b2-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
