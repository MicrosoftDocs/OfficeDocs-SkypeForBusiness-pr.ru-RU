---
title: 'Lync Server 2013: тестирование маршрутизации телефонных звонков PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b831aef01d80a0d68a0eea06f429502026b7ccb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>Тестирование маршрутизации телефонных звонков PSTN в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Daily (Ежедневный)</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsInterTrunkRouting</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет **Test-CsInterTrunkRouting** проверяет, могут ли вызовы маршрутизироваться от одного SIP к другому. Для этого для командлета задается телефонный номер и конфигурация магистрали. После этого **Test-CsInterTrunkRouting** сообщит о маршрутах обратного совпадения и использовании PSTN для указанного номера. Обратите внимание на то, что звонки могут маршрутизироваться между магистральными каналами, только если они имеют шаблон номера, соответствующий указанному номеру телефона и только тогда, когда магистрали имеют по крайней мере одно использование PSTN.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Команды, показанные ниже, возвращают подходящие маршруты и подходящие способы использования телефонов, которые позволяют пользователям звонить по телефону 1-206-555-1219 с помощью параметров конфигурации магистрали для сайта Redmond.

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если звонки могут маршрутизироваться от одного SIP к другому, будет выведен результат, подобный следующему:

Фирстматчинграуте Матчингусаже Матчинграутес

\------------------ ------------- --------------

Редмондрауте Локалусаже {Редмондрауте}

Если проверка завершилась неудачно, будет выведен результат, подобный следующему:

Test-CsInterTrunkRouting: не удается обработать Преобразование аргументов для параметра

"TrunkConfiguration". Недопустимый Трункконфигуратионсеттинг (параметр). Указать

допустимый параметр (параметр), а затем повторите попытку.

В строке: 1 символ: 79

\+Test-CsInterTrunkRouting-Таржетнумбер "Tel: + 12065551219"

\-TrunkConfiguration $t...

\+

~~

\+Категоринфо: Инвалиддата: (:) \[Test-CsInterTrunkRouting\], номинал

аметербиндингаргументтрансформатионексцептион

\+Фулликуалифиедеррорид: Параметераргументтрансформатионеррор, Microsoft. R

технически. Management. Voice. командлеты. Тестоксинтертрункраутингкмдлет

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsInterTrunkRouting** :

  - Указаны недопустимые параметры. Магистраль еще не настроен правильно, а указанный целевой номер может быть неверным или недопустимым.

</div>

<div>

## <a name="see-also"></a>См. также


[Get — CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get — CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

