---
title: 'Lync Server 2013: доступ к данным мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3acb91831a57ba68648ee513af337abe6a894849
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a><span data-ttu-id="319e2-102">Доступ к данным мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="319e2-102">Accessing monitoring data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="319e2-103">_**Последнее изменение темы:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="319e2-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="319e2-p101">Данные мониторинга хранятся в двух базах данных SQL Server: LcsCdr для данных регистрации звонков и QoEMetrics для данных качества взаимодействия. Эти базы данных ничем особенным не выделяются, т. е. доступ к данным в них можно получить с помощью любого средства, которое вы обычно используете для просмотра и анализа данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="319e2-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>

<span data-ttu-id="319e2-106">Для получения доступа к данным мониторинга и их анализа необходимо учитывать одно средство: отчеты мониторинга сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="319e2-106">One tool you should consider for accessing and analyzing monitoring data is the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="319e2-107">Отчеты мониторинга — это набор стандартных отчетов, публикуемых службой Microsoft SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="319e2-107">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="319e2-108">Эти отчеты, доступные в браузере, предоставляют сведения об использовании, диагностики звонков и качестве медиаданных на основе записей регистрации вызовов (CDR) и качества взаимодействия (QoE) в база данных CDR и QoE.</span><span class="sxs-lookup"><span data-stu-id="319e2-108">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="319e2-109">Отчеты мониторинга поставляются с Lync Server 2013 и могут быть установлены с помощью мастера развертывания Lync Server после установки Lync Server и настройки мониторинга.</span><span class="sxs-lookup"><span data-stu-id="319e2-109">Monitoring Reports ship with Lync Server 2013 and can be installed from the Lync Server Deployment Wizard after Lync Server has been installed and monitoring has been configured.</span></span>

<span data-ttu-id="319e2-p103">Как было отмечено, для отчетов мониторинга требуется служба SQL Server Reporting Service, которую можно установить вместе с SQL Server в любое время после установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="319e2-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>

<span data-ttu-id="319e2-112">Для получения дополнительных сведений ознакомьтесь с разделом [install the Lync server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) в руководстве по развертыванию lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="319e2-112">For more information, see the topic [Installing Lync Server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) in the Lync Server 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

