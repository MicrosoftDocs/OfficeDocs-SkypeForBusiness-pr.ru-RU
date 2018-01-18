---
title: "Создание политик настраиваемого внешнего доступа"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Скайп для бизнеса в Интернет позволяет создавать политики дополнительные внешнего доступа. В отличие от клиента или конференц-связи политик, где может иметь несколько комбинаций, существует три политики предварительно заданных внешнего доступа, которые могут охватывать большинство сценариев."
ms.openlocfilehash: ffb08963d82af77f4d68c679b82bc8b8c44fa75f
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="ea96f-104">Создание политик настраиваемого внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="ea96f-104">Create custom external access policies</span></span>

<span data-ttu-id="ea96f-105">Скайп для бизнеса в Интернет позволяет создавать политики дополнительные внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="ea96f-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="ea96f-106">В отличие от клиента или конференц-связи политик, где может иметь несколько комбинаций, существует три политики предварительно заданных внешнего доступа, которые могут охватывать большинство сценариев.</span><span class="sxs-lookup"><span data-stu-id="ea96f-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="ea96f-107">Далее представлены:</span><span class="sxs-lookup"><span data-stu-id="ea96f-107">These are:</span></span>
  
- <span data-ttu-id="ea96f-108">Федеративные no или потребитель Скайп доступа (_Тег: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="ea96f-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="ea96f-109">Федеративный доступ только (_Тег: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="ea96f-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="ea96f-110">Федеративные и потребителей доступа (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="ea96f-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="ea96f-111">Настраиваемые внешние политики позволяют для создания дополнительных политик, не, к которому применяется выше параметров.</span><span class="sxs-lookup"><span data-stu-id="ea96f-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="ea96f-112">При создании политики, вам необходимо задать все требуемые параметры и их невозможно изменить позднее.</span><span class="sxs-lookup"><span data-stu-id="ea96f-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="ea96f-113">Создание новых настраиваемых политик позволяют функции управления, например Скайп потребитель доступа или политики для отключения общедоступных облачных аудио и видео, что-то, что не был рассмотрен с предварительно заданных параметров.</span><span class="sxs-lookup"><span data-stu-id="ea96f-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="ea96f-114">Политики настраиваемого внешнего доступа выполните же синтаксисом, что политики клиентов, мобильных устройств и конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="ea96f-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="ea96f-115">Дополнительную информацию по эти параметры можно найти [здесь](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="ea96f-115">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="ea96f-116">Чтобы выполнить эту операцию, пользователю необходимо включить поддерживаемая версия 2016 Click-to-Run Скайп для бизнес-приложение, которое поддерживает его.</span><span class="sxs-lookup"><span data-stu-id="ea96f-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="ea96f-117">Следующие Минимальная версия Скайп для клиента Business 2016 Click-to-Run является обязательным:</span><span class="sxs-lookup"><span data-stu-id="ea96f-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="ea96f-118">**Тип**</span><span class="sxs-lookup"><span data-stu-id="ea96f-118">**Type**</span></span>|<span data-ttu-id="ea96f-119">**Дата выпуска**</span><span class="sxs-lookup"><span data-stu-id="ea96f-119">**Release date**</span></span>|<span data-ttu-id="ea96f-120">**Версия**</span><span class="sxs-lookup"><span data-stu-id="ea96f-120">**Version**</span></span>|<span data-ttu-id="ea96f-121">**Построение**</span><span class="sxs-lookup"><span data-stu-id="ea96f-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ea96f-122">Первый выпуск для текущего канала</span><span class="sxs-lookup"><span data-stu-id="ea96f-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="ea96f-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="ea96f-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="ea96f-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="ea96f-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="ea96f-125">Версия 1611 (сборка 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="ea96f-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="ea96f-126">Текущая платформа канала</span><span class="sxs-lookup"><span data-stu-id="ea96f-126">Current Channel</span></span>  <br/> |<span data-ttu-id="ea96f-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="ea96f-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="ea96f-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="ea96f-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="ea96f-129">Версия 1611 (сборка 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="ea96f-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="ea96f-130">Отложенная канала</span><span class="sxs-lookup"><span data-stu-id="ea96f-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="ea96f-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="ea96f-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="ea96f-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="ea96f-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="ea96f-133">Версия 1609 (сборка 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="ea96f-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="ea96f-134">Пользователей, которые более старых версиях Скайп для приложения для бизнеса Windows или Mac клиентов по-прежнему будут иметь возможность передавать файлы.</span><span class="sxs-lookup"><span data-stu-id="ea96f-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="ea96f-135">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea96f-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="ea96f-136">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="ea96f-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="ea96f-137">Чтобы убедиться, что выполняется версия 3.0 или более поздней версии: **Меню "Пуск"** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ea96f-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ea96f-138">Проверьте версию, введя в окне **Windows PowerShell** команду _Get-Host_.</span><span class="sxs-lookup"><span data-stu-id="ea96f-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="ea96f-p105">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="ea96f-p105">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="ea96f-p106">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="ea96f-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="ea96f-145">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="ea96f-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="ea96f-146">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ea96f-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="ea96f-147">Из **меню Пуск** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ea96f-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ea96f-148">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ea96f-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ea96f-149">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="ea96f-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="ea96f-150">Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [подключение к Скайп для бизнеса в Интернет с помощью Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ea96f-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="ea96f-151">Создание политики настраиваемого внешнего доступа для пользователя</span><span class="sxs-lookup"><span data-stu-id="ea96f-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="ea96f-152">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ea96f-152">To do this, run:</span></span>
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ea96f-153">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ea96f-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="ea96f-p107">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="ea96f-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ea96f-157">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ea96f-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ea96f-158">Почему необходимо использовать Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea96f-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ea96f-p108">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="ea96f-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ea96f-161">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea96f-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ea96f-162">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ea96f-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ea96f-163">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ea96f-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ea96f-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea96f-164">Related topics</span></span>
[<span data-ttu-id="ea96f-165">Передача файлов точка-точка блока</span><span class="sxs-lookup"><span data-stu-id="ea96f-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="ea96f-166">Настройка политик клиента для вашей организации</span><span class="sxs-lookup"><span data-stu-id="ea96f-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="ea96f-167">Настройка политик конференц-связи в вашей организации</span><span class="sxs-lookup"><span data-stu-id="ea96f-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
