---
title: Настройка различных политик
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0abb428dab96c09c7cd8b82d99de12ba76068eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505246"
---
# <a name="configuring-the-various-policies"></a>Настройка различных политик

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-24_

<div>

Ниже приведены различные политики, которые можно настроить в топологии Lync Server 2013 до запуска средства нагрузки и производительности Lync Server 2013.

<div>

## <a name="configuring-the-archiving-policy"></a>Настройка политики архивации

Просмотрите пример скрипта ArchivingPolicy.ps1. Этот сценарий необходимо использовать, только если в вашей топологии развернут сервер архивации. Дополнительные сведения см. в справке по Lync Server 2013 и командлетам для [архивации и мониторинга командлетов в Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>Настройка политики конференц-связи

Просмотрите пример скрипта MeetingPolicy.ps1. Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и справка командлета для [командлетов веб-конференций в Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>Настройка политики контактов

Просмотрите пример ContactsPolicy.ps1. Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и справка командлета для [мгновенных сообщений и командлетов присутствия в Lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-federation-policy"></a>Настройка политики Федерации

Просмотрите пример FederationPolicy.ps1. Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и справке командлетов [пограничного сервера в командлетах Lync server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) , [Федерации и внешнего доступа в Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>Настройка политики контроля допуска звонков

Просмотрите пример BandwidthPolicy.ps1. Для получения дополнительных сведений ознакомьтесь со статьей Lync Server 2013 в документации по [контролю допуска звонков в Lync server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) и справке командлета для [командлетов контроля допуска звонков в Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>Настройка правил маршрутизации голосовой связи

Просмотрите пример RoutingRules.ps1. При настройке правил маршрутизации голосовой связи запишите контекст телефона (то есть,/Локатион Profile или/Симпленаме), а также внутренние/внешние коды областей, чтобы их можно было указать при создании пользователей и во время настройки Линкперфтул (в частности, для PSTN-UC и UC-PSTN). Например, параметр Симпленаме в вызове командлета **New – CsDialPlan** в RoutingRules.ps1 примере должен использоваться для значения LocationProfile на следующем рисунке UserProfileGenerator.exe.

![Пример правила маршрутизации голосовых вызовов.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Пример правила маршрутизации голосовых вызовов.")

Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и обратитесь к разделу Справка по командлетам [корпоративной голосовой связи в Lync server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>Настройка приложения помощника по конференц-связи

Просмотрите пример ConferenceAutoAttendantConfiguration.ps1. Запишите номер телефона КонференЦингаутоаттендант (1121111111 по умолчанию), чтобы можно было ввести его в средство настройки средства Линкперф для создания конфигурации.

![Настройка приложения "помощник по конференц-связи"](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Настройка приложения "помощник по конференц-связи"")

Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и справке командлета для [командлетов веб-конференций в Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) и [командлетах конференц-связи с телефонным подключением в Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Настройка службы парковки вызовов Lync Server

По умолчанию парковки вызовов отключен. Просмотрите пример CallParkConfiguration.ps1. Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и справка командлета для [командлетов приложений парковки вызовов в Lync server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-emergency-calls"></a>Настройка экстренных вызовов

Выполните указанные ниже действия, чтобы настроить нагрузочное тестирование и тестирование производительности для экстренных вызовов.

1.  Настройте маршрут голосовой связи для экстренных вызовов. Пример настройки этого маршрута голосовой связи представлен в RoutingRules.ps1 сценарии под комментарием "Route E911 to PSTN".
    
    <div>
    

    > [!WARNING]  
    > Пример команды в RoutingRules.ps1 имеет числовой шаблон, включающий число 119, а не 911. Не следует использовать 911 (или фактический локальный номер экстренного реагирования) для предотвращения случайных вызовов локальных аварийных операторов во время нагрузочного тестирования. Эта конфигурация предназначена только для целей моделирования.

    
    </div>

2.  Настройте адреса, заполнив значения на вкладке **LIS (LIS** ) в усерпровисионингтул, как показано на следующем рисунке.
    
    ![Настройка службы сведений о местоположении.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Настройка службы сведений о местоположении.")  

3.  Щелкните **создать файлы конфигурации LIS**.

4.  Создаются CSV-файлы для портов, подсетей, коммутаторов и точек беспроводного доступа (WAPs), а также XML-файла для средства нагрузки и производительности Lync Server 2013. CSV-файлы используются в качестве входных данных (в той же папке) при настройке службы сведений о местоположении (LIS) с помощью скрипта LisConfiguration.ps1. Переместите созданный файл Locations0.xml в ту же папку, где находится исполняемый файл Lync Server 2013 (LyncPerfTool.exe), в котором будут выполняться сценарии профилей расположения (абонентской группы).

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>Создание, включение, Настройка и отключение пользователей

Перед выполнением следующих сценариев необходимо создать всех пользователей. Следуйте инструкциям в статье [CREATE Users and Contacts](create-users-and-contacts.md) to Create Users. Для получения дополнительных сведений обратитесь к документации по командлетам Lync Server 2013 для командлетов [Get – CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))и [Disable – CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) .

</div>

<div>

## <a name="configuring-response-group-application"></a>Настройка приложения группы ответа

Просмотрите пример ResponseGroupConfiguration.ps1. Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и справка командлета для [командлетов приложений группы ответа в Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)). Чтобы просмотреть конфигурацию приложения группы ответа, посмотрите `https://<poolfqdn>/RgsConfig/` , как показано на следующем рисунке.

![Средство настройки группы ответа.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "Средство настройки группы ответа.")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

