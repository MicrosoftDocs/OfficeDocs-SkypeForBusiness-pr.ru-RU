---
title: 'Lync Server 2013: Проверка структуры топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 361713c22842abee7de1d8e29de498f4d4ad5cc7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a>Проверка структуры топологии в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-01-02_

В построителе топологий автоматически проверяется топология. Любая ошибка топологии считается ошибкой проверки и обозначается значком ошибки проверки рядом с ролью сервера. Важно также проверить, что топология правильно представляет топологию вашего развертывания.

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>Проверка топологии до публикации

1.  Проверьте, что все простые URL-адреса настроены правильно.

2.  Убедитесь, что сервер на основе SQL Server подключен к сети и доступен компьютеру, на котором установлен построитель топологий, включая все необходимые правила брандмауэра.

3.  Проверьте, что файловое хранилище доступно и для него заданы необходимые разрешения.

4.  Проверьте, что в топологии заданы правильные роли сервера, удовлетворяющие требованиям развертывания.

5.  Убедитесь, что серверы существуют в доменных службах Active Directory. Это осуществляется автоматически, если серверы присоединены к домену.

Когда топология проверена и ошибки проверки отсутствуют, все должно быть готово к публикации топологии. Если имеются ошибки проверки, то перед публикацией топологии их необходимо исправить. Сведения о публикации топологии приведены [в статье публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

