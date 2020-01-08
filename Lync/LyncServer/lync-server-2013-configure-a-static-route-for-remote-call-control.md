---
title: 'Lync Server 2013: настройка статического маршрута для дистанционного управления вызовами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a11b24fc8d4be54f5645853c050891d3821945e4
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Настройка статического маршрута для дистанционного управления вызовами в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-22_

Удаленное управление звонками требует, чтобы каждый пул серверов Lync Server настроился с помощью пути из этого пула на шлюз SIP/КСТА, который подключается к частной сети обмена филиалами (УАТС). Этот путь требует, чтобы каждый пул выделил один статический маршрут для каждого шлюза, на который будет прокси-сервер, управляющие сообщениями, связанные с вызовами УАТС. Если вы настроили глобальный статический маршрут для удаленного управления звонком, то каждый пул, для которого не настроен статический маршрут на уровне пула, будет использовать глобальный статический маршрут.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>Настройка статического маршрута для удаленного управления звонками

1.  Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или роль управления доступом на основе ролей (RBAC), для которой вы назначили командлет **New-ксстатикрауте** .

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Чтобы создать статический маршрут и вставить его в переменную $TLSRoute или $TCPRoute, выполните одно из указанных ниже действий.
    
    <div class="">
    

    > [!TIP]  
    > Чтобы сопоставить дочерние домены домена, можно задать подстановочное значение в параметре Матчури. Например, <STRONG>*. contoso.NET</STRONG>. Это значение соответствует любому домену, который заканчивается на суффикс <STRONG>contoso.NET</STRONG>.

    
    </div>
    
      - Для подключения к протоколу TLS введите в командной строке следующую команду:
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        Например:
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        Если для Уседефаултцертификате задано значение false, необходимо указать параметры Тлсцертиссуер и Тлсцертсериалнумбер. Эти параметры указывают имя центра сертификации (ЦС), который выдал сертификат, используемый в статическом маршруте, и порядковый номер этого TLS-сертификата соответственно. Подробнее об этих параметрах можно узнать в справке Lync Server Management Shell, введя следующую команду в командной строке:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - Для подключения по протоколу TCP введите в командной строке следующую команду:
        
        <div class="">
        

        > [!NOTE]  
        > Если вы указали полное доменное имя (FQDN), необходимо сначала настроить DNS A Record (доменное имя).

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        Например:
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        Ниже указаны значения по умолчанию для статических маршрутов с необязательными параметрами.
        
          - Enabled = True
        
          - Матчонлифонеури = false
        
          - Реплацехостинрекуестури = false
        
        Мы настоятельно рекомендуем не менять эти значения по умолчанию. Однако если вы должны изменить любой из этих параметров, ознакомьтесь со справкой оболочки среды управления Lync Server, введя в командной строке следующую команду:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  Чтобы сохранить созданный статический маршрут в хранилище Центрального управления, выполните одно из следующих действий:
    
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
[Определение IP-адреса для шлюза SIP/CSTA в Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

