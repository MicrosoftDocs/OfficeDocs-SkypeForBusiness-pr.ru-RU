---
title: Управление надстройками
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Manage add-ins
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48185204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef4586d0d84d53173f5e27fc504a9911905f1dd5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-add-ins"></a>Управление надстройками

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-06_

Создание новой надстройки для сервера для создания постоянного чата

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

<div>

## <a name="create-get-set-or-remove-an-add-in"></a>Создание, получение, установка и удаление надстройки

Создание новой надстройки

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

<div>


> [!IMPORTANT]  
> Строка &lt;&gt; персистентчатпулфкдн является обязательной только в том случае, если существует несколько пулов серверов сохраняемого чата.



</div>

Получение надстройки

    Get-CsPersistentChatAddin -Identity <String>]

или

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

Настройка надстройки

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

или

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

Удаление надстройки

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

или

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

