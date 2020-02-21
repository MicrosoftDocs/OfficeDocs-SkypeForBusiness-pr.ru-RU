---
title: 'Lync Server 2013: тестирование доступа к единому хранилищу контактов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34dbf6ede9f58b39df1722e742511ee0844c41f7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>Тестирование доступа к единому хранилищу контактов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2015-05-15_


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
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsUnifiedContactStore</strong> . Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Единое хранилище контактов, представленное в Lync Server 2013, дает администраторам возможность хранить контакты пользователя в Microsoft Exchange Server 2013, а не в Lync Server. Это позволяет пользователю получить доступ к тому же набору контактов в Outlook Web Access в дополнение к Lync 2013. (Или вы можете продолжить хранение контактов в Lync Server. В этом случае пользователям потребуется поддерживать два отдельных набора контактов: один для использования с Outlook и Outlook Web Access и один для использования с Lync 2013.)

Чтобы определить, были ли контакты пользователя перемещены в единое хранилище контактов, запустите командлет **Test-CsUnifiedContactStore** . Командлет **Test-CsUnifiedContactStore** принимает указанную учетную запись пользователя, подключается к единому хранилищу контактов и пытается получить контакт для пользователя. Если не удается получить контакты, команда завершится с сообщением "нет контактов, полученных для пользователя". Убедитесь, что контакты существуют для пользователя. "

Обратите внимание на то, что командлет **Test-CsUnifiedContactStore** завершится с ошибками, если пользователь успешно выполнил миграцию в единое хранилище контактов, но не имеет контактов в своем списке контактов. Указанный пользователь должен иметь по крайней мере один контакт для успешного выполнения командлета **Test-CsUnifiedContactStore** .

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Команды, показанные в следующем примере, определяют, можно ли найти контакты\\для пользователя litwareinc kenmyer в едином хранилище контактов. Для этого первая команда в примере использует командлет **Get – Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell для пользователя litwareinc\\kenmyer. Обратите внимание, что для этой учетной записи необходимо указать пароль, чтобы создать допустимый объект учетных данных, а затем убедиться, что командлет **Test-CsUnifiedContactStore** может выполнить его проверку.

Вторая команда в примере использует предоставленный объект учетных данных ($x) и SIP-адрес пользователя litwareinc\\kenmyer, чтобы определить, можно ли найти его контакты в едином хранилище контактов.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если доступ к хранилищу контактов настроен правильно, будут получены выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success.**

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:14.9862716

Сообщение об ошибке:

Диагност

Если доступ к хранилищу контактов настроен неправильно, результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз:

Предупреждение: не удалось считать номер порта регистратора для данного полного имени

доменное имя (FQDN). Использование номера порта регистратора по умолчанию. Возникновения

System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.

в

Microsoft. RTC. Management. SyntheticTransactions. Сипсинсетиктрансактион. Триретри

Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)

Целевое полное доменное имя: atl-cs-001.litwareinc.com

Результат: сбой

Задержка: 00:00:00

Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона

не ответил должным образом по истечении определенного периода времени или

не удалось установить подключение, так как у подключенного узла есть

не удалось ответить на 10.188.116.96:5061

Внутреннее исключение: сбой попытки подключения, так как

подключенная сторона не ответила должным образом после периода

время или установленное подключение не выполнено, так как подключенный узел

не удалось ответить на 10.188.116.96:5061

Диагност

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsUnifiedContactStore** :

  - Предоставлено неправильное значение параметра. Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками. Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.

  - Не удалось подключиться к единому хранилищу контактов, и попытка получить контакт для пользователя была невозможна. Возможны проблемы с сетевым подключением.

</div>

<div>

## <a name="see-also"></a>См. также


[New — CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[Set — CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

