---
title: Настройка клиентов для миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 399320fd840391b8d0483b3dc45b62c83311d91f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>Настройка клиентов для миграции

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-11-21_

В этой статье описаны рекомендованные этапы развертывания клиента перед переходом на Lync Server 2013. Эти изменения конфигурации следует вносить в Office Communications Server 2007 R2. Прежде чем выполнять миграцию, очень важно выполнить эти действия. Подробные сведения можно найти [в разделе Планирование клиентов и устройств в Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

<div>

## <a name="to-configure-clients-prior-to-migration"></a>Настройка клиентов перед миграцией

1.  Развертывание самых последних обновлений сервера Office Communications Server 2007 R2, клиентов и устройств (исправлений):
    
      - [Установка обновлений Office Communications Server 2007 R2](apply-office-communications-server-2007-r2-updates.md)
    
      - [Описание накопительного пакета обновления для Communicator 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Получение обновлений программного обеспечения для устройств](http://go.microsoft.com/fwlink/?linkid=335809)

2.  В Office Communications Server 2007 R2 используйте фильтрацию по версии клиента, чтобы разрешить только клиентам Office Communications Server 2007 R2, у которых установлены последние обновления, чтобы войти в систему.

3.  В Office Communications Server 2007 R2 используйте фильтрацию версий клиента, чтобы заблокировать вход в приложение Lync Server 2013 для клиентов. Выполните действия, описанные в статье **Настройка фильтрации клиентских версий** [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) , чтобы добавить фильтры версий, указанные в приведенной ниже таблице. Для каждого фильтра версий назначьте **блок**действий.
    
    
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
    <td><p>OCPhone</p></td>
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

