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
description: Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online.
ms.openlocfilehash: 3928e77e5bac77dbfe89f7be5e762dd0d8ff93eb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814568"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="de43c-103">Скачайте и установите модуль Skype для бизнеса Online Connector</span><span class="sxs-lookup"><span data-stu-id="de43c-103">Download and install the Skype for Business Online Connector module</span></span>

> [!NOTE]
> <span data-ttu-id="de43c-104">Новейшая [общедоступная версия оболочки PowerShell для Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) поддерживается с помощью соединителя Skype для бизнеса Online, что обеспечивает единый модуль для управления оболочкой PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de43c-104">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="de43c-105">Модуль соединителя Skype для бизнеса Online включает командлет **New-CsOnlineSession** , который позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="de43c-105">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="de43c-106">Этот модуль, поддерживаемый только на компьютерах 64 (более подробная информация содержится в разделе [Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md) ), можно загрузить в центре загрузки Майкрософт по адресу [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) .</span><span class="sxs-lookup"><span data-stu-id="de43c-106">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="de43c-107">Скачайте файл SkypeOnlinePowershell.exe, а затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="de43c-107">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="de43c-108">Дважды щелкните файл **SkypeOnlinePowershell.exe**.</span><span class="sxs-lookup"><span data-stu-id="de43c-108">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="de43c-p102">В мастере установки Windows PowerShell для Skype для бизнеса online на странице **Условия лицензионного соглашения на использование программного обеспечения корпорации Майкрософт** щелкните **Я принимаю условия лицензионного соглашения** и нажмите кнопку **Установить**. Если появится диалоговое окно **Контроль учетных записей**, нажмите кнопку **Да** для продолжения установки.</span><span class="sxs-lookup"><span data-stu-id="de43c-p102">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**. If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="de43c-111">На странице **Установка модуля Windows PowerShell для Skype для бизнеса Online завершена** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="de43c-111">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="de43c-p103">Программа установки копирует на ваш компьютер модуль Модуль соединителя Skype для бизнеса Online и командлет **New-CsOnlineSession**. Чтобы запустить этот модуль, откройте сеанс Windows PowerShell с правами администратора и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="de43c-p103">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer. To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="de43c-p104">Если вы не хотите вводить эту команду каждый раз при запуске Windows PowerShell, добавьте ее в свой профиль Windows PowerShell. Для этого в командной строке Windows PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="de43c-p104">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile. To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="de43c-116">В окне редактора "Блокнот" вставьте следующую строку после команд, уже добавленных в профиль (если таковые есть):</span><span class="sxs-lookup"><span data-stu-id="de43c-116">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="de43c-p105">Сохраните файл. В следующий раз при запуске Windows PowerShell модуль будет импортироваться автоматически Модуль соединителя Skype для бизнеса Online. Обратите внимание, что если запуск Windows PowerShell выполнен не от имени администратора, появится сообщение об ошибке и модуль не будет загружен.</span><span class="sxs-lookup"><span data-stu-id="de43c-p105">Save the file. The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported. Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="de43c-p106">Вместе с модулем Модуль соединителя Skype для бизнеса Online из файла SkypeOnlinePowershell.exe также устанавливаются следующие дополнительные компоненты: 1) Библиотека клиентской среды удостоверений (IDCRL), которая используется для проверки подлинности клиентов при доступе к Skype для бизнеса online. 2) Среда .NET Framework 4.5. 3) Распространяемый пакет Microsoft Visual C++ 2012 (x64) (версия 11.0.50727). Среда .NET Framework 4.5 реализует необходимую инфраструктуру для построения и выполнения приложений .NET, включая Windows PowerShell. Распространяемый пакет Visual C++ обеспечивает установку компонентов среды выполнения Visual C++ на компьютерах без среды Microsoft Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="de43c-p106">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727). .NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell. The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="de43c-123">Чтобы проверить версию установленного на вашем компьютере модуля соединителя, откройте панель управления, выберите **Программы и компоненты** и просмотрите значение, представленное в разделе **Модуль Windows PowerShell для Skype для бизнеса Online**.</span><span class="sxs-lookup"><span data-stu-id="de43c-123">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="de43c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="de43c-124">Related topics</span></span>
[<span data-ttu-id="de43c-125">Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="de43c-125">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
