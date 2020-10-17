---
title: 'Lync Server 2013: Конфигурация узла-наблюдателя тестирования'
description: 'Lync Server 2013: Конфигурация узла-наблюдателя тестирования.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1eeb141eee011d7e06f5dd49e483e026484d733
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546845"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Конфигурация узла-наблюдателя тестирования в Lync Server 2013

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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsWatcherNodeConfiguration</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Если вы используете Microsoft System Center Operations Manager для мониторинга Lync Server 2013, то у вас есть возможность настройки "узлов-наблюдателей": компьютеры, которые периодически и автоматически выполняют искусственные транзакции, чтобы убедиться, что Lync Server работает должным образом. Узлы-наблюдатели назначаются пулам и управляются с помощью командлетов **CsWatcherNodeConfiguration** . Следует отметить, что при использовании System Center Operations Manager устанавливать узлы-наблюдатели не обязательно. Вы по-прежнему можете отслеживать систему без использования узлов-наблюдателей. Единственное отличие заключается в том, что все искусственные транзакции, которые требуется запустить, необходимо вызвать вручную, а не автоматически вызывать Operations Manager.

Командлет **Test-CsWatcherNodeConfiguration** позволяет проверить правильность настройки узла-наблюдателя и присвоения действительного пула Lync Server 2013. Обратите внимание на то, что командлет **Test-CsWatcherNodeConfiguration** должен быть запущен на самом узле-наблюдателе. Командлет не может выполняться для удаленных компьютеров.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Следующая команда проверяет параметры конфигурации для каждого узла-наблюдателя, используемого в Организации.

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

В приведенном ниже примере показана успешная система с четырьмя пограничными серверами.

Проверка целевого пула atl-cs-001.litwareinc.com в соответствии с топологией.

Успех: целевой пул atl-cs-001.litwareinc.com существует в топологии.

Успешно: в целевом пуле atl-cs-001.litwareinc.com установлена роль регистратора.

Успех: целевой пул atl-cs-001.litwareinc.com поддерживаемая версия.

Успех: номер порта для 5061 целевого пула atl-cs-001.litwareinc.com правильный.

Запущена проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя. Если обнаружена какая-либо ошибка, она будет распечатана.

Проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя завершена.

Выполняется проверка наличия разделов реестра узла-наблюдателя, созданных при установке узла-наблюдателя. Если обнаружена какая-либо ошибка, она будет распечатана.

Проверка наличия разделов реестра узла-наблюдателя, созданных при установке узла-наблюдателя, завершена. Обнаруженный тип проверки подлинности — Negotiate.

Успешная проверка существования учетных данных тестового пользователя SIP: user1@ atl-cs-001.litwareinc.com в хранилище управления учетными данными.

Успешная проверка существования учетных данных тестового пользователя SIP: user2@ atl-cs-001.litwareinc.com в хранилище управления учетными данными.

Запущена проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя. Если обнаружена какая-либо ошибка, она будет распечатана.

Предупреждение: atl-cs-001.litwareinc.com пула имеет регистратор

роль установлена, но тестовые пользователи не настроены.

Проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя завершена.

Проверка наличия разделов реестра узла-наблюдателя, созданных при установке узла-наблюдателя, — это

выполняться. Если обнаружена какая-либо ошибка, она будет распечатана.

Test-CsWatcherNodeConfiguration: не удается найти раздел реестра работоспособности в

Программное обеспечение \\ \\ связи в режиме реального времени Майкрософт. Убедитесь, что узел наблюдателя. MSI является

правильно установлен.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsWatcherNodeConfiguration** :

  - Узел-наблюдатель установлен неправильно.

  - Тестовые пользователи не настроены.

</div>

<div>

## <a name="see-also"></a>См. также


[Get — CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New — CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[Remove — CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set — CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

