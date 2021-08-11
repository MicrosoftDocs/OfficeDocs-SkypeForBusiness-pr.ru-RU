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
description: Узнайте, как использовать поиск контента в Центр соответствия требованиям Microsoft 365 для поиска Microsoft Teams, хранящемся в Exchange Online, SharePoint Online, OneDrive для бизнеса и OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6810355304371564a2a305c82290df7667f5efd41889e598021636cc9ccd11d4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278217"
---
# <a name="use-content-search-in-microsoft-teams"></a>Поиск контента в Microsoft Teams

> [!NOTE]
> Поиск контента в сообщениях и файлах в закрытых [каналах](private-channels.md) работает не так, как в стандартных каналах. Дополнительные информацию см. в [поиске контента в закрытых каналах.](#content-search-of-private-channels)

Поиск контента позволяет запрашивать Microsoft Teams данных, охватывающих Exchange, SharePoint Online и OneDrive для бизнеса.

Дополнительные информацию см. в [Microsoft 365.](/microsoft-365/compliance/content-search)

Например, с  помощью поиска контента в почтовом ящике "Производственные спецификации" и на сайте Manufacturing Specs SharePoint вы можете искать сообщения в стандартном канале Teams из Exchange, отправку файлов и изменения из SharePoint Online и OneNote изменений.

Вы также можете добавить условия запроса для **Поиска контента**, чтобы сузить возвращаемые результаты. В примере выше вы можете найти содержимое, в котором использовались ключевые слова **"New Factory Specs".**

> [!TIP]
> После добавления условий поиска вы можете экспортировать отчет или фактическое содержимое на компьютер для анализа.

## <a name="content-search-of-private-channels"></a>Поиск контента в закрытых каналах

Записи для сообщений, отправленных по частному каналу, доставляются в почтовый ящик всех участников частного канала, а не в групповой почтовый ящик. Названия записей форматируются, чтобы указать, с какого частного канала они были отправлены.

Так как каждый частный канал имеет SharePoint отдельно от родительского сайта группы, управлять файлами в частном канале можно независимо от родительской группы.

Teams не поддерживает поиск контента по одному каналу, поэтому поиск необходимо для всей группы. Чтобы выполнить поиск контента в частном канале, выполните поиск по всей команде, семейому веб-сайту, связанному с частным каналом (чтобы включить файлы), а также почтовым ящикам участников частного канала (чтобы включить сообщения).

Чтобы идентифицировать файлы и сообщения в частном канале, чтобы включить их в поиск контента, с помощью следующих действий:

### <a name="include-private-channel-files-in-a-content-search"></a>Включить файлы частных каналов в поиск контента

Перед выполнением этих действий установите SharePoint Online Management Shell и [подключите его к SharePoint Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. Чтобы получить список всех веб-SharePoint, связанных с частными каналами в группе, запустите следующую команду:

    ```PowerShell
    Get-SPOSite
    ```
2. Запустите следующий сценарий PowerShell, чтобы получить список URL-SharePoint сайтов, связанных с частными каналами в группе и ид родительской группы.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Для каждой группы или ИД группы запустите следующий сценарий PowerShell, чтобы определить все соответствующие сайты частных каналов.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Включить сообщения частного канала в поиск контента

Прежде чем выполнять эти действия, убедитесь, что у вас установлена последняя версия Teams [PowerShell.](teams-powershell-overview.md)

1. Чтобы получить список частных каналов в команде, запустите следующую команду:

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Чтобы получить список участников частного канала, запустите следующую:

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Включите в запрос поиска контента почтовые ящики всех участников из каждого частного канала группы.

## <a name="related-topics"></a>Статьи по теме

- [Дела eDiscovery в Центре Microsoft 365 соответствия требованиям](/Office365/SecurityCompliance/ediscovery-cases)