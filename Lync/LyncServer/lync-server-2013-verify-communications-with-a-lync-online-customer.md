---
title: 'Lync Server 2013: Проверка связи с клиентом Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0269c66ad88f7be7f34874a8e4370fb65b954ccf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518666"
---
# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>Проверка связи с клиентом Lync Online в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-08_

Чтобы разрешить пользователям Lync в Организации общаться с пользователями Microsoft Lync Online 2010, необходимо выполнить следующие действия:

  - Соблюсти все обязательные условия. К ним относятся развертывание внутренних и пограничных серверов, включение поддержки федерации для организации и настройка пользовательских учетных записей. Сведения о том, [как включить федерацию с клиентом Lync Online в Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md), можно найти в статье необходимые условия.

  - Настроить поддержку доступа к домену во внутреннем развертывании. Сюда входит создание записи поставщика узла и Настройка развертывания для предоставления доступа из домена клиента Lync Online. Дополнительную информацию можно узнать [в статье Настройка поддержки федерации для домена Lync Online в Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).

  - Настроить пользовательские учетные записи для поддержки федерации. Дополнительную информацию можно узнать в статье [Настройка доступа пользователей для Федерации с клиентом Lync Online в Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).

После выполнения всех этих действий администратор Lync Online 2010 завершает всю конфигурацию своих веб-служб для поддержки Федерации с вашей организацией, а также для проверки связи путем тестирования связи между внутренним пользователем в Организации и пользователем клиента Lync Online. В случае неудачного подключения используйте средство ведения журнала с пограничного сервера для записи файлов журнала и трассировки, чтобы устранить эту проблему. Сведения об использовании средства ведения журнала приведены в статье [Open the администрирование Lync Server 2013 Tools](lync-server-2013-open-lync-server-administrative-tools.md) в документации по операциям. Для получения дополнительных сведений о средстве ведения журнала обратитесь к документации по средству ведения журнала Lync Server 2010 в библиотеке TechNet по адресу [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) .

</div>

<span> </span>

</div>

</div>

</div>

