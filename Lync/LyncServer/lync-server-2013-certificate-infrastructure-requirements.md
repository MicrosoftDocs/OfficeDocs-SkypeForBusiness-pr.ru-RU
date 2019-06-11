---
title: 'Lync Server 2013: требования инфраструктуры сертификатов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59089e9e44110809374ef0bf11fb2dc97705d0d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Требования инфраструктуры сертификатов для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-06-23_

Lync Server 2013 требует наличия инфраструктуры открытых ключей (PKI) для поддержки TLS и взаимного TLS-соединения (MTLS).

Lync Server использует сертификаты для следующих целей:

  - TLS соединения между клиентом и сервером

  - для подключений MTLS между серверами;

  - Федерация с использованием автоматического обнаружения DNS для партнеров

  - для доступа удаленных пользователей к обмену мгновенными сообщениями;

  - Доступ внешних пользователей к сеансам аудио-и видеосвязи, совместному использованию приложений и конференции

  - Мобильные запросы с автоматическим обнаружением веб-служб

Для Lync Server применяются следующие общие требования:

  - Все сертификаты серверов должны поддерживать авторизацию сервера (EKU сервера).

  - Все сертификаты серверов должны содержать точку распространения списка отзыва сертификатов (CDP).

  - Все сертификаты должны быть подписаны с помощью алгоритма подписывания, поддерживаемого операционной системой. Lync Server 2013 поддерживает наборы "SHA-1" и "SHA-2" уровней дайджеста (224, 256, 384 и 512), а также удовлетворяют требованиям или превышает требования к операционной системе. Сведения о поддержке операционной системы можно [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)найти в разделе.
    
    <div>
    

    > [!NOTE]  
    > Использование алгоритма подписи RSASSA-PSS не поддерживается и может привести к ошибкам при входе в систему, проблемам с переадресацией звонков и другим неполадкам. 

    
    </div>

  - Автоматическая подача заявки поддерживается для внутренних серверов, на которых работает Lync Server.

  - Автоматическая подача заявки не поддерживается для серверов пограничного сервера Lync Server.

  - Когда вы отправляете запрос на веб-сертификат в центр сертификации Windows Server 2003, вы должны отправить его с компьютера под управлением Windows Server 2003 с пакетом обновления 2 (SP2) или Windows XP.
    
    Обратите внимание, что несмотря на то, что KB922706 предоставляет поддержку для устранения проблем, связанных с регистрацией веб-сертификатов на веб-сайте службы сертификации Windows Server 2003, она не позволяет использовать Windows Server 2008, Windows Vista и Windows 7 для запроса сертификат, предоставленный центром сертификации Windows Server 2003.

  - Поддерживается длина ключей шифрования в 1024, 2048 и 4096 бит. Рекомендуется использовать ключи не короче 2048 бит.

  - По умолчанию используется дайджест-алгоритм (алгоритм хэширования и подписывания) RSA. Также поддерживаются\_алгоритмы\_ECDH P256, ECDH\_P384 и ECDH P521. 

<div>

## <a name="in-this-section"></a>Содержание

  - [Требования к сертификатам для внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Требования к сертификатам для доступа внешних пользователей в Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Требования к сертификатам для сервера сохраняемого чата в Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Требования к сертификатам для организации мобильной работы в Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

