---
title: 'Lync Server 2013: поддержка инфраструктуры сертификатов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc8cb5bdad02de4fcb407d7eb27960258a46dd3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Поддержка инфраструктуры сертификатов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-11-07_

Lync Server 2013 требует наличия инфраструктуры открытых ключей (PKI) для поддержки протоколов TLS и взаимного TLS-соединения (MTLS). По умолчанию Lync Server 2013 настроен на использование протокола TLS для подключений между клиентом и сервером. MTLS используется для подключений между серверами.

Сертификаты MTLS должны выдаваться доверенными центрами сертификации (ЦС) для Lync Server 2013. Lync Server поддерживает сертификаты, выданные следующими центрами сертификации:

  - Сертификаты, выданные внутренним центром сертификации:
    
      - Центр сертификации операционной системы Windows Server 2003
    
      - Центр сертификации операционной системы Windows Server 2008
    
      - Центр сертификации операционной системы Windows Server 2008 R2
    
      - Центр сертификации операционной системы Windows Server 2012
    
      - Центр сертификации операционной системы Windows Server 2012 R2

  - Сертификаты, выданные общедоступным центром сертификации

Для связи с другими приложениями и серверами, такими как Exchange 2013, требуется сертификат, который поддерживается другими приложениями и продуктами. В выпуске 2013, Lync Server 2013 и других серверных продуктах Microsoft, включая Exchange 2013 и SharePoint Server, поддерживается протокол OAuth для проверки подлинности и авторизации сервера и сервера. Дополнительные сведения можно найти [в разделе Управление проверкой подлинности серверов (OAuth) и партнерским приложением в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) в документации по развертыванию или документации по эксплуатации.

Для подключений клиентов с операционной системой Windows 7, операционной системой Windows Server 2008 R2 и Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 включает поддержку (но не обязательно) сертификатов, подписанных с помощью SHA-256 криптографическая хэш-функция. Для поддержки внешнего доступа с помощью SHA-256 внешний сертификат выдается общедоступным центром сертификации с помощью SHA-256.

Сведения о требованиях к сертификатам можно найти в разделе [требования к инфраструктуре сертификатов для Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) в документации по планированию. Подробнее об использовании подстановочных знаков в сертификатах можно узнать [в разделе Поддержка сертификатов с помощью подстановочных знаков в Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) в документации по поддержке.

</div>

<span> </span>

</div>

</div>

</div>

