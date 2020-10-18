---
title: 'Lync Server 2013: запросить сертификаты заранее (необязательно)'
description: 'Lync Server 2013: запросить сертификаты заранее (необязательно).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92ac9b68012487d07f25f08649689611117202
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579035"
---
# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Запрос сертификатов в предварительной (необязательный) для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Сертификаты необходимы для всех внутренних серверов, на которых работает Lync Server 2013, в том числе для каждого сервера переднего плана Enterprise Edition, сервера Standard Edition, директора, пограничного сервера и изолированного сервера-посредника. Хотя для внутренних серверов рекомендуется внутренний центр сертификации (ЦС) предприятия, можно также использовать общедоступный ЦС. Сведения о требованиях к сертификатам и использовании общедоступного ЦС приведены в статье [требования к сертификатам для внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) в документации по планированию.

Lync Server 2013 Setup включает мастер сертификатов, который упрощает задачу запроса, назначения и установки сертификатов во время развертывания. Если необходимо запросить сертификаты перед установкой серверов (например, для экономии времени при фактическом развертывании серверов), это можно сделать с помощью компьютера, на котором установлены средства администрирования Lync Server 2013, или с помощью процедуры запроса сертификата, определенной в Организации, при условии, что сертификаты являются экспортируемыми и содержат все обязательные альтернативные имена субъектов. Предварительный запрос сертификатов является необязательным. Если вы не запрашиваете их заранее, их необходимо запросить в процессе настройки каждого сервера, для которого требуется сертификат.

В этой документации по развертыванию приводятся инструкции по использованию мастера сертификатов для запроса сертификатов в процессе установки, как описано в разделе [Configure Certificate for Servers in Lync server 2013](lync-server-2013-configure-certificates-for-servers.md), [Настройка сертификатов для директора в Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)и [Установка файлов для сервера-посредника в разделе Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) этой документации по развертыванию. Если сертификаты запрашиваются заблаговременно, необходимо соответствующим образом изменить процедуры развертывания сертификатов в этих разделах, чтобы вместо запроса сертификатов во время развертывания выполнять из импорт и назначение.

<div>


> [!NOTE]  
> Lync Server 2013 включает поддержку сертификатов SHA/256 для подключений клиентов, работающих под управлением операционных систем Windows Vista, Windows Server &nbsp; 2008, Windows server &nbsp; 2008 &nbsp; R2 и Windows 7, и Lync Phone Edition. Для поддержки внешнего доступа с использованием SHA-256 внешний сертификат выдается общедоступным ЦС с использованием SHA-256.



</div>

</div>

<span> </span>

</div>

</div>

</div>

