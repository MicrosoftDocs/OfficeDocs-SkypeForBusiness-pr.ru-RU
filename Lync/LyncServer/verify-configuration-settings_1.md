---
title: Проверка параметров настройки
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1ad498f25656e01507e55c41d98ff4bb9143b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508416"
---
# <a name="verify-configuration-settings"></a>Проверка параметров настройки

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

После объединения топологии и запуска командлета **Import – CsLegacyConfiguration** убедитесь, что политики и параметры Office Communications Server 2007 R2 были импортированы в Lync Server 2013. В следующей таблице приведены политики и параметры, которые следует проверить.

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>Политики и параметры, которые следует проверить после миграции


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>При использовании этой нагрузки:</th>
<th>Проверьте следующие политики и параметры:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Мгновенные сообщения и конференц-связь</p></td>
<td><p>Политика присутствия</p>
<p>Политика конференц-связи</p></td>
</tr>
<tr class="even">
<td><p>Конференц-связь с телефонным подключением</p></td>
<td><p>Номера для телефонного подключения</p>
<p>Абонентские группы</p></td>
</tr>
<tr class="odd">
<td><p>Корпоративная голосовая связь</p></td>
<td><p>Политика голосовой связи</p>
<p>Маршруты голосовых вызовов</p>
<p>Абонентские группы</p>
<p>Параметры использования ТСОП</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>Простые URL-адреса</p></td>
</tr>
<tr class="odd">
<td><p>Внешние пользователи</p></td>
<td><p>Политики внешнего доступа</p></td>
</tr>
<tr class="even">
<td><p>Архивация</p></td>
<td><p>Политика архивации</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>Чтобы проверить политики и параметры

1.  В среде Office Communications Server 2007 R2 запишите названия абонентских группы (ранее называемые профилями мест), Номера доступа для телефонного подключения (номера телефонов для доступа к конференциям и регионы), маршруты голосовой связи и политики, перечисленные в предыдущей таблице, в дополнение к URL-адресам, используемым для веб-клиента Communicator.

2.  На сервере переднего плана Lync Server 2013 откройте панель управления Lync Server.

3.  Чтобы проверить импортированные политики конференц-связи, в левой области щелкните **Конференц**-связь, выберите пункт **Политика Конференц**-связи, а затем убедитесь, что все политики конференц-связи в среде Office Communications Server 2007 R2 включены в список.
    
    <div>
    

    > [!NOTE]  
    > Политика конференц-связи из предыдущих версий Office Communications Server теперь <STRONG>называется политикой Конференц</STRONG> -связи в Lync Server 2013. Кроме того, параметр <STRONG>анонимного партикпантс</STRONG> из предыдущих версий Office Communications Server теперь является параметром политики конференц-связи Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > В Office Communications Server 2007 R2, если политика конференц-связи не настроена на <STRONG>использование для пользователя</STRONG>, импортируются только глобальные параметры политики. В этом случае никакие другие политики конференц-связи не импортируются.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Если <STRONG>Анонимные участники</STRONG> настроены для <STRONG>применения</STRONG> в политике конференц-связи Office Communications Server 2007 R2, в процессе миграции создаются две политики конференц-связи: один с <STRONG>аллованонимауспартиЦипантсинмитингс</STRONG> , для которого задано <STRONG>значение true</STRONG> , а для параметра <STRONG>аллованонимауспартиЦипантсинмитингс</STRONG> задано <STRONG>значение false</STRONG>.

    
    </div>

4.  Чтобы проверить импортированные абонентские группы, щелкните **Маршрутизация голосовой связи**, щелкните **Абонентская группа**, затем убедитесь, что все абонентские планы из среды Office Communicator 2007 R2 включены в список.
    
    <div>
    

    > [!NOTE]  
    > В Lync Server 2013 <STRONG>профили местоположения</STRONG> теперь называются <STRONG>телефонными планами</STRONG>.

    
    </div>

5.  Чтобы проверить импортированные политики голосовой связи, щелкните **Маршрутизация голосовой связи**, щелкните **Политика голосовой связи**, затем убедитесь, что все политики голосовой связи из среды Office Communicator 2007 R2 включены в список.
    
    <div>
    

    > [!NOTE]  
    > Если политика голосовой связи не настроена для <STRONG>использования на уровне пользователя</STRONG> в среде Office Communications Server 2007 R2, импортируются только глобальные параметры политики. В этом случае никакие другие политики голосовой связи не импортируются.

    
    </div>

6.  Чтобы проверить импортированные маршруты голосовой связи, щелкните **Маршрутизация голосовой связи**, щелкните **Маршрут**, затем убедитесь, что все маршруты голосовой связи из среды Office Communicator 2007 R2 включены в список.

7.  Чтобы проверить импортированные параметры использования ТСОП, щелкните **Маршрутизация голосовой связи**, щелкните **Использование ТСОП**, затем убедитесь, что параметры использования ТСОП из среды Office Communicator 2007 R2 включены в список.

8.  Чтобы проверить импортированные политики внешнего доступа, щелкните **Федерация и внешний доступ**, щелкните **Политика внешнего доступа**, затем убедитесь, что все политики внешнего доступа из среды Office Communicator 2007 R2 включены в список.

9.  Чтобы проверить политики архивации, щелкните **мониторинг и архивация**, щелкните **Политика архивации**, а затем убедитесь, что все политики архивирования в среде Office Communications Server 2007 R2 включены в список.

10. Откройте командную консоль Lync Server.

11. Чтобы проверить политики присутствия, введите в командной строке следующую команду:
    
        Get-CsPresencePolicy
    
    Взглянув на имя в параметре **Identity** , убедитесь, что все политики присутствия в среде Office Communications Server 2007 R2 импортированы.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>Чтобы проверить политики и параметры с помощью командлетов

1.  Откройте командную консоль Lync Server.

2.  Запустите командлеты в следующей таблице для проверки политик и параметров.
    
    Синтаксис этих командлетов аналогичен следующему примеру:
    
        Get-CsConferencingPolicy
    
    Для получения дополнительных сведений об этих командлетах, выполните следующую команду:
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Для этой политики или параметра:</th>
<th>Используйте следующий командлет:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Политика присутствия</p></td>
<td><p><strong>Get-CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Политика конференц-связи</p></td>
<td><p><strong>Get-CsConferencingPolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>Номера для телефонного подключения</p></td>
<td><p><strong>Get — CsDialInConferencingAccessNumber</strong></p></td>
</tr>
<tr class="even">
<td><p>Абонентские группы</p></td>
<td><p><strong>Get-CsDialPlan</strong></p></td>
</tr>
<tr class="odd">
<td><p>Политика голосовой связи</p></td>
<td><p><strong>Get-CsVoicePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Маршруты голосовых вызовов</p></td>
<td><p><strong>Get — Ксвоицерауте</strong></p></td>
</tr>
<tr class="odd">
<td><p>Использование ТСОП</p></td>
<td><p><strong>Get — Кспстнусаже</strong></p></td>
</tr>
<tr class="even">
<td><p>URL-адреса</p></td>
<td><p><strong>Get — CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>Политики внешнего доступа</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Политика архивации</p></td>
<td><p><strong>Get — CsArchivingPolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

