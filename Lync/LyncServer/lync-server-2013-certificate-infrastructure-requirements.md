---
title: Требования к инфраструктуре сертификатов Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18666f33becabcbdf61370a32900ae7a4819e0cb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508026"
---
# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Требования к инфраструктуре сертификатов для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-06-23_

Lync Server 2013 требует наличия инфраструктуры открытых ключей (PKI) для поддержки подключений TLS и взаимного TLS (MTLS).

Lync Server использует сертификаты для следующих целей:

  - для подключений TLS между клиентом и сервером;

  - для подключений MTLS между серверами;

  - для федерации с использованием автоматического обнаружения DNS партнеров;

  - для доступа удаленных пользователей к обмену мгновенными сообщениями;

  - для доступа внешних пользователей к сеансам аудио- и видеосвязи, к приложениям с общим доступом и к конференц-связи;

  - для мобильных запросов с использованием автоматического обнаружения веб-служб.

Для Lync Server применяются следующие общие требования:

  - Все сертификаты серверов должны поддерживать авторизацию сервера (EKU сервера).

  - Все сертификаты серверов должны содержать точку распространения списка отзыва сертификатов (CDP).

  - Все сертификаты должны быть подписаны с помощью алгоритма подписи, поддерживаемого операционной системой. Lync Server 2013 поддерживает набор размеров дайджеста SHA-1 и SHA-2 (224, 256, 384 и 512), а также отвечает или превышает требования к операционной системе. Сведения о поддержке операционной системы приведены в разделе [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002) .
    
    <div>
    

    > [!NOTE]  
    > Использование алгоритма подписи RSASSA-PSS не поддерживается и может привести к ошибкам при входе в систему и переадресации вызовов, среди прочих проблем.

    
    </div>

  - Автоматическая регистрация поддерживается для внутренних серверов, на которых работает Lync Server.

  - Автоматическая регистрация не поддерживается для пограничных серверов Lync Server.

  - Запрос на сертификат через Интернет в центр сертификации Windows Server 2003 необходимо подавать с компьютера, работающего под управлением либо Windows Server 2003 с пакетом обновления 2 (SP2), либо Windows XP.
    
    Следует отметить, что хотя в статье базы знаний KB922706 предоставляется поддержка для разрешения проблем с регистрацией сертификатов через Интернет с помощью служб сертификатов Windows Server 2003, она не делает возможным запрос сертификата в ЦС Windows Server 2003 с использованием Windows Server 2008, Windows Vista или Windows 7.

  - Поддерживаются длины ключей шифрования 1024, 2048 и 4096. Рекомендуется использовать ключи длиной 2048 и выше.

  - Для дайджеста по умолчанию или хэш-подписи используется алгоритм RSA. \_ \_ Также поддерживаются алгоритмы ECDH P256, ECDH P384 и ECDH \_ P521. 

<div>

## <a name="in-this-section"></a>Содержание

  - [Требования к сертификатам для внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Требования к сертификатам для доступа внешних пользователей в Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Требования к сертификатам для сервера сохраняемого чата в Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Требования к сертификатам для мобильных устройств в Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

