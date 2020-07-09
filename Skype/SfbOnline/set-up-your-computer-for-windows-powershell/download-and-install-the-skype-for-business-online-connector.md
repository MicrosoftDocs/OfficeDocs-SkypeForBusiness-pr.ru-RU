---
title: Скачайте и установите модуль Skype для бизнеса Online Connector
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
- PowerShell
description: 'Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online. '
ms.openlocfilehash: 8c5068c221c46f7be0d9d97c1c3d515ae244b316
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085705"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="a1929-103">Скачайте и установите модуль Skype для бизнеса Online Connector</span><span class="sxs-lookup"><span data-stu-id="a1929-103">Download and install the Skype for Business Online Connector module</span></span>

> [!NOTE]
> <span data-ttu-id="a1929-104">Новейшая [общедоступная версия оболочки PowerShell для Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) поддерживается с помощью соединителя Skype для бизнеса Online, что обеспечивает единый модуль для управления оболочкой PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1929-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="a1929-105">Модуль соединителя Skype для бизнеса Online включает командлет **New-CsOnlineSession** , который позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="a1929-105">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="a1929-106">Этот модуль, поддерживаемый только на компьютерах 64 (более подробная информация содержится в разделе [Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md) ), можно загрузить в центре загрузки Майкрософт по адресу [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) .</span><span class="sxs-lookup"><span data-stu-id="a1929-106">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="a1929-107">Скачайте файл SkypeOnlinePowershell.exe, а затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a1929-107">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="a1929-108">Дважды щелкните файл **SkypeOnlinePowershell.exe**.</span><span class="sxs-lookup"><span data-stu-id="a1929-108">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="a1929-109">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span><span class="sxs-lookup"><span data-stu-id="a1929-109">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="a1929-110">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span><span class="sxs-lookup"><span data-stu-id="a1929-110">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="a1929-111">На странице **Установка модуля Windows PowerShell для Skype для бизнеса Online завершена** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a1929-111">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="a1929-112">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span><span class="sxs-lookup"><span data-stu-id="a1929-112">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="a1929-113">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span><span class="sxs-lookup"><span data-stu-id="a1929-113">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="a1929-114">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span><span class="sxs-lookup"><span data-stu-id="a1929-114">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="a1929-115">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span><span class="sxs-lookup"><span data-stu-id="a1929-115">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="a1929-116">В окне редактора "Блокнот" вставьте следующую строку после команд, уже добавленных в профиль (если таковые есть):</span><span class="sxs-lookup"><span data-stu-id="a1929-116">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="a1929-117">Save the file.</span><span class="sxs-lookup"><span data-stu-id="a1929-117">Save the file.</span></span> <span data-ttu-id="a1929-118">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span><span class="sxs-lookup"><span data-stu-id="a1929-118">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="a1929-119">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span><span class="sxs-lookup"><span data-stu-id="a1929-119">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="a1929-120">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="a1929-120">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="a1929-121">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1929-121">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="a1929-122">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span><span class="sxs-lookup"><span data-stu-id="a1929-122">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="a1929-123">Чтобы проверить версию установленного на вашем компьютере модуля соединителя, откройте панель управления, выберите **Программы и компоненты** и просмотрите значение, представленное в разделе **Модуль Windows PowerShell для Skype для бизнеса Online**.</span><span class="sxs-lookup"><span data-stu-id="a1929-123">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a1929-124">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="a1929-124">Related topics</span></span>
[<span data-ttu-id="a1929-125">Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1929-125">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
