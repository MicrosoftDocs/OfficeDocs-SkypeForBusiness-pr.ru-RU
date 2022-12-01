---
title: Отключение политики отправки собственных файлов Teams
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Узнайте, как создавать, задавать, назначать и настраивать политику файлов Teams с помощью PowerShell.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.openlocfilehash: 6c7d5c89c780fa5c9286f5d7f7d2304f2e6c6220
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198531"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Отключение политики отправки собственных файлов Teams

Майкрософт Teams использует OneDrive и SharePoint для хранения и совместного использования содержимого, но некоторые организации и пользователи могут предпочесть использовать сторонних поставщиков хранилища.  

Если ваша организация выбирает стороннюю сторону для хранения содержимого, необходимо отключить `NativeFileEntryPoints` параметр в политике файлов Teams. Этот параметр включен по умолчанию, который показывает возможность отправки содержимого из OneDrive или SharePoint в чаты или каналы Teams.

Эта статья поможет вам создать, задать, назначить и удалить `NativeFileEntryPoints` параметр с помощью PowerShell.

>[!NOTE]
>Если политика файлов Teams отключена, пользователи не будут видеть точки доступа для OneDrive и SharePoint в Teams, но создание новых команд и каналов будет по-прежнему активировать создание соответствующих библиотек SharePoint.

## <a name="prepare-to-update-the-teams-files-policy"></a>Подготовка к обновлению политики файлов Teams

### <a name="set-up-microsoft-powershell"></a>Настройка Майкрософт PowerShell

В настоящее время эту политику нельзя изменить в Центре администрирования Teams. Администратору клиента Майкрософт 365 вашей организации придется внести изменения с помощью командлетов PowerShell, описанных далее в этой статье.

Узнайте, как установить модуль PowerShell Teams с помощью коллекция PowerShell, из статьи [Установка модуля PowerShell Майкрософт Teams](teams-powershell-install.md).

Сведения об установке или скачивании модуля Teams PowerShell см. в статье [коллекция PowerShell для Майкрософт Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Дополнительные сведения о настройке PowerShell для управления Teams см. в статье [Управление Teams с помощью PowerShell Майкрософт Teams](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Разрешить сторонние приложения в Teams Администратор Center

Этот шаг не требуется для изменения политики файлов Teams, но он необходим, когда вы готовы интегрировать стороннего поставщика хранилища в интерфейс Teams пользователей.

Администратору клиента Майкрософт 365 потребуется включить политику "Разрешить сторонние приложения" в Центре администрирования Teams.

Сведения о том, как разрешить сторонние или пользовательские приложения, см. в статье Управление параметрами приложений для всей организации [статьи Управление приложениями в Центре администрирования Майкрософт Teams](/microsoftteams/manage-apps#manage-org-wide-app-settings).

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Отключение NativeFileEntryPoints для всего клиента

Если параметру присвоено `-Identity` значение , `Global` параметры политики будут применены ко всем пользователям в организации.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Пример командлета политики PowerShell для всего клиента

Этот пример команды PowerShell установит`NativeFileEntryPoints` для параметра значение `Disabled` для всего клиента.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Проверка состояния клиента  

Чтобы просмотреть текущее состояние политики файлов Teams клиента, используйте `Get-CsTeamsFilesPolicy` командлет .

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Включение или отключение собственной точки отправки файлов

Чтобы включить или отключить собственную точку отправки файлов для всего клиента, задайте для `NativeFileEntryPoints` параметра значение `Enabled` или `Disabled`.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Удаление политики для пользователей

Чтобы удалить политику файлов Teams для пользователей, используйте `Remove-CsTeamsFilesPolicy` командлет .

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Отключение NativeFileEntryPoints для определенных пользователей

Вы также можете обновить политику файлов Teams для определенных пользователей, создав новую строку политики `-Identity` файлов Teams и назначив только что созданную политику пользователям.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Пример командлета политики PowerShell для определенных пользователей

Этот пример команды PowerShell создаст новый объект с именем как `UserPolicy` и параметром `NativeFileEntryPoints` `Disabled`.`-Identity` `CsTeamsFilesPolicy`

Если пользователю назначается с `-Identity UserPolicy`, его собственные `CsTeamsFilesPolicy` точки входа в файл будут отключены.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Назначение политики пользователю

После создания новой политики ее можно назначить пользователям с помощью командлета `Grant-CsTeamsFilesPolicy` .

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Обновление политики

Если необходимо изменить параметр новой политики `UserPolicy`файлов Teams , используйте `Set-CsTeamsFilePolicy` командлет .

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Удаление политики для полного списка пользователей

Чтобы удалить политику для всех пользователей, назначенных политике `UserPolicy`файлов Teams , используйте `Remove-CsTeamsFilesPolicy` командлет .

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> После внесения изменений в политику разрешите отображение изменений в клиентах Teams пользователей в течение 12 часов.
