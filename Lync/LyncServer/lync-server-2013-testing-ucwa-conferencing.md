---
title: 'Lync Server 2013: тестирование конференц-связи по UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5879eaa10b128bedbc1e28fe85cee40aed27dddd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503916"
---
# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Тестирование конференц-связи UCWA в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-11-03_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Ежедневное</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsUcwaConference</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Командлет **Test-CsUcwaConference** проверяет, может ли пользователь, запланировать, присоединиться к Конференции, а затем провести интерактивную конференцию с помощью веб-API объединенных коммуникаций (UCWA). Для этого командлет использует службу веб-билета Lync Server для проверки подлинности двух тестовых пользователей и их регистрации в Lync Server. Командлет затем запускает конференцию с помощью учетных данных организатора и приглашает участника присоединиться к встрече. После подключения к собранию командлет **Test-CsUcwaConference** проверяет, могут ли пользователи выполнять такие действия, как обмен мгновенными сообщениями и проведение пулов, а затем отключает конференцию и отменяет регистрацию двух тестовых пользователей. Запланированная Конференция также будет удалена после завершения теста.

Командлет **Test-CsUcwaConference** также можно использовать, чтобы определить, могут ли анонимные пользователи присоединяться к конференциям.

Обратите внимание на то, что командлет **Test-CsUcwaConference** не следует запускать для пула Microsoft Lync Server 2010, если UCWA не установлен в этом пуле. Если UCWA не установлен, вызов командлета **Test-CsUcwaConference** завершится с ошибками.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Команда, показанная в Примере 1 проверяет возможность для пары тестовых пользователей принимать участие в конференции UCWA на пуле atl-cs-001.litwareinc.com. Обратите внимание, что эта команда не будет выполнена успешно, если заранее не определены тестовые пользователи конфигурации мониторинга состояния для atl-cs-001.litwareinc.com.

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

Команды, показанные в примере 2, проверяют возможность использования пользователями двух пользователей (litwareinc \\ Pilar и litwareinc \\ kenmyer) для участия в конференции UCWA. Для этого первая команда в примере использует командлет Get-Credential для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Pilar Ackerman. (Так как имя для входа, litwareinc \\ Pilar, было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell необходимо, чтобы администратор вводил пароль для учетной записи Pilar Ackerman.) Полученный объект учетных данных сохраняется в переменной с именем $cred 1. Вторая команда производит аналогичную операцию, возвращая объект учетных данных для учетной записи Ken Myer.

При наличии двух объектов учетных данных в наличии третья команда в примере определяет, могут ли два пользователя участвовать в конференции UCWA. Для запуска этой задачи вызывается командлет **Test-CsUcwaConference** , а также следующие параметры: TargetFqdn (полное доменное имя пула регистратора); Организерсипаддресс (SIP-адрес организатора собрания); Организеркредентиал (объект Windows PowerShell, содержащий учетные данные для этого пользователя); ПартиЦипантсипаддресс (SIP-адрес для другого тестового пользователя); и ПартиЦипанткредентиал (объект интерфейса командной строки Windows PowerShell, который содержит учетные данные для другого пользователя).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если Конференц-связь настроена правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Целевой URI: https://Линктест – SE. Линктест. Селфхост. Corp.

Microsoft.com:443/CertProv/CertProvisiongService.svc

Результат: успешное выполнение

Задержка: 00:00:14.9862716

Сообщение об ошибке:

Диагност

Если указанные пользователи не могут использовать конференц-связь, результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз:

Предупреждение: не удалось считать номер порта регистратора для данного полного имени

доменное имя (FQDN). Использование номера порта регистратора по умолчанию. Возникновения

System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.

в

Microsoft. RTC. Management. SyntheticTransactions. Сипсинсетиктрансактион. Триретри

Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)

Test-CsUcwaConference: нет тестового пользователя, назначенного для

\[LyncTest.SelfHost.Corp.Microsoft.com \] . Проверьте конфигурацию тестовой учетной записи пользователя.

В строке: 1 символ: 1

\+ Test-CsUcwaConference TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+ Категоринфо: Ресаурцеунаваилабле: (:) \[ Test-CsUcwaConference\]

, InvalidOperationException

\+ Фулликуалифиедеррорид: Нотфаундтестусерс, Microsoft. RTC. Management. синтезатор

Етиктрансактионс. Тестукваконференцекмдлет

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsUcwaConference** :

  - Предоставлено неправильное значение параметра. Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками. Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.

  - Возможность проведения Конференции зависит от политики конференц-связи, назначенной пользователю, который организует конференцию (в случае командлета **Test-CsUcwaConference** , который является "отправителем"). Если организатор не может включать в свое собрание действия для совместной работы (например, если для свойства Енабледатаколлаборатион в политике конференц-связи задано значение false), командлет **Test-CsUcwaConference** завершится с ошибками.

  - Эта команда завершится с ошибками, если пограничный сервер неправильно настроен или еще не развернут.

</div>

<div>

## <a name="see-also"></a>См. также


[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[Test-Ксавконференце](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

