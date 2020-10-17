---
title: 'Lync Server 2013: определение IP-адреса шлюза SIP/CSTA'
description: 'Lync Server 2013: определение IP-адреса шлюза SIP/CSTA.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23286b2748df3af06f905a791bf0ee80c6f0a919
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560435"
---
# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Определение IP-адреса шлюза SIP/CSTA в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Если Lync Server будет подключаться к шлюзу SIP/CSTA, развернутому для удаленного управления звонками с помощью подключения по протоколу TCP, необходимо определить IP-адрес шлюза в построителе топологий. Этот шаг не требуется для шлюзов, поддерживающих подключения TLS. Для любого шлюза, поддерживающего TLS подключения, можно пропустить эту процедуру и продолжить развертывание удаленного управления звонками, выполнив действия, описанные в статье [Включение удаленного управления звонками для пользователей Lync в Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>Задание IP-адреса шлюза SIP/CSTA с помощью построителя топологий

1.  Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.

2.  Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.

3.  Выберите загрузку существующей топологии.

4.  Разверните узел **Trusted application servers** (Доверенные серверы приложений).

5.  Щелкните правой кнопкой мыши созданный пул доверенных приложений, как описано в разделе [Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), а затем щелкните **изменить свойства**.

6.  Снимите флажок **Enable replication of configuration data to this pool** (Включить репликацию данных конфигурации для этого пула).

7.  Щелкните **Limit service usage to selected IP addresses** (Разрешить использовать службу только указанным IP-адресам). По умолчанию используется параметр **Use all configured IP addresses** (Использовать все настроенные IP-адреса).

8.  В текстовом поле **Primary IP address** (Основной IP-адрес) введите IP-адрес шлюза SIP/CSTA.

9.  Чтобы обновить топологию в центральном хранилище управления, в дереве консоли выберите узел **Lync Server** и затем на панели **Действия** щелкните **Опубликовать**.

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка статического маршрута для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

