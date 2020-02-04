---
title: Проверка параметров настройки
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4d13f3bdd5af1a2c9b90e190775522ea6f11b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>Проверка параметров настройки

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

После того как вы объедините топологию и запустите командлет **Import-кслегациконфигуратион** , убедитесь, что политики и параметры Office Communications Server 2007 R2 были импортированы в Lync Server 2013. В следующей таблице перечислены политики и параметры, которые необходимо проверить.

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>Политики и параметры для проверки после миграции


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>При использовании этой рабочей нагрузки:</th>
<th>Проверьте следующие политики и параметры.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Обмен мгновенными сообщениями и конференц-связь</p></td>
<td><p>Политика присутствия</p>
<p>Политика конференц-связи</p></td>
</tr>
<tr class="even">
<td><p>Конференц-связь с телефонным подключением</p></td>
<td><p>Номера доступа для телефонного подключения</p>
<p>Абонентские группы</p></td>
</tr>
<tr class="odd">
<td><p>Корпоративная голосовая связь</p></td>
<td><p>Политика голосовой связи</p>
<p>Маршруты голосовых вызовов</p>
<p>Абонентские группы</p>
<p>Параметры использования PSTN</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>Простые URL-адреса</p></td>
</tr>
<tr class="odd">
<td><p>внешние пользователи;</p></td>
<td><p>Политики внешнего доступа</p></td>
</tr>
<tr class="even">
<td><p>Архивирование</p></td>
<td><p>Политика архивации</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>Проверка политик и параметров

1.  В среде Office Communications Server 2007 R2 Обратите внимание на названия абонентских планов (прежнее название — профили местоположений) и номера доступа для телефонного подключения (номера телефонов для доступа к конференциям), Голосовые маршруты и политики, указанные в разделе Предыдущая таблица в дополнение к URL-адресам, используемым в Communicator Web Access.

2.  На сервере переднего плана Lync Server 2013 откройте панель управления Lync Server.

3.  Чтобы проверить импортированные политики конференц-связи, на левой панели выберите **Конференц**-связь, нажмите кнопку **Политика конференции**и убедитесь, что все политики конференций в среде Office Communications Server 2007 R2 включены в список.
    
    <div>
    

    > [!NOTE]  
    > Политика <STRONG>собраний</STRONG> из предыдущих версий Office Communications Server теперь называется политикой конференц-связи в Lync Server 2013. Кроме того, параметр <STRONG>анонимного партикпантс</STRONG> из предыдущих версий Office Communications Server теперь является параметром в политике конференц-связи Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > В Office Communications Server 2007 R2, если политика Конференции не настроена на <STRONG>использование для пользователей</STRONG>, импортируются только глобальные параметры политики. В этой ситуации другие политики Конференции не импортируются.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Если <STRONG>Анонимные участники</STRONG> настроены на <STRONG>принудительное применение</STRONG> в политике конференц-связи Office Communications Server 2007 R2, во время миграции создаются две политики конференций: один с <STRONG>аллованонимауспартиЦипантсинмитингс</STRONG> , для которого установлено значение <STRONG>true</STRONG> , а для <STRONG>аллованонимауспартиЦипантсинмитингс</STRONG> задано значение <STRONG>false</STRONG>.

    
    </div>

4.  Чтобы проверить импортированные абонентские группы, выберите пункт **Маршрутизация голосовых сообщений**, щелкните **абонентская группа**и убедитесь, что все абонентские группы в среде Office Communicator 2007 R2 включены в список.
    
    <div>
    

    > [!NOTE]  
    > В Lync Server 2013 <STRONG>Профили местоположений</STRONG> теперь называются <STRONG>телефонными планами</STRONG>.

    
    </div>

5.  Чтобы проверить импортированные политики голосовой связи, выберите пункт **Маршрутизация голоса**, нажмите кнопку **политика голосовой связи**и убедитесь, что все политики голосовой связи в среде Office Communicator 2007 R2 включены в список.
    
    <div>
    

    > [!NOTE]  
    > Если политика голосовой связи не настроена на <STRONG>использование для пользователей</STRONG> в среде Office Communications Server 2007 R2, импортируются только глобальные параметры политики. Другие политики голосовой связи в этой ситуации не импортируются.

    
    </div>

6.  Для проверки импортированных голосовых маршрутов выберите пункт **Маршрутизация голосовой связи**, нажмите кнопку **маршрут**и убедитесь в том, что все голосовые маршруты в среде Office Communicator 2007 R2 включены в список.

7.  Чтобы проверить импорт параметров использования PSTN, выберите пункт **Маршрутизация голосовой связи**, выберите **Использование PSTN**и убедитесь, что параметры использования PSTN из среды Office Communicator 2007 R2 включены в список.

8.  Чтобы проверить импортированные внешние политики доступа, выберите пункт **Федерация и внешний доступ**, нажмите кнопку **Политика внешних доступа**, а затем убедитесь, что все политики доступа в среде Office Communicator 2007 R2 включены в список.

9.  Чтобы проверить политики архивации, выберите пункт **мониторинг и архивация**, нажмите кнопку **Политика архивации**и убедитесь, что все политики архивации в среде Office Communications Server 2007 R2 включены в список.

10. Откройте командную консоль Lync Server Management Shell.

11. Чтобы проверить политики присутствия, в командной строке введите следующую команду:
    
        Get-CsPresencePolicy
    
    Изучив имя в параметре **Identity** , убедитесь в том, что все политики присутствия в среде Office Communications Server 2007 R2 импортированы.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>Проверка политик и параметров с помощью командлетов

1.  Откройте командную консоль Lync Server Management Shell.

2.  Чтобы проверить политики и параметры, выполните командлеты, приведенные в следующей таблице.
    
    Синтаксис этих командлетов подобен приведенному ниже примеру.
    
        Get-CsConferencingPolicy
    
    Чтобы получить подробные сведения об этих командлетах, выполните следующие действия:
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Для этой политики или параметра:</th>
<th>Используйте этот командлет:</th>
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
<td><p>Номера доступа для телефонного подключения</p></td>
<td><p><strong>Get-CsDialInConferencingAccessNumber</strong></p></td>
</tr>
<tr class="even">
<td><p>Абонентские группы</p></td>
<td><p><strong>Get-CsDialPlan</strong></p></td>
</tr>
<tr class="odd">
<td><p>Политика голосовой связи</p></td>
<td><p><strong>Get-Ксвоицеполици</strong></p></td>
</tr>
<tr class="even">
<td><p>Маршруты голосовых вызовов</p></td>
<td><p><strong>Get-CsVoiceRoute</strong></p></td>
</tr>
<tr class="odd">
<td><p>Использование ТСОП</p></td>
<td><p><strong>Get-CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>URL-адреса</p></td>
<td><p><strong>Get-CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>Политики внешнего доступа</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Политика архивации</p></td>
<td><p><strong>Get-CsArchivingPolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

