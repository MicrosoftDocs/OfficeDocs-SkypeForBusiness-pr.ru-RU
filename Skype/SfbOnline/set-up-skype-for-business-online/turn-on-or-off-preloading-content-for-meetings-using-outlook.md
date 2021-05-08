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
ms.openlocfilehash: b6ff40e34c6459a75d0b79a8d750902a3457e00d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239112"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Включение и выключение разрешения предварительной загрузки содержимого для собраний с помощью Outlook

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Пользователи могут предварительно загрузки содержимого, файлов или вложений, вложенных в Outlook приглашения на собрание Skype для бизнеса по сети, но вы можете включить или отключить его. Он включен по умолчанию для всех организаций, использующих Skype для бизнеса Online. Узнайте, как [предварительно загрузка вложений для Skype для бизнеса собрания.](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)
  
> [!NOTE]
> В настоящее время в Skype для бизнеса Online нет Skype для бизнеса для настройки и просмотра сетевых значений _для MaxContentStorageMB_ и _MaxUploadFileMB._ Они доступны только для локальных развертываний. Важно знать, что содержимое не будет добавлено на собрание, если вложенное содержимое превышает _maxUploadFileSizeMB_ или достигнут предел _MaxContentStorageMB._
  
## <a name="to-get-you-started"></a>Чтобы начать работу, можно сделать следующее

## <a name="start-windows-powershell"></a>Начните Windows PowerShell

> [!NOTE]
> Skype для бизнеса В настоящее время Online Connector является частью последней версии Teams PowerShell. Если вы используете последний общедоступный Teams PowerShell, вам не нужно устанавливать Skype для бизнеса Online Connector.
1. Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Откройте Windows PowerShell командную команду и запустите следующие команды: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

Дополнительные сведения о запуске Windows PowerShell см. в Подключение всех службах Microsoft 365 или [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или Настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.
  
## <a name="turning-it-on-or-off"></a>Включение и выключение функции

Возможность предварительной загрузки содержимого, вложенного в Outlook приглашения на собрание Skype для бизнеса собрания по сети, по умолчанию включена, но может потребоваться запретить пользователям в организации предварительной загрузки содержимого на собраниях.
  
> [!IMPORTANT]
> Этот параметр можно отключить или отключить только для всей организации. вы не можете включить или отключить ее для одного пользователя. 
  
 **Чтобы отключить функцию, откройте Windows PowerShell и выполните следующие действия:**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **Чтобы снова включить функцию, откройте Windows PowerShell и выполните следующие действия:**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Шесть причин, по которым может потребоваться использовать Windows PowerShell управление Microsoft 365 или Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](set-up-skype-for-business-online.md)

[Разрешение на добавление контактов Skype пользователям Skype для бизнеса](let-skype-for-business-users-add-skype-contacts.md)

  
