---
title: 'Lync Server 2013: Настройка пассивной проверки подлинности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 780b539aeaf6a6bc6956fc5f8b6185092675632b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532496"
---
# <a name="configuring-lync-server-2013-passive-authentication"></a>Настройка пассивной проверки подлинности Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-07-11_

В следующем разделе описано, как настроить Lync Server 2013 с накопительными пакетами обновления: 2013 июля для поддержки пассивной проверки подлинности. После включения Пользователи Lync, для которых включена двухфакторная проверка подлинности, должны использовать физическую или виртуальную смарт-карту и действительный ПИН-код для входа в систему с помощью Lync 2013 с накопительными обновлениями для Lync с накопительными обновлениями: Июль 2013 клиент.

<div class="">


> [!NOTE]  
> Пользователям настоятельно рекомендуется включить пассивную проверку подлинности для регистратора и веб-служб на уровне службы. Если пассивная проверка подлинности включена для регистратора и веб-служб на глобальном уровне, это может привести к сбоям проверки подлинности на уровне Организации для пользователей, которые не входят в состав Lync 2013 с накопительными пакетами обновления 2013: обновление клиента клиентского рабочего стола.



</div>

<div>

## <a name="web-service-configuration"></a>Конфигурация веб-службы

Ниже описано, как создать настраиваемую конфигурацию веб-службы для директоров, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.

**Создание настраиваемой конфигурации веб-службы**

1.  Выполните вход на сервер Lync Server 2013 с накопительными пакетами обновления для сервера переднего плана 2013 с использованием учетной записи администратора Lync.

2.  Запустите командную консоль Lync Server 2013.

3.  В командной строке командной консоли Lync Server создайте новую конфигурацию веб-службы для каждого директора, корпоративного пула и сервера Standard Edition, для которых будет включена пассивная проверка подлинности, выполнив следующую команду:
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > Значение полного доменного имени WsFedPassiveMetadataUri — это имя службы федерации сервера AD FS 2,0. Значение имени службы федерации можно найти в консоли управления AD FS 2,0, щелкнув правой кнопкой мыши элемент <STRONG>Служба</STRONG> в области навигации, а затем выбрав <STRONG>изменить свойства службы федерации</STRONG>.

    
    </div>

4.  Убедитесь, что значения Усевсфедпассивеаус и WsFedPassiveMetadataUri были заданы правильно, выполнив следующую команду:
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  Для клиентов пассивная проверка подлинности является наименее предпочтительным методом проверки подлинности для проверки подлинности. Для всех директоров, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности, все остальные типы проверки подлинности необходимо отключить в веб-службах Lync, выполнив следующую команду:
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  Убедитесь, что все остальные типы проверки подлинности успешно отключены, выполнив следующую команду:
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>Настройка прокси-сервера

Если проверка подлинности сертификатов отключена для веб-служб Lync, клиент Lync будет использовать менее предпочтительный тип проверки подлинности, например Kerberos или NTLM, для проверки подлинности в службе регистратора. Проверка подлинности с помощью сертификата по-прежнему необходима для того, чтобы позволить клиенту Lync получить билет, однако для службы регистратора необходимо отключить Kerberos и NTLM.

Ниже описано, как создать конфигурацию настраиваемого прокси-сервера для пограничных пулов, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.

**Создание настраиваемой конфигурации прокси-сервера**

1.  В командной строке командной консоли Lync Server создайте новую конфигурацию прокси-сервера для каждого сервера Lync Server 2013 с накопительными пакетами обновления 2013: пограничный пул, корпоративный пул и сервер Standard Edition, для которых будет включена пассивная проверка подлинности, выполнив следующие команды:
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  Убедитесь, что все остальные типы проверки подлинности прокси-сервера успешно отключены, выполнив следующую команду:
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

