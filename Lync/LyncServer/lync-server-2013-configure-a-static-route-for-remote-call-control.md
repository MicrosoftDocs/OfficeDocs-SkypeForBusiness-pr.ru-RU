---
title: 'Lync Server 2013: Настройка статического маршрута для удаленного управления звонками'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535574a47a9ea77b5db20e45dcdcbb62fab2e4b9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Настройка статического маршрута для удаленного управления звонками в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-22_

Для удаленного управления вызовами необходимо, чтобы каждый пул Lync Server был настроен с использованием пути из этого пула к шлюзу SIP/CSTA, который подключается к УАТС. Этот путь требует, чтобы каждому пулу был назначен один статический маршрут на каждый шлюз, на который пул будет передавать сообщения управления вызовами SIP, связанные с вызовами в УАТС. Если настроить глобальный статический маршрут для удаленного управления вызовами, каждый пул, для которого не задан статический маршрут на уровне пула, будет использовать этот глобальный маршрут.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>Настройка статического маршрута для удаленного управления вызовами

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или роли управления доступом на основе ролей (RBAC), которой назначен командлет **New-CsStaticRoute** .

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Чтобы настроить статический маршрут и поместить его в переменную $TLSRoute или $TCPRoute, выполните одно из следующих действий.
    
    <div class="">
    

    > [!TIP]  
    > Для сопоставления дочерних доменов домена можно указать подстановочное значение параметра MatchUri. Например, <STRONG>*.contoso.net</STRONG>. Это значение соответствует любому домену, который заканчивается суффиксом <STRONG>contoso.net</STRONG>.

    
    </div>
    
      - Для подключения по протоколу TLS введите в командной строке следующую команду:
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        Пример:
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        Если для Уседефаултцертификате задано значение false, необходимо указать параметры TLSCertIssuer и TLSCertSerialNumber. Эти параметры указывают имя центра сертификации (ЦС), который выдал сертификат, используемый в статическом маршруте, и серийный номер этого сертификата TLS соответственно. Для получения дополнительных сведений об этих параметрах ознакомьтесь со статьей Справка по консоли управления Lync Server, введя следующую команду в командной строке:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - Для подключения по протоколу TCP введите в командной строке следующую команду:
        
        <div class="">
        

        > [!NOTE]  
        > Если указывается полное доменное имя, сначала необходимо настроить запись DNS.

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        Например:
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        Ниже приведены значения по умолчанию для необязательных параметров статических маршрутов.
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        Настоятельно рекомендуем не изменять эти значения по умолчанию. Тем не менее, если необходимо изменить любой из этих параметров, ознакомьтесь со статьей Справка по консоли управления Lync Server, введя следующую команду в командной строке:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  Чтобы сохранить только что созданный статический маршрут в центральном хранилище управления, выполните одно из следующих действий (при необходимости).
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Определение IP-адреса шлюза SIP/CSTA в Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

