---
title: 'Lync Server 2013: Настройка политик пользователей для архивации в Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee2074aa9608dad4adcfe85845e7b2e045276f59
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497516"
---
# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Настройка политик пользователей для архивации в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-10_

Для включения или отключения архивации для отдельных пользователей, размещенных в Lync Server 2013, необходимо создать и настроить одну или несколько политик пользователей, а затем применить соответствующую политику к определенным пользователям или группам пользователей. Политики пользователей переопределяют сайт и глобальные политики, но только для пользователей, размещенных в Lync Server 2013.

Пользователи всегда размещены в Lync Server. Если включена интеграция Microsoft Exchange, то для пользователей, чьи почтовые ящики находятся в Microsoft Exchange Server 2013, не нуждаются в политиках архивации в Lync Server Managed. Управление архивацией для этих пользователей осуществляется с помощью Exchange In-Place удержание.

Сведения о том, как работают политики архивации, в том числе иерархия для глобальных политик, политик сайтов и пользователей, приведены в статье Планирование, документация по развертыванию и документация по работе [при архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) .

<div>


> [!NOTE]  
> Если для развертывания включена интеграция с Microsoft Exchange, политики хранения Exchange In-Place контролируют, включено ли архивирование для пользователей, размещенных в Exchange 2013. Для архивации требуется, чтобы почтовые ящики пользователей были помещены на судебное удержание. Дополнительные сведения: <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.<BR>Перед включением архивации необходимо задать все требуемые параметры с помощью конфигураций архивации. Дополнительные сведения приведены в статье <A href="lync-server-2013-configuring-archiving-options.md">Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Создание и Настройка политик пользователей для архивации в Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Применение политики архивации Lync Server к пользователю в Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

