﻿---
title: "Включение интеграции Exchange 2013 Outlook Web App и службы обмена мгн. сообщ."
TOCTitle: "Включение интеграции Exchange 2013 Outlook Web App и службы обмена мгн. сообщ."
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204857(v=OCS.15)
ms:contentKeyID: 49309617
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Включение интеграции Exchange 2013 Outlook Web App и службы обмена мгновенными сообщениями

 

_**Дата изменения раздела:** 2012-10-19_

Чтобы включить интеграцию Outlook Web Access (OWA) Exchange 2013 и системы обмена мгновенными сообщениями с Lync Server 2013, необходимо добавить сервер клиентского доступа Exchange 2013 в топологию Lync Server 2013 в качестве сервера доверенных приложений.

## Чтобы создать пул доверенных приложений

1.  Откройте командную консоль командная консоль Lync Server 2013.

2.  выполнить следующий командлет:
    
        Get-CsSite
    
    Это вернет siteID для siteName, имени сайта, в котором следует создать пул. Подробные сведения см. в разделе [Get-CsSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsSite) документации по командная консоль Lync Server 2013.

3.  выполнить следующий командлет:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Подробные сведения см. в описании командлета [New-CsTrustedApplicationPool](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrustedApplicationPool) в документации по командной консоли командная консоль Lync Server 2013.
    
    Полное доменное имя Exchange Server должно быть настроено в сертификате Exchange OWA как имя субъекта или альтернативное имя субъекта (SAN).
    
    Убедитесь, что в Exchange OWA полное доменное имя пула также является доверенным.
    
    > [!IMPORTANT]
    > Если сервер клиентского доступа <em>не</em> расположен на одном сервере с сервером единой системы обмена сообщениями Exchange 2013, пропустите оставшиеся действия этой процедуры и выполните процедуру «Создание доверенного приложения для сервера клиентского доступа Exchange 2013» далее в этом разделе. Если сервер клиентского доступа совмещен на одном сервере с единой системой обмена сообщениями Exchange 2013, выполните действия, приведенные в этой процедуре, и не выполняйте действия, приведенные в процедуре «Создание доверенного приложения для сервера клиентского доступа Exchange 2013», которая приведена далее в этом разделе.


4.  Запустите **Enable-CsTopology** .

5.  Откройте построитель топологий и загрузите текущую топологию.

6.  На левой панели разверните дерево, пока не достигните узла **Серверы доверенных приложений** .

7.  Разверните узел **Trusted application servers** (Доверенные серверы приложений).

8.  Теперь вы должны видеть сервер клиентского доступа Exchange 2013, указанный в списке как сервер доверенного приложения.

## Чтобы создать доверенное приложение для сервера клиентского доступа Exchange 2013

1.  Откройте командную консоль командная консоль Lync Server 2013.

2.  Если сервер клиентского доступа *не* располагается на одном сервере с единой системой обмена сообщениями Exchange 2013, выполните следующий командлет:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Подробные сведения см. в разделе [New-CsTrustedApplication](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrustedApplication) документации по командная консоль Lync Server 2013.

3.  Запустите **Enable-CsTopology** .

4.  В построителе решений на левой панели разверните дерево, пока не достигните узла **Серверы доверенных приложений** .

5.  Разверните узел **Trusted application servers** (Доверенные серверы приложений).

6.  Теперь вы должны видеть сервер клиентского доступа Exchange 2013, указанный в списке как сервер доверенного приложения.

