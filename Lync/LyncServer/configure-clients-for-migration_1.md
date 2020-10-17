---
title: Настройка клиентов для миграции
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99a0b7bfead8f74e27d8539038cf768b1a85b72e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499566"
---
# <a name="configure-clients-for-migration"></a>Настройка клиентов для миграции

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-11-21_

В этой статье описываются рекомендуемые действия по развертыванию клиентов перед переходом на Lync Server 2013. Эти изменения конфигурации следует вносить в Office Communications Server 2007 R2. Эти действия обязательно должны выполняться перед миграцией. Дополнительные сведения см [в разделе Планирование для клиентов и устройств в Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

<div>

## <a name="to-configure-clients-prior-to-migration"></a>Настройка клиентов перед миграцией

1.  Разверните самый последний сервер Office Communications Server 2007 R2, клиентские обновления и обновления устройств (исправления).
    
      - [Применение обновлений Office Communications Server 2007 R2](apply-office-communications-server-2007-r2-updates.md)
    
      - [Описание накопительного пакета обновления для Communicator 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Получение обновлений программного обеспечения для устройств](https://go.microsoft.com/fwlink/?linkid=335809)

2.  В Office Communications Server 2007 R2 используйте фильтрацию версий клиентов, чтобы разрешить вход только клиентам Office Communications Server 2007 R2 с последними установленными обновлениями.

3.  В Office Communications Server 2007 R2 используйте фильтрацию версий клиентов для блокирования входа клиентов Lync Server 2013. Выполните действия, описанные в статье **Настройка фильтрации версий клиентов** , [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) чтобы добавить фильтры версий, перечисленные в следующей таблице. Для каждого фильтра версии назначьте действие **блокировать**.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Клиент</th>
    <th>Заголовок агента пользователя</th>
    <th>Версия</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*.*. *</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*.*. *</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>окфоне</p></td>
    <td><p>4.*.*. *</p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

