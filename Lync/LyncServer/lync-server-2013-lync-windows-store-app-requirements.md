---
title: 'Lync Server 2013: требования к приложению Магазина Windows для Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06d32aa0cf2248c80b8f98d80e8c796818b89a6b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Требования к приложению для Магазина Windows Lync для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-12-03_

Организации, использующие локальное развертывание Lync Server, должны удовлетворять следующим требованиям для поддержки приложения Lync Windows в магазине.

<div>


> [!NOTE]  
> Для Lync Server 2010 запустите накопительный пакет обновления для Lync Server 2010: Февраль 2012 (доступен по адресу <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2670352</A>) или более поздней версии на всех серверах. Чтобы разрешить пользователям присоединяться к собраниям, запустите накопительное обновление для Lync Server 2010: Октябрь 2012 (доступно по адресу <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>) на серверах.



</div>

  - Включите службу автообнаружения, Lync Web App и службы веб-билетов на сервере.

  - Включите проверку подлинности на сертификате на сервере переднего плана или интерфейсном пуле. (Процесс регистрации пользователя на сервере переднего плана или интерфейсном пуле часто называется регистратором). Дополнительные сведения: [CREATE регистратор параметры конфигурации в Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

  - Опубликуйте записи ресурса псевдонима DNS (CNAME) для службы автообнаружения.

  - Больше не требуется гарантировать, что точка распространения списка отзыва сертификатов (CDP) для сертификатов, выданных серверу Lync Server, указывает на ресурс HTTP, а не на ресурс LDAP. Тем не менее, убедитесь, что на клиентских компьютерах установлены последние обновления Windows.

  - Настройте прокси-серверы HTTP на предприятии, чтобы разрешить HTTP-трафик, связанный с Lync Server.При необходимости добавьте исключения для служб автообнаружения, Lync Web App и веб-билетов.

  - На клиентских компьютерах установите Windows 8,1 и последнюю версию Lync Windows App Store, чтобы устранить проблему при входе, которая обычно возникает при использовании нескольких доменов (например, когда URI SIP является **userA@domainZ.com** , а пограничный сервер — **SIP.domainX.com**).

Если ваша организация подписывается на Lync Online или Office 365 и вы используете свое собственное доменное имя, необходимо выполнить некоторые дополнительные действия по настройке сети для автоматического обнаружения серверов Lync. Требования к конфигурации сети одинаковы для приложений Lync Windows и Lync на мобильных устройствах. Следуйте инструкциям "Настройка сети" в вики-статье Office 365 "Настройка мобильных устройств Lync" [https://go.microsoft.com/fwlink/?LinkId=271822](https://go.microsoft.com/fwlink/?linkid=271822).

<div>

## <a name="see-also"></a>См. также


[Развертывание приложения Lync Windows для магазина в Lync Server 2013](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

