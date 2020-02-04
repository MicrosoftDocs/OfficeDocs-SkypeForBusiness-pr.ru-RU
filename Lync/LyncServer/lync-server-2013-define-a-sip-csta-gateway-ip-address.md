---
title: 'Lync Server 2013: определение IP-адреса для шлюза SIP/CSTA'
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
ms.openlocfilehash: c50958f2c7c44045e25ff4ac9619f3ad73a5f302
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Определение IP-адреса для шлюза SIP/CSTA в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Если Lync Server подключается к шлюзу SIP/КСТА, который вы развернули для удаленного управления звонками с помощью протокола TCP, необходимо задать IP-адрес шлюза в построителе топологии. Это действие не требуется для шлюзов, поддерживающих соединения TLS. Для всех шлюзов, поддерживающих TLS подключения, вы можете пропустить эту процедуру и продолжить развертывание удаленного управления звонком, выполнив действия, описанные в статье [Включение пользователей Lync для удаленного управления звонками в Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>Определение IP-адреса шлюза SIP/КСТА с помощью построителя топологии

1.  Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.

2.  Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.

3.  Выберите параметр для скачивания существующей топологии.

4.  Разверните узел **серверы доверенных приложений** .

5.  Щелкните правой кнопкой мыши созданную группу доверенных приложений, как описано в разделе [Настройка надежной записи приложения для удаленного управления звонком в Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), а затем выберите команду **изменить свойства**.

6.  Снимите флажок **Разрешить репликацию данных конфигурации в этот пул** .

7.  Нажмите кнопку **ограничить использование службы до выбранных IP-адресов**. Параметр по умолчанию **использует все настроенные IP-адреса**.

8.  В текстовом поле **основной IP-адрес** введите IP-адрес шлюза SIP/кста.

9.  Чтобы обновить топологию в хранилище Центрального управления, в дереве консоли щелкните **Lync Server**, а затем в области **действий** нажмите кнопку **опубликовать**.

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка статического маршрута для дистанционного управления вызовами в Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

