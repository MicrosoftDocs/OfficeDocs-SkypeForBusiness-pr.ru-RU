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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Пользователи Skype для бизнеса могут использовать встроенное средство обратной связи в Skype для бизнеса, чтобы пользователи могли сообщать о проблемах и получать отзывы прямо в Microsoft о своих впечатлениях.
ms.openlocfilehash: 3b91bc88c20450b7c0d9c5705bceec53af5f9edb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814188"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>Включение и выключение отчетов и отзывов клиентов в Skype для бизнеса

Вы можете разрешить пользователям Skype для бизнеса Online использовать встроенное средство обратной связи с приложениями Skype для бизнеса, чтобы пользователи могли сообщать о проблемах и получать отзывы прямо в Microsoft о своих впечатлениях. 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
С помощью этого средства пользователь может скопировать журналы из приложения на своем устройстве, чтобы корпорация Майкрософт могла лучше исследовать и устранять неполадки, связанные с ними. 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
Кроме того, с помощью параметра  _EnableOnlineFeedbackScreenshot_ пользователи могут добавлять в отзывы снимки экранов своих устройств.
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> Журналы, собранные средством обратной связи приложения, будут храниться в течение не более 90 дней в США, пока эта неполадка не будет устранена. В связи с этим просим не активировать данную функцию, если это условие нарушает действующую в вашей организации политику защиты данных. 
  
## <a name="verify-and-start-windows-powershell"></a>Проверка и запуск Windows PowerShell

- **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . При появлении запроса перезагрузите компьютер.
    
4. Кроме того, вам потребуется установить модуль Windows PowerShell для Teams, который позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online. 
    
Дополнительные сведения можно найти в разделе [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Запуск сеанса Windows PowerShell**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. В окне **Windows PowerShell** подключитесь к службе Microsoft 365 или Office 365, выполнив следующие действия:
    
  > [!NOTE]
  > Skype для бизнеса Online уже входит в состав последнего модуля PowerShell для Teams.
  >
  > Если вы используете последнюю версию [общедоступной оболочки для Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), вам не нужно устанавливать соединитель Skype для бизнеса Online.
 
   ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или[Настройка компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>Включение средства обратной связи в клиентском приложении для всех пользователей в организации

Чтобы включить отчеты о отзывах для пользователей в вашей организации и разрешить им отправлять снимки экрана устройства, выполните следующие действия:
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин, по которым вам может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](set-up-skype-for-business-online.md)

[Разрешение на добавление контактов Skype пользователям Skype для бизнеса](let-skype-for-business-users-add-skype-contacts.md)

  
 
