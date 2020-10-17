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
ms.openlocfilehash: c9f4186a351876b874a8b84963f9923369511f65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511826"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Требования к публикации топологии в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

В этом разделе описываются требования к инфраструктуре и программному обеспечению, характерные для публикации топологии, независимо от того, использует ли построитель топологий или интерфейс командной строки командной консоли Lync Server 2013. Эти требования относятся к общим требованиям операционной системы, программного обеспечения и разрешений, которые применяются ко всем административным средствам Lync Server 2013. Перед публикацией топологии убедитесь, что все требования к средствам администрирования соблюдены.

  - Построитель топологий необходимо запускать на компьютере, присоединенном к тому же домену или лесу сервера Lync Server 2013, который вы создаете, чтобы действия по подготовке доменных служб Active Directory были выполнены, позволяя использовать средства администрирования на этом компьютере для успешной публикации топологии.

  - Компьютеры, определенные в топологии, должны быть присоединены к домену, за исключением пограничных серверов, и AD DS. Однако компьютеры необязательно должны быть в сети при публикации топологии.

  - Необходимо создать общий файловый ресурс для пула, который должен быть доступен для удаленных пользователей.

  - Чтобы опубликовать пул переднего плана Enterprise Edition, сервер переднего плана, основанный на SQL Server, должен быть присоединен к домену, в котором развертываются серверы, в сети и настроены соответствующие правила брандмауэра, чтобы сделать его доступным удаленным пользователям. Дополнительные сведения об указании исключений брандмауэра приведены [в статье Общие сведения о требованиях к брандмауэру для SQL Server с Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Дополнительные сведения о настройке SQL Server можно найти в статье [Настройка SQL Server для Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    
    <div>
    

    > [!NOTE]  
    > Сервер Standard Edition имеет размещенную базу данных, которая будет принимать опубликованную конфигурацию. Сначала необходимо запустить задачу " <STRONG>Подготовка первого сервера Standard Edition</STRONG> " в мастере развертывания Lync Server.

    
    </div>

<div>

## <a name="see-also"></a>См. также


[Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  


[Требования к программному обеспечению для средств администрирования в Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Права и разрешения администратора, необходимые для установки и администрирования Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

