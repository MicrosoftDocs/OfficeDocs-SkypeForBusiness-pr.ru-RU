---
title: 'Lync Server 2013: Настройка пассивной проверки подлинности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c85bd20222a5fa70d052b21f62d0c19c76eea46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>Настройка пассивной проверки подлинности Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-07-11_

В следующем разделе описано, как настроить Lync Server 2013 с накопительными обновлениями: Июль 2013 для поддержки пассивной проверки подлинности. После включения Пользователи Lync, на которых включена двухфакторная проверка подлинности, должны использовать физическую или виртуальную смарт-карту и допустимый ПИН-код, чтобы войти в систему с помощью Lync 2013 с накопительными обновлениями: Июль 2013 (клиент).

<div class="">


> [!NOTE]  
> Заказчикам настоятельно рекомендуется включить пассивную проверку подлинности для регистратора и веб-служб на уровне служб. Если для регистраторов и веб-служб на глобальном уровне включена пассивная проверка подлинности, это может привести к сбоям проверки подлинности в масштабах Организации для пользователей, которые не входят в состав Lync 2013 с накопительными обновлениями: Июль 2013 клиентские компьютеры.



</div>

<div>

## <a name="web-service-configuration"></a>Конфигурация веб-служб

Ниже описана процедура создания настраиваемой конфигурации веб-служб для директоров, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.

**Порядок создания настраиваемой конфигурации веб-служб**

1.  Войдите на сервер Lync Server 2013 с накопительными обновлениями: сервер Июль 2013 на сервере переднего плана с помощью учетной записи администратора Lync.

2.  Запустите командную консоль Lync Server 2013.

3.  В командной строке оболочки Lync Server Management Shell создайте новую конфигурацию веб-службы для каждого директора, корпоративного пула и сервера Standard Edition, для которых будет включена пассивная проверка подлинности, выполнив следующую команду:
    
        New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    
    <div class="">
    

    > [!WARNING]  
    > Значением полного доменного имени WsFedPassiveMetadataUri является имя службы федерации сервера AD FS 2.0. Значение имени службы федерации можно найти в консоли управления AD FS 2.0, щелкнув <STRONG>Служба</STRONG> в области навигации правой кнопкой мыши и затем выбрав <STRONG>Изменить свойства службы федерации</STRONG>.

    
    </div>

4.  Проверьте правильность значений UseWsFedPassiveAuth и WsFedPassiveMetadataUri, выполнив следующую команду:
    
        Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri

5.  Для клиентов пассивная проверка подлинности является наименее предпочтительным способом проверки подлинности WebTicket. Для всех режиссеров, корпоративных пулов и серверов Standard Edition, для которых будет разрешена пассивная проверка подлинности, в веб-службах Lync должны быть отключены все другие типы проверки подлинности, выполнив следующую команду:
    
        Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE

6.  Убедитесь, что все другие типы проверки подлинности успешно отключены, выполнив следующую команду:
    
        Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth

</div>

<div>

## <a name="proxy-configuration"></a>Конфигурация прокси-сервера

Если для веб-служб Lync отключена проверка подлинности сертификата, клиент Lync будет использовать менее предпочтительный тип проверки подлинности, например Kerberos или NTLM, для проверки подлинности в службе регистратора. Проверка подлинности сертификата по-прежнему необходима для того, чтобы клиент Lync мог получить веб-билет, но для службы регистратора необходимо отключить Kerberos и NTLM.

Ниже описана процедура создания настраиваемой конфигурации прокси-сервера для пограничных пулов, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.

**Порядок создания настраиваемой конфигурации прокси-сервера**

1.  В командной строке оболочки Lync Server Management Shell создайте новую конфигурацию прокси-сервера для каждого сервера Lync Server 2013 с накопительными обновлениями для каждого из выпусков: Июль 2013 EDGE, корпоративный пул и сервер Standard Edition, для которых будет включена пассивная проверка подлинности. следующие команды:
    
       ```
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  Убедитесь, что все остальные типы проверки подлинности прокси-сервера успешно отключены, выполнив следующую команду:
    
        Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth

</div>

</div>

<span> </span>

</div>

</div>

</div>

