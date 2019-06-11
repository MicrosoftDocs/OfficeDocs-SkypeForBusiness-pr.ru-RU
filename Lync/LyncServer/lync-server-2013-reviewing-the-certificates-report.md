---
title: 'Lync Server 2013: проверка отчета о сертификатах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Просмотр отчета о сертификатах в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Отчет о сертификатах включает все сертификаты, необходимые для рекомендуемого развертывания Lync Server 2013. Инструмент "планирование" используется для ввода имен субъектов и альтернативных имен субъектов. Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates. Certificate information also contains information about where the certificate can typically be issued from. If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider. Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.

![Отчет администратора о сертификатах] (images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Отчет администратора о сертификатах")

Тщательно рассмотрите и осознайте использование и назначение каждого сертификата в развертывании. Если возникает вопрос о том, для чего именно нужен определенный сертификат, определите взаимодействие серверов и служб. Сертификаты в Lync Server 2013 используются в двух основных целях:

  - Протокол MTLS — каждый из взаимодействующих компьютеров предоставляет сертификат, подтверждающий его удостоверение другому компьютеру. Это называется проверкой подлинности сервера. Взаимодействие не начинается до тех пор, пока каждый из компьютеров не будет доверять удостоверению другого компьютера.

  - Шифрование — шифрование (по протоколам SSL и TLS) имеет критически важное значение для обеспечения безопасности связи, конфиденциальности, а также создания системы доверенного взаимодействия и совместной работы.

<div>

## <a name="see-also"></a>См. также


[Просмотр отчетов администратора в Lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

