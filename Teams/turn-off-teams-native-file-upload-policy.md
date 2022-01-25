---
title: Отключение политики Teams файлов Upload файлов
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Узнайте, как создавать, задавать, назначать и настраивать политику Teams файлов с помощью PowerShell.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64bd9d23527ef1a63df4f258e89de5e60862a878
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192506"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Отключение политики Teams файлов Upload файлов

Microsoft Teams ODSP использует OneDrive и SharePoint (ODSP), но некоторые организации и пользователи предпочитают использовать сторонних поставщиков хранилищ.  

Если в вашей организации для хранения содержимого задан сторонний вариант, необходимо отключить параметр в политике Teams ``NativeFileEntryPoints`` файлов. Этот параметр включен по умолчанию, в котором показана возможность отправки содержимого из ODSP в Teams чаты или каналы.

Эта статья поможет вам создать, задать, назначить и удалить параметр ``NativeFileEntryPoints`` с помощью PowerShell.

>[!NOTE]
>После отключения политики Teams Files пользователи не увидят точки доступа для OneDrive и SharePoint (ODSP) в Teams, но создание новых команд и каналов будет продолжать вызывать создание совпадающих библиотек SharePoint.

## <a name="prepare-to-update-the-teams-files-policy"></a>Подготовка к обновлению политики Teams файлов

### <a name="set-up-microsoft-powershell"></a>Настройка Microsoft PowerShell

В настоящее время эту политику нельзя изменить в центре Teams администрирования. Администратору клиента Microsoft 365 организации придется внести изменения с помощью подробных инструкций PowerShell далее в этой статье.

Узнайте, как установить модуль PowerShell Teams с помощью коллекции PowerShell, прочитав статью Установка Microsoft Teams [PowerShell.](teams-powershell-install.md)

Чтобы установить или скачать модуль Teams PowerShell, см. коллекции [PowerShell для Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0)

Дополнительные сведения о том, как настроить PowerShell для управления Teams, см. в Teams с помощью [Microsoft Teams PowerShell.](teams-powershell-managing-teams.md)

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Разрешение сторонних приложений в Teams администрирования

Этот шаг не требуется для изменения политики Teams файлов, но он необходим, когда вы будете готовы интегрировать стороного поставщика хранилища с Teams пользователями.

Администратору Microsoft 365 клиента потребуется включить политику "Разрешить сторонние приложения" в Центре администрирования Teams приложений.

Чтобы узнать, как разрешить сторонние или пользовательские приложения, см. управление настройками приложений для всей организации в Microsoft Teams [центре администрирования.](/microsoftteams/manage-apps#manage-org-wide-app-settings)

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Отключение NativeFileEntryPoints для всего клиента

Настройка ``-Identity`` параметра ``Global`` применяет параметры политики для всех пользователей в организации.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Пример cmdlet политики PowerShell для всего клиента

В этом примере для команды PowerShell будет задан ``NativeFileEntryPoints`` параметр ``Disabled`` для всего клиента.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Проверка состояния клиента  

Чтобы просмотреть текущее состояние политики файлов Teams клиента, воспользуйтесь ``Get-CsTeamsFilesPolicy`` этим cmdlet.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Включите или отключите точки отправки файлов на языке

Чтобы включить или отключить точки отправки файлов для всего клиента, задайте для параметра ``NativeFileEntryPoints`` либо ``Enabled`` либо ``Disabled`` .

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Удаление политики для пользователей

Чтобы удалить политику Teams файлов для пользователей, воспользуйтесь ``Remove-CsTeamsFilesPolicy`` этим cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Отключение NativeFileEntryPoints для определенных пользователей

Вы также можете обновить политику Teams файлов для определенных пользователей, создав новую строку политики Teams файлы и назначив новую политику ``-Identity`` пользователям.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Пример cmdlet политики PowerShell для определенных пользователей

В этом примере с помощью команды PowerShell будет создана новая команда с именем ``CsTeamsFilesPolicy`` ``-Identity`` "как" ``UserPolicy`` и ``NativeFileEntryPoints`` параметром , заданным для ``Disabled`` .

Когда пользователю назначено с , собственные точки входа в файл ``CsTeamsFilesPolicy`` ``-Identity UserPolicy`` будут отключены.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Назначение политики пользователю

Создав новую политику, вы можете назначить ее пользователям с помощью ``Grant-CsTeamsFilesPolicy`` этого cmdlet.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Обновление политики

Если вам нужно изменить параметр новой политики Teams файлов ``UserPolicy`` , используйте ``Set-CsTeamsFilePolicy`` этот cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Удаление политики для полного списка пользователей

Чтобы удалить политику для всех пользователей, которые назначены политике Teams файлов ``UserPolicy`` , используйте ``Remove-CsTeamsFilesPolicy`` этот cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> После внесения изменений в политику в течение 12 часов эти изменения будут демонстрироваться в клиентах Teams пользователей.
