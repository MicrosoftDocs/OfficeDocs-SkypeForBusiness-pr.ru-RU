---
title: 'Lync Server 2013: компоненты и топологии для мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 065cab8b4db7ecbc764ab8a8c6168c88fe1afd50
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Компоненты и топологии для мониторинга в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-05_

Поскольку агенты сбора универсальных данных автоматически устанавливаются и активируются на каждом сервере переднего плана, не требуется настраивать сервер для работы в качестве сервера мониторинга; каждый сервер переднего плана уже функционирует как сервер мониторинга. Однако потребуется установить и настроить базу данных для работы в качестве внутреннего хранилища данных мониторинга. Microsoft Lync Server 2013 может использовать любую из следующих баз данных в качестве серверного хранилища для мониторинга.

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

Обратите внимание, что вы должны использовать 64-разрядные выпуски этих баз данных; 32-разрядные выпуски SQL Server не могут использоваться в качестве внутреннего хранилища данных мониторинга. Аналогично, Lync Server 2013 не поддерживает Экспресс выпуски SQL Server 2008 или SQL Server 2012. Дополнительные сведения о требованиях к базе данных для Lync Server 2013 приведены в статье [Поддержка программного обеспечения баз данных в Lync server 2013](lync-server-2013-database-software-support.md) в руководстве по поддержке lync Server 2013.

Помните, что SQL Server необходимо установить и настроить до развертывания и настройки мониторинга. Однако достаточно развернуть сам SQL Server; не нужно заранее настраивать базы данных наблюдения. Вместо этого эти базы данных будут автоматически созданы при публикации топологии Lync Server.

Данные наблюдения могут совместно использовать экземпляр SQL Server с другими типами данных. Обычно база данных регистрации вызовов (LcsCdr) и база данных качества взаимодействия (QoEMetrics) совместно используют один экземпляр SQL; также распространены случаи, когда две базы данных мониторинга находятся в одном экземпляре SQL с базой данных архивации (LcsLog). Единственное реальное требование к экземплярам SQL Server заключается в том, что каждый экземпляр SQL Server должен иметь следующие ограничения.

  - Один экземпляр внутренней базы данных Lync Server 2013. (Как правило, не рекомендуется, чтобы база данных мониторинга размещалась в том же экземпляре SQL или даже на том же компьютере, что и внутренняя база данных. Хотя технически это возможно, существует риск того, что база данных мониторинга займет пространство диска, необходимое для внутренней базы данных.)

  - Один экземпляр базы данных регистрации вызовов.

  - Один экземпляр базы данных качества взаимодействия.

  - Один экземпляр базы данных архивации.

Другими словами, нельзя иметь два экземпляра базы данных LcsCdr в одном экземпляре SQL Server. Если требуется несколько экземпляров базы данных LcsCdr, придется настроить несколько экземпляров SQL Server.

<div>

## <a name="see-also"></a>См. также


[Развертывание мониторинга в Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

