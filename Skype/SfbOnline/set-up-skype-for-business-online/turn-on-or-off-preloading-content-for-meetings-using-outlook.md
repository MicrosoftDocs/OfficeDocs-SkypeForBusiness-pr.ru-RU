---
title: Включение и выключение разрешения предварительной загрузки содержимого для собраний с помощью Outlook
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 7a59edb72b72cb42661cdf0e2cb350d7617a47bf
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568905"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Включение и выключение разрешения предварительной загрузки содержимого для собраний с помощью Outlook

Пользователи могут заранее перезагружать содержимое, файлы или вложения, вложенные в приглашение на собрание Outlook, на собрание Skype для бизнеса Online, но вы можете включить или отключить эту возможность. Этот режим по умолчанию включен для всех организаций, использующих Skype для бизнеса Online. Узнайте, как [предварительно загрузка вложений для собрания Skype для бизнеса.](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)
  
> [!NOTE]
> В настоящее время в Skype для бизнеса Online нет cmdlets для настройки и просмотра значений в сети для _MaxContentStorageMB_ и _MaxUploadFileMB._ Они доступны только для локальных развертываний. Важно знать, что содержимое не будет загружено на собрание, если вложенное содержимое превышает максимально допустимый предел _MaxUploadFileSizeMB_ или достигнуто ограничение _MaxContentStorageMB._
  
## <a name="to-get-you-started"></a>Чтобы начать работу, можно сделать следующее

## <a name="start-windows-powershell"></a>Начать Windows PowerShell

> [!NOTE]
> Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell. Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.
1. Установите модуль [Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Откройте Windows PowerShell и запустите следующие команды: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.
  
## <a name="turning-it-on-or-off"></a>Включение и выключение функции

Возможность предварительной загрузки содержимого, вложенного в приглашение на собрание Outlook, в собраниях Skype для бизнеса Online включена по умолчанию, но может потребоваться запретить пользователям в вашей организации предварительной загрузки содержимого во время собраний.
  
> [!IMPORTANT]
> Этот параметр можно отключить только для всей организации; его нельзя включить или отключить для одного пользователя. 
  
 **Чтобы отключить функцию, откройте Windows PowerShell и выполните следующие действия:**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **Чтобы снова включить функцию, откройте Windows PowerShell и выполните следующие действия:**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](set-up-skype-for-business-online.md)

[Разрешение на добавление контактов Skype пользователям Skype для бизнеса](let-skype-for-business-users-add-skype-contacts.md)

  
 
