---
title: Поиск контента в Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Сведения об использовании поиска контента в Портал соответствия требованиям Microsoft Purview для поиска содержимого Microsoft Teams, хранимого в Exchange Online, SharePoint Online, OneDrive для бизнеса и OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b976c5e3c6467a6c71bb51eb1ff3ef720813584b
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808240"
---
# <a name="use-content-search-in-microsoft-teams"></a>Использование поиска контента в Microsoft Teams

> [!NOTE]
> Поиск контента сообщений и файлов в [частных каналах](private-channels.md) работает иначе, чем в стандартных каналах. Дополнительные сведения см. в [разделе "Поиск контента частных каналов"](#content-search-of-private-channels).

Поиск контента позволяет запрашивать сведения Microsoft Teams, охватывающие Exchange, SharePoint Online и OneDrive для бизнеса.

Дополнительные сведения см. в [разделе "Поиск контента" в Microsoft 365](/microsoft-365/compliance/content-search).

Например, с помощью  поиска контента в почтовом ящике "Производственные спецификации" и сайте Производственные спецификации SharePoint можно выполнять поиск по стандартным беседам каналов Teams из Exchange, отправке файлов и изменениям из SharePoint Online и изменений OneNote.

Вы также можете добавить условия запроса для **Поиска контента**, чтобы сузить возвращаемые результаты. В приведенном выше примере можно найти содержимое, в котором использовались ключевые слова **"Новые** спецификации фабрики".

> [!TIP]
> После добавления условий поиска можно экспортировать отчет или фактическое содержимое на компьютер для анализа.

## <a name="content-search-of-private-channels"></a>Поиск контента в частных каналах

Записи для сообщений, отправленных по частному каналу, доставляются в почтовый ящик всех участников частного канала, а не в групповой почтовый ящик. Названия записей форматируются, чтобы указать, с какого частного канала они были отправлены.

Так как каждый частный канал имеет собственное семейство веб-сайтов SharePoint, отдельное от родительского сайта группы, управление файлами в частном канале выполняется независимо от родительской команды.

Teams не поддерживает поиск контента одного канала, поэтому поиск должен выполняться всей командой. Чтобы выполнить поиск контента частного канала, выполните поиск по всей команде, семейство веб-сайтов, связанное с частным каналом (чтобы включить файлы), и почтовые ящики участников закрытого канала (чтобы включить сообщения).

Выполните следующие действия, чтобы определить файлы и сообщения в частном канале, чтобы включить их в поиск контента.

### <a name="include-private-channel-files-in-a-content-search"></a>Включение файлов частного канала в поиск контента

Перед выполнением этих действий установите [консоль управления SharePoint Online и подключитесь к SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Выполните следующую команду, чтобы получить список всех семейств веб-сайтов SharePoint, связанных с частными каналами в команде.

    ```PowerShell
    Get-SPOSite
    ```
2. Выполните следующий сценарий PowerShell, чтобы получить список всех URL-адресов семейства веб-сайтов SharePoint, связанных с частными каналами в команде и идентификатором родительской группы.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Для каждой команды или группы выполните следующий сценарий PowerShell, чтобы определить все соответствующие сайты частных каналов.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Включение сообщений частного канала в поиск контента

Перед выполнением этих действий убедитесь, что установлена последняя версия [модуля Teams PowerShell](teams-powershell-overview.md) .

1. Выполните следующую команду, чтобы получить список частных каналов в команде.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Выполните следующую команду, чтобы получить список участников закрытого канала.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Включите почтовые ящики всех участников из каждого закрытого канала в команду в качестве части запроса на поиск контента.

## <a name="related-topics"></a>См. также

- [Дела обнаружения электронных данных в Портал соответствия требованиям Microsoft Purview](/Office365/SecurityCompliance/ediscovery-cases)