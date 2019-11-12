---
title: Поиск контента в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
description: Узнайте о поиске контента в Microsoft Teams, а также о том, как выполнять поиск по каналам связи в Exchange, отправлять файлы и изменения из SharePoint и вносить изменения в OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3042a39d30ca14ff4eda9be6a1042bfca3484bd2
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231160"
---
<a name="use-content-search-in-microsoft-teams"></a>Поиск контента в Microsoft Teams
=====================================

> [!NOTE]
> Поиск контента сообщений и файлов в [закрытых каналах](private-channels.md) отличается от работы со стандартными каналами. Дополнительные сведения можно найти в разделе [Поиск контента в частных каналах](#content-search-of-private-channels).

Поиск контента позволяет запрашивать сведения о Microsoft Teams, попадающее в Exchange, SharePoint Online и OneDrive для бизнеса.

Подробнее читайте [в статье Поиск содержимого в Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).

Например, с помощью **поиска по содержимому** на веб-сайте SharePoint specs and specs можно выполнять поиск по стандартным каналам связи в Exchange, отправлять файлы и изменения из SharePoint Online и вносить изменения в OneNote.

Вы также можете добавить условия запроса для **Поиска контента**, чтобы сузить возвращаемые результаты. В приведенном выше примере вы можете найти содержимое, в котором использовались ключевые слова "**новые спецификации фабрики"** .

> [!TIP]
> После добавления условий поиска вы можете экспортировать отчет или данные на компьютер для анализа.

## <a name="content-search-of-private-channels"></a>Поиск контента в частных каналах

Записи для сообщений, отправленных в частном канале, доставляются в почтовый ящик всех участников личного канала, а не в почтовом ящике группы. Заголовки записей форматируются для обозначения закрытого канала, с которого они были отправлены.

Поскольку каждый частный канал имеет собственную коллекцию сайтов SharePoint, отделенную от родительского сайта группы, файлы в частном канале управляются независимо от родительской команды.

Команды не поддерживают поиск контента в одном канале, поэтому для всей команды нужно выполнить поиск. Чтобы выполнить поиск контента в частном канале, выполните поиск по команде, в семействе веб-сайтов, связанном с частным каналом (для включения файлов), и почтовых ящиков участников личного канала (для включения сообщений).

Выполните указанные ниже действия, чтобы определить файлы и сообщения в частном канале, чтобы включить в поиск контента.

### <a name="include-private-channel-files-in-a-content-search"></a>Включение файлов закрытого канала в поиск контента

Перед выполнением этих действий установите [командную консоль SharePoint Online и подключитесь к SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Выполните указанные ниже действия, чтобы получить список всех семейств веб-сайтов SharePoint, связанных с частными каналами в команде.

    ```
    Get-SPOSite
    ```
2. Запустите следующий сценарий PowerShell, чтобы получить список всех URL-адресов семейств веб-сайтов SharePoint, связанных с частными каналами в команде и ИДЕНТИФИКАТОРом родительской группы групп.

    ```
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Для каждого кода группы или группы выполните следующий сценарий PowerShell для идентификации всех соответствующих сайтов закрытого канала.

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Включение сообщений личного канала в поиск контента

Перед выполнением этих действий убедитесь в том, что у вас установлена [новейшая версия модуля Teams PowerShell](teams-powershell-overview.md) .

1. Выполните указанные ниже действия, чтобы получить список частных каналов в команде.

    ```
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Выполните указанные ниже действия, чтобы получить список участников личного канала.

    ```
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Включите в поисковый запрос содержимого почтовые ящики всех участников группы из любого закрытого канала.

## <a name="related-topics"></a>См. также

- [варианты обнаружения электронных данных в центре безопасности & Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 