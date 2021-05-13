---
title: Переход с Skype для бизнеса Online Connector на модуль Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте, как перейти Skype для бизнеса Online Connector к Teams PowerShell для управления Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e788fc8cd31bd6e8754e410132e02829eaa2cad8
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469721"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Переход с Skype для бизнеса Online Connector на модуль Teams PowerShell

Teams Модуль PowerShell содержит полный набор командлетов для управления Teams непосредственно из командной строки PowerShell. Администраторам не требуется Skype Для бизнеса Online Connector для Teams администрирования.

> [!NOTE]
> Teams сообщение центра сообщений (MC244740 от 16 марта 2021 г.); MC250940 от 16 апреля 2021 г.) об этом изменении.
>
> Teams Модуль PowerShell использует современную проверку подлинности, но для Windows клиента удаленного управления (WinRM) необходимо разрешить базовую проверку подлинности. Инструкции [о том, как включить проверку](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) подлинности WinRM для Basic, см. в Windows PowerShell и установке приложения.

> [!WARNING]
> Skype для бизнеса Подключения online Connector будут отклоняться с 17 мая 2021 г. Обратитесь в службу поддержки Майкрософт за помощью и поддержкой по переходу на Teams PowerShell.

## <a name="how-to-migrate"></a>Перенос

Перейти с Skype для бизнеса Online Connector на Teams powerShell очень просто. Ниже объясняется, как это сделать.

1. Установите последнюю версию Teams PowerShell. По шагам см. [Microsoft Teams Powershell.](teams-powershell-install.md)
2. Удалить соединитель Skype для бизнеса Online. Для этого на панели управления перейдите в программу и функции **,** выберите Skype для бизнеса **Online, модуль Windows PowerShell**, а затем **—** Удалить .
3. В сценариях PowerShell измените имя модуля, на который ссылается ```Import-Module```

    `SkypeOnlineConnector` или `LyncOnlineConnector` в `MicrosoftTeams` .

    Например, измените `Import-Module -Name SkypeOnlineConnector` на `Import-Module -Name MicrosoftTeams` .

4. При использовании Teams PowerShell Module 2.0 или более поздней версии обновите сценарии, которые ссылаются на `New-CsOnlineSession` `Connect-MicrosoftTeams` . `Import-PsSession`больше не требуется создавать сеанс удаленной Skype для бизнеса PowerShell в Интернете, так как он делается неявным при использовании `Connect-MicrosoftTeams` .

    ```powershell
       # When using the Skype for Business online connector
         Import-Module SkypeForBusinessConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
       # Example getting tenant details
         Get-csTenant
    
       # When using Teams PowerShell Module 2.0 or later
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
       # Example getting tenant details
         Get-csTenant
    
       # Closing the Session when using the Skype for Business online connector
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # Disconnecting from Teams PowerShell Module 
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a>Поддержка в Интернете

Экономите время, отправив запрос на обслуживание через Интернет. Мы поможем вам найти решение или подключиться к службе технической поддержки.
1.  Перейдите в Центр администрирования в [https://admin.microsoft.com](https://admin.microsoft.com) . Если вы получаете сообщение о том, что у вас нет разрешения на доступ к этой странице или выполнение этого действия, вы не администратор. У Кто есть разрешения администратора в моей компании?
2.  Выберите нужна **помощь?** Кнопку.
3.  В области **Нужна помощь?** расскажите нам, с чем вам нужна помощь, и нажмите ввод.
4.  Если результаты не помогли, выберите Обратиться **в службу поддержки**.
5.  Введите описание проблемы, подтвердите свой номер контакта и адрес электронной почты, выберите предпочтительный способ связи, а затем выберите Связаться со **мной**. Ожидаемое время ожидания указано в области Нужна помощь? Панели.

## <a name="related-topics"></a>См. также

[Установка Microsoft Teams Powershell](teams-powershell-install.md)

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Заметки о выпуске PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams ссылки на cmdlet](/powershell/teams/?view=teams-ps)

[Skype для бизнеса ссылки на cmdlet](/powershell/skype/intro?view=skype-ps)
