---
title: 'Lync Server 2013: Настройка политик архивации для пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58d7b149c55d8daac9cb47f5e3ab0e1b4ea0596
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509736"
---
# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a>Настройка политик архивации для пользователей в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-09_

Вы можете включить или отключить архивацию для отдельных пользователей, создав и настроив для пользователей политику архивации, а затем применив ее к отдельным пользователям или группам пользователей. Политики пользователей переопределяют любую глобальную политику и политики сайтов. Политики архивации применяются только в том случае, если вы не используете интеграцию с Microsoft Exchange или если вы используете интеграцию Microsoft Exchange, но у вас есть некоторые пользователи, которые не размещены в Exchange 2013 и почтовые ящики помещаются на In-Place удержание.

Сведения о том, как работают политики архивации, в том числе иерархия глобальных, сайтов и пользовательских политик, приведены в статье Планирование [работы архивации в среде Lync Server 2013](lync-server-2013-how-archiving-works.md) , документация по развертыванию или документация по операциям.

<div>


> [!NOTE]  
> Если для развертывания включена интеграция с Microsoft Exchange, политики хранения Exchange In-Place контролируют, включена ли архивация для пользователей, размещенных в Exchange 2013, и почтовые ящики помещаются на In-Place удержание. Дополнительные сведения: <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.<BR>Чтобы включить архивацию внутренних и внешних коммуникаций в политиках архивации, вы должны указать все соответствующие параметры конфигураций архивации. Дополнительные сведения приведены в статье <A href="lync-server-2013-configuring-archiving-options.md">Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка политик пользователей для архивации в Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [Настройка политик архивации в Lync Server 2013 при использовании интеграции с Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

