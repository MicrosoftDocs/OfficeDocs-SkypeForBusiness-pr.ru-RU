---
title: Поиск контента в Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Узнайте, как использовать поиск контента в Microsoft Teams для запроса сведений Microsoft Teams из Exchange, SharePoint Online, OneDrive для бизнеса и OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d05d815a74fc395c06763920014b7de453847bec
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121529"
---
<a name="use-content-search-in-microsoft-teams"></a>Поиск контента в Microsoft Teams
=====================================

> [!NOTE]
> Поиск контента в сообщениях и файлах в частных [каналах](private-channels.md) работает не так, как в стандартных каналах. Подробнее см. в [поиске контента в закрытых каналах.](#content-search-of-private-channels)

Поиск контента позволяет запрашивать сведения в Microsoft Teams, охватывающих Exchange, SharePoint Online и OneDrive для бизнеса.

Чтобы узнать больше, ознакомьтесь с [поиском контента в Microsoft 365 или Office 365.](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)

Например, используя  поиск контента для почтового ящика производственной спецификации и сайта SharePoint по производственным спецификациям, вы можете искать беседы стандартных каналов Teams из Exchange, отправку файлов и изменения из SharePoint Online и OneNote.

Вы также можете добавить условия запроса для **Поиска контента**, чтобы сузить возвращаемые результаты. В примере выше можно найти содержимое, в котором использовались ключевые слова **"New Factory Specs".**

> [!TIP]
> После добавления условий поиска вы можете экспортировать отчет или данные на компьютер для анализа.

## <a name="content-search-of-private-channels"></a>Поиск контента в закрытых каналах

Записи для сообщений, отправленных по частному каналу, доставляются в почтовый ящик всех участников частного канала, а не в групповой почтовый ящик. Названия записей форматируются, чтобы указать, с какого частного канала они были отправлены.

Так как у каждого частного канала есть собственное веб-собрание SharePoint, которое отделено от родительского сайта группы, управление файлами в частном канале не отделялось от родительской команды.

Teams не поддерживает поиск контента в одном канале, поэтому необходимо искать вся команда. Чтобы выполнить поиск контента в частном канале, выполните поиск в группе, в семейсе веб-сайтов, связанном с закрытым каналом (чтобы включить файлы), а также в почтовых ящиках участников частного канала (включая сообщения).

Чтобы идентифицировать файлы и сообщения в частном канале, чтобы включить их в поиск контента, с помощью следующих действий:

### <a name="include-private-channel-files-in-a-content-search"></a>Включить файлы частных каналов в поиск контента

Перед выполнением этих действий установите управляющую оболочку [SharePoint Online и подключитесь к SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. Чтобы получить список всех коллекций веб-сайтов SharePoint, связанных с частными каналами в группе, запустите следующую команду:

    ```PowerShell
    Get-SPOSite
    ```
2. Запустите следующий сценарий PowerShell, чтобы получить список URL-адресов всех сайтов sharePoint, связанных с частными каналами в группе, и их ИД родительской группы.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Чтобы определить все соответствующие сайты частных каналов, запустите следующий сценарий PowerShell для каждой группы или группы:

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Включить сообщения частного канала в поиск контента

Перед выполнением этих действий убедитесь, что установлена последняя версия [модуля Teams PowerShell.](teams-powershell-overview.md)

1. Чтобы получить список частных каналов в команде, запустите следующую команду:

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Чтобы получить список участников частного канала, запустите следующую ссылку:

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Включите в запрос поиска контента почтовые ящики всех участников каждого частного канала в команду.

## <a name="related-topics"></a>Статьи по теме

- [Дела eDiscovery в Центре соответствия требованиям Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 