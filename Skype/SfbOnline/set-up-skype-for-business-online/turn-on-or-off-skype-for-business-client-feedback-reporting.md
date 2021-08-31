---
title: Включение и выключение отчетов и отзывов клиентов в Skype для бизнеса
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Вы можете позволить Skype для бизнеса пользователям использовать встроенное средство обратной связи Skype для бизнеса приложения, чтобы пользователи могли сообщать о проблемах и напрямую сообщать корпорации Майкрософт об их впечатлениях.
ms.openlocfilehash: 9382c19c5abf78dc47dcaa3de33841a64e96f490
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728288"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>Включение и выключение отчетов и отзывов клиентов в Skype для бизнеса

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Вы можете позволить пользователям Skype для бизнеса Online использовать встроенное средство обратной связи Skype для бизнеса приложения, чтобы пользователи могли сообщать о проблемах и напрямую сообщать корпорации Майкрософт об их впечатлениях. 
  
![Значок "Обратная связь".](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
С помощью этого средства пользователь может скопировать журналы из приложения на своем устройстве, чтобы помочь корпорации Майкрософт лучше исследовать и устранять проблемы, которые могут возникнуть у него. 
  
![Сообщить о проблеме с помощью Параметры значка.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
Кроме того, с помощью параметра  _EnableOnlineFeedbackScreenshot_ пользователи могут добавлять в отзывы снимки экранов своих устройств.
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> Журналы, собранные средством обратной связи приложения, хранятся в США не более 90 дней, пока ведется изучение проблемы. В связи с этим просим не активировать данную функцию, если это условие нарушает действующую в вашей организации политику защиты данных. 
  
## <a name="start-windows-powershell"></a>Начните Windows PowerShell

> [!NOTE]
> Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell. Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.
1. Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Откройте Windows PowerShell командную команду и запустите следующие команды: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   Дополнительные сведения о запуске Windows PowerShell см. в Подключение всех службах Microsoft 365 или [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или Настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>Включение средства обратной связи в клиентском приложении для всех пользователей в организации

Чтобы включить отчеты о отзывах для пользователей в организации и разрешить им отправлять снимки экрана устройства, запустите:
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Шесть причин, по которым может потребоваться использовать Windows PowerShell управление Microsoft 365 или Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](set-up-skype-for-business-online.md)

[Разрешение на добавление контактов Skype пользователям Skype для бизнеса](let-skype-for-business-users-add-skype-contacts.md)

  
