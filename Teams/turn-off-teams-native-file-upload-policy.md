---
title: Отключение собственной политики отправки файлов Teams
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
ms.collection:
- M365-collaboration
ms.openlocfilehash: 1993371099d0712d21106987f21575e85e181ad7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268931"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Отключение собственной политики отправки файлов Teams

Microsoft Teams использует OneDrive и SharePoint для хранения и совместного использования содержимого, но некоторые организации и пользователи могут использовать сторонних поставщиков хранилищ.  

Если ваша организация выбирает стороннего поставщика для хранения содержимого, `NativeFileEntryPoints` необходимо отключить параметр в политике файлов Teams. Этот параметр включен по умолчанию, который показывает возможность передачи содержимого из OneDrive или SharePoint в чаты или каналы Teams.

Эта статья поможет вам создать, задать, назначить и удалить параметр `NativeFileEntryPoints` с помощью PowerShell.

>[!NOTE]
>Если политика файлов Teams отключена, пользователи не будут видеть точки доступа для OneDrive и SharePoint в Teams, но создание новых команд и каналов будет активировать создание соответствующих библиотек SharePoint.

## <a name="prepare-to-update-the-teams-files-policy"></a>Подготовка к обновлению политики файлов Teams

### <a name="set-up-microsoft-powershell"></a>Настройка Microsoft PowerShell

В настоящее время эту политику нельзя изменить в Центре администрирования Teams. Администратору клиента Microsoft 365 вашей организации придется внести изменения с помощью командлетов PowerShell, описанных далее в этой статье.

Узнайте, как установить модуль PowerShell Teams с коллекция PowerShell, прочитав статью ["Установка модуля Microsoft Teams PowerShell"](teams-powershell-install.md).

Сведения об установке или скачии модуля Teams PowerShell [см. коллекция PowerShell microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Дополнительные сведения о настройке PowerShell для управления Teams см. в разделе ["Управление Teams с помощью Microsoft Teams PowerShell"](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Разрешить сторонние приложения в Teams Администратор Center

Этот шаг не требуется для изменения политики файлов Teams, но он необходим, когда вы будете готовы интегрировать стороннего поставщика хранилища в интерфейс Teams пользователей.

Администратору клиента Microsoft 365 потребуется включить политику "Разрешить сторонние приложения" в Центре администрирования Teams.

Сведения о том, как разрешить сторонние или пользовательские приложения, см. в статье "Управление параметрами приложений на уровне организации" в разделе "Управление приложениями" в [Центре администрирования Microsoft Teams](/microsoftteams/manage-apps#manage-org-wide-app-settings).

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Отключение NativeFileEntryPoints для всего клиента

Настройка параметра `-Identity` будет `Global` применять параметры политики ко всем пользователям в организации.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Пример командлета политики PowerShell для всего клиента

В этом примере команды PowerShell будет задано`NativeFileEntryPoints` значение параметра `Disabled` для всего клиента.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Проверка состояния клиента  

Чтобы просмотреть текущее состояние политики файлов Teams клиента, используйте `Get-CsTeamsFilesPolicy` командлет.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Включение или отключение собственной точки отправки файлов

Чтобы включить или отключить собственную точку отправки файлов для всего клиента, `NativeFileEntryPoints` задайте для параметра значение либо `Disabled``Enabled` .

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Удаление политики для пользователей

Чтобы удалить политику файлов Teams для пользователей, используйте `Remove-CsTeamsFilesPolicy` командлет.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Отключение NativeFileEntryPoints для определенных пользователей

Вы также можете обновить политику файлов Teams для определенных пользователей, создав новую строку политики файлов Teams `-Identity` и назначив только что созданную политику пользователям.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Пример командлета политики PowerShell для определенных пользователей

В этом примере команды PowerShell будет создаваться `CsTeamsFilesPolicy` `-Identity` новая команда с именем и `UserPolicy` параметром `NativeFileEntryPoints` , для параметра установлено значение `Disabled`.

Если пользователю назначено значение `CsTeamsFilesPolicy` with `-Identity UserPolicy`, его собственные точки входа в файл будут отключены.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Назначение политики пользователю

После создания новой политики ее можно назначить пользователям с помощью командлета `Grant-CsTeamsFilesPolicy` .

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Обновление политики

Если необходимо изменить параметр новой политики файлов Teams `UserPolicy`, используйте `Set-CsTeamsFilePolicy` командлет.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Удаление политики для полного списка пользователей

Чтобы удалить политику из всех пользователей, назначенных политике файлов Teams `UserPolicy`, используйте `Remove-CsTeamsFilesPolicy` командлет.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> После внесения изменений в политику разрешите отображение изменений в клиентах Teams пользователей в течение 12 часов.
