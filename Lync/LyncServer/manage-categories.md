---
title: Управление категориями
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Manage categories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48183543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7632c0de3c17c921af05a8daa225364727a3a3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-categories"></a>Manage categories

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-06_

Создание новой категории сервера для сохраняемого чата

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

<div>


> [!IMPORTANT]  
> Персистентчатпулфкдн необходим только в том случае, если существует несколько пулов серверов сохраняемого чата.



</div>

Чтобы внести изменения в существующую категорию сервера сохраняемого чата

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

Windows PowerShell: Алловедмемберс, Дениедмемберс и Creators могут быть установлены одновременно. Создатели должны быть подмножеством Алловедмемберс за вычетом Дениедмемберс. Вы также можете задать свойства категории одновременно с членами и авторами.

<div>

## <a name="create-get-set-or-remove-a-category"></a>Создание, получение, задание и удаление категории

Создание новой категории

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

Получение категории

    Get-CsPersistentChatCategory -Identity <String>

или

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

Настройка категории

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

или

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

Удаление категории

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

или

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

