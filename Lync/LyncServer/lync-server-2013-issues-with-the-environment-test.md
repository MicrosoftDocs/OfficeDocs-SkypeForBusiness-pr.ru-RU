---
title: 'Lync Server 2013: проблемы с тестом среды'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 812796be0589342f346cfc6755ace64cb402f63a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514086"
---
# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Проблемы, связанные с проверкой среды в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Анализатор соответствия рекомендациям позволяет убедиться, что ваша среда Lync Server 2013 является поддерживаемой конфигурацией. В рамках проверки доменных служб Active Directory анализатор соответствия рекомендациям выполняет следующие действия:

  - проверяет лес доменных служб Active Directory и подготовку схемы;

  - определяет число сайтов и доменов доменных служб Active Directory в развертывании;

  - проверяет уровни лесов и доменов;

  - проверяет версию контроллера домена;

  - определяет домен, конфигурацию и контекст именования схемы;

  - определяет число пользователей с включенной поддержкой;

  - проверяет место хранения глобальных параметров доменных служб Active Directory;

  - Проверяет наличие точек подключения службы (Скпс) для Lync Server.

  - определяет версию базы данных.

<div>

## <a name="resolving-issues-with-the-environment"></a>Устранение проблем со средой

Если тестирование среды выявило неполадки, вероятно, они вызваны проблемами с конфигурацией Active Directory или уровнем программного обеспечения, запущенного на конкретных серверах. Например, если анализатор соответствия рекомендациям обнаруживает в среде контроллеры домена, работающие под управлением Windows Server 2000, он выдает предупреждение, и вам потребуется обновить такие контроллеры до поддерживаемой версии Windows Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

