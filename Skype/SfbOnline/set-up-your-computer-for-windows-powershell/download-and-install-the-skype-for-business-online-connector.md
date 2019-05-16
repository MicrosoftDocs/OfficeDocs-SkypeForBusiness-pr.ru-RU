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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 'Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online. '
ms.openlocfilehash: a93cf1d3d09910001f25619969b6d504e23ec36f
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036695"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Скачайте и установите модуль Skype для бизнеса Online Connector

Скайп для модуля Business Online Connector включает в себя командлет **New-CsOnlineSession** , который позволяет создавать удаленного сеанса Windows PowerShell, который подключается к Скайп для бизнеса в Интернет. В этом модуле, который поддерживается только в 64-разрядных компьютерах ( [Настройка компьютера для Скайп для бизнеса в Интернет управление с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md) более подробные сведения), можно загрузить из центра загрузки Майкрософт по [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366). Загрузите файл SkypeOnlinePowershell.exe, а затем выполните следующие действия:
  
1. Дважды щелкните файл **SkypeOnlinePowershell.exe**.
    
2. В мастере установки Windows PowerShell для Skype для бизнеса online на странице **Условия лицензионного соглашения на использование программного обеспечения корпорации Майкрософт** щелкните **Я принимаю условия лицензионного соглашения** и нажмите кнопку **Установить**. Если появится диалоговое окно **Контроль учетных записей**, нажмите кнопку **Да** для продолжения установки.
    
3. На странице **Установка модуля Windows PowerShell для Skype для бизнеса Online завершена** нажмите кнопку **Готово**.
    
Программа установки копирует на ваш компьютер модуль Модуль соединителя Skype для бизнеса Online и командлет **New-CsOnlineSession**. Чтобы запустить этот модуль, откройте сеанс Windows PowerShell с правами администратора и выполните следующую команду:
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Если вы не хотите вводить эту команду каждый раз при запуске Windows PowerShell, добавьте ее в свой профиль Windows PowerShell. Для этого в командной строке Windows PowerShell введите следующую команду и нажмите клавишу ВВОД:
  
```
notepad.exe $profile
```

 В окне редактора "Блокнот" вставьте следующую строку после команд, уже добавленных в профиль (если таковые есть):
  
```
Import-Module SkypeOnlineConnector
```

Сохраните файл. В следующий раз при запуске Windows PowerShell модуль будет импортироваться автоматически Модуль соединителя Skype для бизнеса Online. Обратите внимание, что если запуск Windows PowerShell выполнен не от имени администратора, появится сообщение об ошибке и модуль не будет загружен.
  
Вместе с модулем Модуль соединителя Skype для бизнеса Online из файла SkypeOnlinePowershell.exe также устанавливаются следующие дополнительные компоненты: 1) Библиотека клиентской среды удостоверений (IDCRL), которая используется для проверки подлинности клиентов при доступе к Skype для бизнеса online. 2) Среда .NET Framework 4.5. 3) Распространяемый пакет Microsoft Visual C++ 2012 (x64) (версия 11.0.50727). Среда .NET Framework 4.5 реализует необходимую инфраструктуру для построения и выполнения приложений .NET, включая Windows PowerShell. Распространяемый пакет Visual C++ обеспечивает установку компонентов среды выполнения Visual C++ на компьютерах без среды Microsoft Visual Studio 2012.
  
Чтобы проверить версию установленного на вашем компьютере модуля соединителя, откройте панель управления, выберите **Программы и компоненты** и просмотрите значение, представленное в разделе **Модуль Windows PowerShell для Skype для бизнеса Online**.
  
## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для Скайп online управления бизнес-процессов с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
