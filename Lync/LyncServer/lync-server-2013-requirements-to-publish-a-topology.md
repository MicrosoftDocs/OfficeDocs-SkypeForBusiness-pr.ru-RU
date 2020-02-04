---
title: 'Lync Server 2013: требования к публикации топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f1422df35ebbe9f368dc8aa3d121caf740e7033
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Требования к публикации топологии в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

В этой статье описаны требования к инфраструктуре и программному обеспечению, специфичные для публикации топологии, будь то использование построителя топологии или интерфейса командной строки оболочки управления Lync Server 2013. Эти требования описаны в дополнение к общим требованиям операционной системы, программного обеспечения и разрешений, применимым ко всем административным средствам Lync Server 2013. Прежде чем публиковать топологию, убедитесь, что все требования к средству администрирования соблюдены.

  - Вы должны запустить построитель топологии на компьютере, который присоединен к тому же домену или лесу Lync Server 2013, который вы создаете, чтобы вы могли завершить процесс подготовки доменных служб Active Directory, что позволит вам использовать средства администрирования на Этот компьютер для успешной публикации топологии.

  - Компьютеры, определенные в топологии, должны быть присоединены к домену, за исключением пограничных серверов и доменных служб Active Directory. Однако при публикации топологии компьютеры не должны быть подключены к сети.

  - Файловый общий доступ для пула должен быть создан и доступен для удаленных пользователей.

  - Для публикации пула переднего плана Enterprise Edition сервер должен быть присоединен к домену, в котором развертываются серверы, в сети и настроены соответствующие правила брандмауэра, чтобы сделать его доступным для удаленных пользователей. Подробнее об указании исключений межсетевого экрана можно узнать [в разделе сведения о требованиях к межсетевому экрану SQL Server с помощью Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Дополнительные сведения о настройке SQL Server можно найти в разделе [Настройка SQL Server для Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    
    <div>
    

    > [!NOTE]  
    > Сервер Standard Edition имеет размещенную базу данных, которая будет поддерживать опубликованную конфигурацию. Сначала необходимо запустить задачу настройки <STRONG>сервера first Standard Edition</STRONG> в мастере развертывания Lync Server.

    
    </div>

<div>

## <a name="see-also"></a>См. также


[Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  


[Программные требования для средств администрирования в Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Поддержка сервера и средств в операционной системе в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Административные права и разрешения, необходимые для установки и администрирования Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

