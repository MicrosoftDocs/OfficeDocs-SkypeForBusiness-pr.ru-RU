---
title: 'Lync Server 2013: Конфигурация узла контрольных значений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d2c79de4f86e490244ef63948c263d8f387fc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Конфигурация узла контрольных значений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-11-03_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Ежедневно</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Требуемые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</p>
<p>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-ксватчернодеконфигуратион</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Если вы используете Microsoft System Center Operations Manager для мониторинга сервера Lync Server 2013, у вас есть возможность настроить "узлы контрольных данных": компьютеры, периодически и автоматически выполняющие синтетические транзакции для проверки работы сервера Lync Server. должным. Узлы наблюдателей назначаются пулам и управляются с помощью командлетов **ксватчернодеконфигуратион** . Обратите внимание, что при использовании System Center Operations Manager вам не нужно устанавливать узлы наблюдения. Вы по-прежнему можете отслеживать систему без использования узлов-наблюдателей. Единственная разница заключается в том, что все синтетические транзакции, которые необходимо выполнить, должны вызываться вручную, а не автоматически с помощью Operations Manager.

Командлет **Test-ксватчернодеконфигуратион** позволяет проверить, правильно ли настроен узел наблюдателя и назначен допустимым пулам Lync Server 2013. Обратите внимание на то, что командлет **Test-ксватчернодеконфигуратион** должен выполняться на самом узле наблюдателя. Командлет не может выполняться для удаленных компьютеров.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Следующая команда проверяет параметры конфигурации для каждого узла-наблюдателя, который используется в Организации.

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успеха или сбоя

Приведенный ниже успешный пример показывает систему с четырьмя пограничными серверами.

Проверка целевого пула atl-cs-001.litwareinc.com в соответствии с топологией.

Успех: конечный пул atl-cs-001.litwareinc.com существует в топологии.

Успех: на целевом пуле atl-cs-001.litwareinc.com установлена роль регистратора.

Успех: atl-cs-001.litwareinc.com пула поддерживает версию.

Успех: номер порта для целевого atl-cs-001.litwareinc.com пула 5061 является правильным.

Проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя начинается. Если обнаружена какая – либо ошибка, она будет распечатана.

Проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя завершена.

Начата проверка разделов реестра узла-наблюдателя, созданных при установке узла-наблюдателя. Если обнаружена какая – либо ошибка, она будет распечатана.

Проверка наличия разделов реестра узла-наблюдателя, созданных при установке узла-наблюдателя, завершено. Обнаруженный тип проверки подлинности — Negotiate.

Проверка существования учетных данных тестового пользователя: user1 @ atl-cs-001.litwareinc.com в магазине управления учетными данными выполнена успешно.

Успешная проверка существования учетных данных тестового пользователя: Пользователь2 @ atl-cs-001.litwareinc.com в хранилище управления учетными данными.

Проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя начинается. Если обнаружена какая – либо ошибка, она будет распечатана.

Предупреждение: atl-cs-001.litwareinc.com пула имеет регистратор

роль установлена, но для нее не заданы тестовые пользователи.

Проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя завершена.

Проверка наличия разделов реестра для узла-наблюдателя, созданных при установке узла-наблюдателя, —

загружен. Если обнаружена какая – либо ошибка, она будет распечатана.

Test-Ксватчернодеконфигуратион: не удается найти раздел реестра Health в

\\Программное\\обеспечение Microsoft для обмена данными в режиме реального времени. Убедитесь в том, что узел наблюдателя. MSI является

установлено правильно.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксватчернодеконфигуратион** :

  - Узел-наблюдатель установлен неправильно.

  - Тестовые пользователи не настроены.

</div>

<div>

## <a name="see-also"></a>См. также


[Get-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[Remove-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

