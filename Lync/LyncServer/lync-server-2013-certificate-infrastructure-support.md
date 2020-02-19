---
title: Lync Server 2013 — поддержка инфраструктуры сертификатов
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
ms.openlocfilehash: 56582d57400bb59e55978caf67a6b957fc91f47d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Поддержка инфраструктуры сертификатов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-11-07_

Для Lync Server 2013 требуется инфраструктура открытых ключей (PKI), поддерживающая подключения TLS и взаимное TLS (MTLS). По умолчанию Lync Server 2013 настроен для использования протокола TLS для подключений между серверами. MTLS используется в подключениях между серверами.

Сертификаты MTLS должны выдаваться доверенными центрами сертификации (CAs) для Lync Server 2013. Lync Server поддерживает сертификаты, выданные из следующих ЦС:

  - Сертификаты, выданные внутренним ЦС:
    
      - ЦС операционной системы Windows Server 2003
    
      - ЦС операционной системы Windows Server 2008
    
      - ЦС операционной системы Windows Server 2008 R2
    
      - ЦС операционной системы Windows Server 2012
    
      - ЦС операционной системы Windows Server 2012 R2

  - Сертификаты, выданные общедоступным ЦС.

Для связи с другими приложениями и серверами, например Exchange 2013, необходим сертификат, который поддерживается другими приложениями и продуктами. Для выпусков 2013, Lync Server 2013 и других серверных продуктов Майкрософт, в том числе Exchange 2013 и SharePoint Server, поддерживается протокол OAuth для проверки подлинности и авторизации "сервер-сервер". Дополнительные сведения: [Управление проверкой подлинности между серверами (OAuth) и партнерских приложений в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) в документации по развертыванию или документации по операциям.

Для подключений клиентов, работающих под управлением операционной системы Windows 7, Windows Server 2008 R2 и Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 включает поддержку (но не обязательно) сертификатов, подписанных с помощью SHA-256 криптографическая хэш-функция. Для поддержки внешнего доступа с использованием SHA-256 внешний сертификат выдается общедоступным ЦС с использованием SHA-256.

Сведения о требованиях к сертификатам приведены в статье [требования к инфраструктуре сертификатов для Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) в документации по планированию. Для получения подробных сведений об использовании подстановочных знаков с сертификатами, обратитесь к разделу [Поддержка сертификатов с помощью подстановочных знаков в Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) в документации по поддержке.

</div>

<span> </span>

</div>

</div>

</div>

