---
title: 'Lync Server 2013: проблемы с проверкой среды'
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
ms.openlocfilehash: 65803ff396a9615787291de2d728fe63f3350d0b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Проблемы, связанные с проверкой среды в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Анализатор соответствия рекомендациям позволяет удостовериться в том, что ваша среда Lync Server 2013 является поддерживаемой конфигурацией. В рамках проверки доменных служб Active Directory анализатор соответствия рекомендациям делает следующее:

  - Проверка леса доменных служб Active Directory и подготовки схемы.

  - Определяет количество сайтов и доменов доменных служб Active Directory в развертывании.

  - Проверка уровней леса и домена.

  - Проверяет версию контроллера домена.

  - Определяет контекст именования домена, конфигурации и схемы.

  - Определяет количество включенных пользователей.

  - Проверка хранения глобальных параметров доменных служб Active Directory.

  - Проверка точек соединения службы (Скпс) для Lync Server.

  - Определяет версию базы данных.

<div>

## <a name="resolving-issues-with-the-environment"></a>Устранение проблем с окружающей средой

Если при тестировании среды обнаружены проблемы с вашей средой, это может быть вызвано проблемами с конфигурацией Active Directory или уровнем программного обеспечения, запущенного на определенных серверах. Например, если анализатор соответствия рекомендациям определяет контроллеры домена в среде под управлением Windows Server 2000, он выдаст предупреждение, и вам потребуется обновить эти контроллеры домена до поддерживаемой версии Windows Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

