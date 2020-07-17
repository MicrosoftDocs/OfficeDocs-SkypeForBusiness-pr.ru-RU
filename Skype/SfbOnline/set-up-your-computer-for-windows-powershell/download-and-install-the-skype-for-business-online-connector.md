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
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Скачайте и установите модуль Skype для бизнеса Online Connector

> [!NOTE]
> Новейшая [общедоступная версия оболочки PowerShell для Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) поддерживается с помощью соединителя Skype для бизнеса Online, что обеспечивает единый модуль для управления оболочкой PowerShell.

Модуль соединителя Skype для бизнеса Online включает командлет **New-CsOnlineSession** , который позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online. Этот модуль, поддерживаемый только на компьютерах 64 (более подробная информация содержится в разделе [Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md) ), можно загрузить в центре загрузки Майкрософт по адресу [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) . Скачайте файл SkypeOnlinePowershell.exe, а затем выполните указанные ниже действия.
  
1. Дважды щелкните файл **SkypeOnlinePowershell.exe**.
    
2. В мастере установки Windows PowerShell для Skype для бизнеса online на странице **Условия лицензионного соглашения на использование программного обеспечения корпорации Майкрософт** щелкните **Я принимаю условия лицензионного соглашения** и нажмите кнопку **Установить**. Если появится диалоговое окно **Контроль учетных записей**, нажмите кнопку **Да** для продолжения установки.
    
3. На странице **Установка модуля Windows PowerShell для Skype для бизнеса Online завершена** нажмите кнопку **Готово**.
    
Программа установки копирует на ваш компьютер модуль Модуль соединителя Skype для бизнеса Online и командлет **New-CsOnlineSession**. Чтобы запустить этот модуль, откройте сеанс Windows PowerShell с правами администратора и выполните следующую команду:
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

Если вы не хотите вводить эту команду каждый раз при запуске Windows PowerShell, добавьте ее в свой профиль Windows PowerShell. Для этого в командной строке Windows PowerShell введите следующую команду и нажмите клавишу ВВОД:
  
```PowerShell
notepad.exe $profile
```

 В окне редактора "Блокнот" вставьте следующую строку после команд, уже добавленных в профиль (если таковые есть):
  
```PowerShell
Import-Module SkypeOnlineConnector
```

Сохраните файл. В следующий раз при запуске Windows PowerShell модуль будет импортироваться автоматически Модуль соединителя Skype для бизнеса Online. Обратите внимание, что если запуск Windows PowerShell выполнен не от имени администратора, появится сообщение об ошибке и модуль не будет загружен.
  
Вместе с модулем Модуль соединителя Skype для бизнеса Online из файла SkypeOnlinePowershell.exe также устанавливаются следующие дополнительные компоненты: 1) Библиотека клиентской среды удостоверений (IDCRL), которая используется для проверки подлинности клиентов при доступе к Skype для бизнеса online. 2) Среда .NET Framework 4.5. 3) Распространяемый пакет Microsoft Visual C++ 2012 (x64) (версия 11.0.50727). Среда .NET Framework 4.5 реализует необходимую инфраструктуру для построения и выполнения приложений .NET, включая Windows PowerShell. Распространяемый пакет Visual C++ обеспечивает установку компонентов среды выполнения Visual C++ на компьютерах без среды Microsoft Visual Studio 2012.
  
Чтобы проверить версию установленного на вашем компьютере модуля соединителя, откройте панель управления, выберите **Программы и компоненты** и просмотрите значение, представленное в разделе **Модуль Windows PowerShell для Skype для бизнеса Online**.
  
## <a name="related-topics"></a>Связанные статьи
[Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
