---
title: 'Lync Server 2013: поддерживаемые пути миграции и сценарии сосуществования серверов'
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
ms.openlocfilehash: 1b16b0c92954c004aa04b9cc665786badb9bf632
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Поддерживаемые пути миграции и сценарии сосуществования серверов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-16_

Lync Server 2013 поддерживает миграцию с любого из следующих вариантов:

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

Миграция из среды, использующей оба эти предыдущих версии, не поддерживается. Миграция с более ранних версий, например Microsoft Office Communications Server 2007 или Live Communications Server 2005, не поддерживается. Если Ваше прежнее развертывание включало групповой чат, его необходимо перенести отдельно.

<div>

## <a name="migration-methods"></a>Способы миграции

Поддерживается миграция всех топологий Lync Server и серверных ролей. Вы можете выполнить миграцию из одной топологии в другую, например с сервера Standard Edition на сервер Enterprise Edition.

Lync Server 2013 поддерживает только следующий способ миграции:

  - <span></span>  
    **Переход с одной стороны на другую.** При переходе по отдельности Lync Server 2013 разворачивается вместе с существующим развертыванием Microsoft Lync Server 2010 или Office Communications Server 2007 R2, а затем переносятся на новые серверы и перемещаются на Lync Server 2013. Для использования этого метода требуются дополнительные серверные платформы, в том числе оборудование и программное обеспечение, и имена систем и пулов различаются в новой конфигурации. Если вы хотите вернуться к предыдущей версии, вы можете переместить операции обратно на предыдущие серверы.

Миграция в лесах доменных служб Active Directory не поддерживается.

Рекомендуемый путь миграции — поэтапный подход. Сведения о переходе с более ранней версии, включая соответствующие фазирование развертывания компонентов, можно найти в следующих статьях в документации по миграции.

  - [Миграция с Lync Server 2010 на Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Миграция с Office Communications Server 2007 R2 на Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Миграция с групповой беседы в Lync Server 2010 или Office Communications Server 2007 R2 на сервер сохраняемого сеанса беседы в Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>Сценарии сосуществования

Lync Server 2013 может сосуществовать с компонентами либо развертыванием Lync Server 2010, либо развертыванием Office Communications Server 2007 R2. Одновременное развертывание Lync Server 2013 с помощью Lync Server 2010 и Office Communications Server 2007 R2 (параллельное развертывание всех трех версий) не поддерживается.

При поэтапной миграции, когда более раннее развертывание Lync Server 2010 или Office Communications Server 2007 R2 входит в состав нового развертывания Lync Server 2013, поддержка маршрутизации для смешанной версии ограничена. Подробности можно найти в документации по миграции.

Для экземпляров базы данных Lync Server 2013 вы должны использовать отдельные и различные компьютеры с Microsoft SQL Server 2008 R2 или Microsoft SQL Server 2012. Вы не можете использовать один и тот же экземпляр SQL Server для пула внешних интерфейсов Lync Server 2013, который вы используете для пула интерфейсов Lync Server 2010 или Office Communications Server 2007 R2. Если вы определили и настроили Lync Server 2013 в построителе топологии для развертывания, у которого уже есть Lync Server 2010 или Office Communications Server 2007 R2, построитель топологии не позволит определить экземпляр Lync Server 2013, который уже используется в Topology (топология).

В построителе топологии появится следующее сообщение об этой ошибке: " \[полное доменное имя SQL Server сервера\] уже включает в себя роль размещения экземпляров SQL" User Store ".

<div>


> [!NOTE]  
> Если вы планируете развертывать роли сервера, которые являются новыми для развертывания Lync Server 2013, необходимо сначала обновить существующее развертывание, как описано в документации по миграции и в документации по развертыванию, а затем развернуть новые роли сервера, как описано в разделе Документация по планированию и руководство по развертыванию. Если вы переносите предыдущую версию группового чата, перенесите ее в последнюю очередь после завершения процесса миграции всех остальных компонентов из Lync Server 2010 или Office Communications Server 2007 R2.



</div>

Для конкретных требований сосуществования и других сведений о сосуществовании и миграции компонентов Lync Server 2010 или Office Communications Server 2007 R2 и Lync Server 2013 ознакомьтесь со статьей [Переход с Lync server 2010 на Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) и [Переход с Office Communications Server 2007 R2 на](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) Lync Server 2013 в документации по миграции. Подробнее о поддержке клиентов смешанной версии можно узнать [в разделе Поддерживаемые клиенты предыдущих развертываний в Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

