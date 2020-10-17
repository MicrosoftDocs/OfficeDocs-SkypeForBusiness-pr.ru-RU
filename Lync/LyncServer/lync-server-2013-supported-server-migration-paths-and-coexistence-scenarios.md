---
title: 'Lync Server 2013: Поддерживаемые пути миграции серверов и сценарии сосуществования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ed7689931cf917c77527266918832ead8bd0a27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523976"
---
# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Поддерживаемые пути миграции и сценарии сосуществования серверов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-16_

Lync Server 2013 поддерживает миграцию из одного из следующих компонентов:

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

Миграция из среды, где запущены обе эти предыдущие версии, не поддерживается. Миграция с более ранних версий, например, Microsoft Office Communications Server 2007 или Live Communications Server 2005, не поддерживается. Если предыдущее развертывание включало групповой чат, его необходимо перенести отдельно.

<div>

## <a name="migration-methods"></a>Способы миграции

Поддерживается миграция всех топологий Lync Server и ролей сервера. Вы можете выполнять миграцию с одной топологии на другую, включая миграцию с сервера Standard Edition на сервер Enterprise Edition.

Lync Server 2013 поддерживает только следующий метод миграции:

  - <span></span>  
    **Параллельная миграция.** При параллельной миграции Lync Server 2013 разворачивается вместе с существующим развертыванием Microsoft Lync Server 2010 или Office Communications Server 2007 R2, а затем выполняется передача операций на новые серверы и перемещение пользователей на Lync Server 2013. При использовании этого способа миграции требуются дополнительные серверные платформы, включая оборудование и программное обеспечение, а имена систем и пулов в новой конфигурации отличаются. Если требуется выполнить откат до предыдущей версии, операции можно перенести обратно на предыдущие серверы.

Миграция между лесами доменных служб Active Directory не поддерживается.

Рекомендуемый путь миграции представляет собой поэтапный подход. Дополнительные сведения о миграции с предыдущего выпуска, включая правильное разделение развертывания компонентов на этапы, см. в следующих разделах документации по миграции:

  - [Миграция с Lync Server 2010 на Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Миграция с Office Communications Server 2007 R2 на Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Миграция с групповой беседы в Lync Server 2010 или Office Communications Server 2007 R2 на сервер сохраняемого сеанса беседы в Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>Сценарии сосуществования

Lync Server 2013 может сосуществовать с компонентами или развертыванием Lync Server 2010 или Office Communications Server 2007 R2. Параллельное развертывание Lync Server 2013 со средой Lync Server 2010 и Office Communications Server 2007 R2 (параллельное развертывание всех трех версий) не поддерживается.

При поэтапной миграции, когда предыдущее развертывание Lync Server 2010 или Office Communications Server 2007 R2 временно существует с новым развертыванием Lync Server 2013, поддержка маршрутизации смешанных версий ограничена. Дополнительные сведения см. в документации по миграции.

Для экземпляров базы данных Lync Server 2013 необходимо использовать отдельные и разные компьютеры, на которых работает Microsoft SQL Server 2008 R2 или Microsoft SQL Server 2012. Нельзя использовать один и тот же экземпляр SQL Server для интерфейсного пула Lync Server 2013, который используется для интерфейсного пула Lync Server 2010 или Office Communications Server 2007 R2. Если вы определили и настроили Lync Server 2013 в построителе топологий для развертывания, в котором уже есть Lync Server 2010 или Office Communications Server 2007 R2, построитель топологий не позволит определить экземпляр сервера Lync Server 2013, который уже используется в топологии.

В построителе топологий отобразится следующее сообщение об этой ошибке: " \[ полное доменное имя SQL Server \] уже содержит роль размещения экземпляра SQL" хранилище пользователей "."

<div>


> [!NOTE]  
> Если вы планируете развертывать роли сервера, которые являются новыми для развертывания Lync Server 2013, необходимо сначала обновить существующее развертывание, как описано в документации по миграции и в документации по развертыванию, а затем развернуть новые роли сервера, как описано в документации по планированию и документации по развертыванию. Если вы переносите предыдущую версию группового чата, перенесите ее последним, после завершения процесса переноса всех остальных компонентов с Lync Server 2010 или Office Communications Server 2007 R2.



</div>

Сведения о специальных требованиях к сосуществованию и других сведениях о сосуществовании и переносе компонентов Lync Server 2010 или Office Communications Server 2007 R2 и Lync Server 2013 приведены в статье [Миграция с Lync server 2010 to Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) и [Миграция с Office Communications Server 2007 R2 на Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) в документации по миграции. Подробные сведения о поддержке разных версий для клиентов приведены [в статье Поддерживаемые клиенты из предыдущих развертываний в Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

