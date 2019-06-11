---
title: 'Lync Server 2013: доступ к данным наблюдения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45f6033c927a0d0c27b139d889c5fb0b0d9d4825
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a>Доступ к данным мониторинга в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-05_

Данные мониторинга хранятся в двух базах данных SQL Server: LcsCdr для данных регистрации звонков и QoEMetrics для данных качества взаимодействия. Эти базы данных ничем особенным не выделяются, т. е. доступ к данным в них можно получить с помощью любого средства, которое вы обычно используете для просмотра и анализа данных SQL Server.

Для получения доступа к данным наблюдения и анализа данных мониторинга необходимо предусмотреть один из инструментов, которые являются отчетами мониторинга Lync Server. Отчеты мониторинга — это набор стандартных отчетов, публикуемых службой Microsoft SQL Server Reporting Service. Эти отчеты, доступные в браузере, предоставляют сведения об использовании, диагностики звонков и качестве медиаданных на основе записей регистрации вызовов (CDR) и качества взаимодействия (QoE) в базе данных CDR и QoE. Отчеты мониторинга поставляются с Lync Server 2013 и могут быть установлены с помощью мастера развертывания Lync Server после установки Lync Server и настройки мониторинга.

Как было отмечено, для отчетов мониторинга требуется служба SQL Server Reporting Service, которую можно установить вместе с SQL Server в любое время после установки SQL Server.

Дополнительные сведения можно найти в разделе [Установка сервера Lync server 2013 мониторинг отчетов](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) в руководстве по развертыванию lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

