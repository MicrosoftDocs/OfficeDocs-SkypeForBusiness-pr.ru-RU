---
title: Настройка записи доверенного приложения для удаленного управления звонками
description: Настройка записи доверенного приложения для удаленного управления звонками.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa5341dc220853670cf000f5b0d5dc379c02fa51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570075"
---
# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a>Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2015-11-02_

Шлюз SIP/CSTA должен быть настроен как доверенное приложение, чтобы Lync Server мог применить статический маршрут для маршрутизации вызовов шлюза.

<div>


> [!IMPORTANT]
> Если вы переносите пользователей из предыдущей версии развертывания Lync Server, убедитесь, что удалены все существующие записи доверенных приложений (ранее известные как авторизованные записи узла), созданные для шлюза SIP/CSTA, прежде чем выполнять процедуры, описанные в этом разделе. Дополнительные сведения см. <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">в статье удаление устаревшего авторизованного узла в Lync Server 2013 (необязательно)</A>.<BR>Если вы планируете развернуть новое удаленное управление звонками с помощью TCP-подключения, необходимо убедиться в том, что ограничения на <STRONG>Использование службы для выбранных IP-адресов</STRONG> должны быть установлены для существующих доверенных приложений и пулов, если вы хотите использовать один и тот же порт TCP для нового доверенного приложения.



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a>Настройка записи доверенного приложения для шлюза SIP/CSTA

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или роли управления доступом на основе ролей (RBAC), которой назначен командлет **New-кструстедаппликатионпул** .

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Чтобы создать запись доверенного приложения, выполните одно из следующих действий:
    
      - Для подключения по протоколу защиты транспортного уровня (TLS) введите в командной строке следующую команду:
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Пример:
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - Для подключения по протоколу управления передачей (TCP) введите в командной строке следующую команду:
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Пример:
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  Чтобы добавить доверенное приложение в пул, выполните одно из следующих действий:
    
      - Для подключения по протоколу TLS введите в командной строке следующую команду:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        Пример:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - Для подключения по протоколу TCP введите в командной строке следующую команду:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        Пример:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  Для реализации опубликованных изменений, внесенных в топологию, введите в командной строке следующую команду:
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка статического маршрута для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Определение IP-адреса шлюза SIP/CSTA в Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

