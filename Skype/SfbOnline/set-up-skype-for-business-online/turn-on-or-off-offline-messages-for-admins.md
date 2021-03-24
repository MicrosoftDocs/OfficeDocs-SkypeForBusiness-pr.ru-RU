---
title: Включение и отключение отправки сообщений в автономном режиме для администраторов
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
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
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 82b6b6c70e129d152d716cdc2567a9776b9d0302
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103825"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Включение и отключение отправки сообщений в автономном режиме для администраторов

[] Теперь можно отправлять сообщения Skype для бизнеса своим контактам, даже если они не вошли в приложение. Эта функция оповещает ваши контакты о том, что вы пытались с ними связаться. Больше не нужно ждать, пока пользователь зайдет в сеть, чтобы отправить ему сообщение.

Для сообщений в автономном режиме важно знать следующее:

- Сообщения в автономном режиме не будут архивироваться в почтовом ящике пользователя.

- Сообщения в автономном режиме будут отправлены в почтовый ящик пользователя, и пользователь получит уведомление, когда войдет в Skype для бизнеса.

- Если статус получателя сообщения **Не беспокоить** или **Идет презентация**, пользователь получит пропущенное сообщение с клиента Skype для бизнеса отправителя.

Дополнительные сведения см. в статье [Отправка сообщений в автономном режиме в Skype для бизнеса](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).

## <a name="to-get-you-started"></a>Чтобы начать работу, можно сделать следующее

> [!NOTE]
> Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell. Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.
1. Установите модуль [Teams PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Откройте Windows PowerShell и запустите следующие команды: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.

## <a name="turning-on-or-off-offline-im"></a>Включение и отключение обмена мгновенными сообщениями в автономном режиме

> [!NOTE]
> Мгновенные сообщения в автономном режиме доступны **только** в последней версии клиента Skype для бизнеса с установкой "нажми и работай" и недоступны в более ранних версиях этого клиента, а также если для установки клиента Skype для бизнеса использовался MSI-файл.

Чтобы включить или отключить отправку автономных сообщений для пользователей в организации, задайте для  _EnableIMAutoArchiving_ значение `True` или `False`. По умолчанию установлено значение `True` .

Чтобы отключить эту функцию, воспользуйтесь командлетом **Set-CsClientPolicy** и выполните следующую команду:

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Чтобы включить или отключить отправку автономных сообщений для пользователя, задайте для  _EnableIMAutoArchiving_ значение `True` или `False`. По умолчанию задано значение  `True`. Вы можете использовать существующую политику или создать ее, как по примеру ниже.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.

  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:

  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](set-up-skype-for-business-online.md)

[Разрешение на добавление контактов Skype пользователям Skype для бизнеса](let-skype-for-business-users-add-skype-contacts.md)