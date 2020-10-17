---
title: Настройка тестовых пользователей и параметров конфигурации узла-наблюдателя
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65ecb6946bcbb7244ef3e5ef8504312063ab1bd9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507526"
---
# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Настройка тестовых пользователей и параметров конфигурации узла-наблюдателя в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-07-29_

Настроив компьютер, который будет выступать в качестве узла-наблюдателя, выполните следующие действия.

1.  Создайте тестовые учетные записи, которые будут использоваться узлами-наблюдателями. Если вы используете проверку подлинности согласованием, вам также необходимо выполнить командлет [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)), чтобы разрешить использование этих учетных записей узлом-наблюдателем.

2.  Обновите параметры конфигурации узла-наблюдателя.

Содержание раздела:

  - Настройка тестовых учетных записей пользователей

  - Настройка базового узла-наблюдателя, использующего искусственные транзакции по умолчанию

  - Настройка расширенных тестов

  - Добавление и удаление искусственных транзакций

  - Просмотр и тестирование конфигурации узла-наблюдателя

<div>

## <a name="configuring-test-user-accounts"></a>Настройка тестовых учетных записей пользователей

Тестовые пользователи не должны представлять реальных людей, но они должны быть действительными учетными записями доменных служб Active Directory; Кроме того, эти учетные записи должны быть включены для Lync Server 2013, они должны иметь допустимые SIP-адреса, а также должны быть включены для корпоративной голосовой связи (для использования Test-CsPstnPeerToPeerCall искусственной транзакции). При использовании метода проверки подлинности TrustedServer все, что нужно сделать, — убедиться, что эти учетные записи существуют и настроены указанным ниже образом. Необходимо назначить по крайней мере трех тестовых пользователей для каждого пула, который необходимо протестировать.

При использовании метода проверки подлинности Negotiate также необходимо использовать командлет **Set-CsTestUserCredential** и командную консоль Lync Server, чтобы включить эти тестовые учетные записи для работы с искусственными транзакциями. Это можно сделать, выполнив команду, аналогичную приведенной ниже. (В этих командах предполагается, что три учетные записи пользователей Active Directory уже созданы и что эти учетные записи были включены для Lync Server 2013.):

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Обратите внимание, что необходимо указать не только адрес SIP, но и имя пользователя и пароль. Если вы не включите пароль Set-CsTestUserCredential предложит ввести эту информацию. Имя пользователя можно указать с помощью формата имени домена \\ , показанного выше, или с помощью формата name@domain имени пользователя; например:

    -UserName "watcher3@litwareinc.com"

Чтобы убедиться, что учетные данные тестового пользователя были созданы, выполните следующие команды в командной консоли Lync Server:

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Команды возвращают сведения о каждом пользователе, похожие на следующие.

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Настройка базового узла-наблюдателя, использующего искусственные транзакции по умолчанию

Создав тестовых пользователей, вы можете создать узел-наблюдатель с помощью следующей команды.

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Эта команда создает узел-наблюдатель с параметрами по умолчанию, который выполняет набор искусственных транзакций по умолчанию. Для нового узла-наблюдателя используются тестовые пользователи watcher1@litwareinc.com, watcher2@litwareinc.com и watcher3@litwareinc.com. Если узел-наблюдатель использует проверку подлинности TrustedServer, три тестовые учетные записи могут быть любыми допустимыми учетными записями пользователей, включенными для Active Directory и Lync Server. Если узел-наблюдатель использует проверку подлинности согласованием, вам нужно разрешить использование этих учетных записей узлом-наблюдателем с помощью командлета **Set-CsTestUserCredential**.

</div>

<div>

## <a name="configuring-extended-tests"></a>Настройка расширенных тестов

Если вы хотите включить тест ТСОП, проверяющий подключение к телефонной сети общего пользования, вам потребуется произвести дополнительную настройку узла-наблюдателя. Во-первых, вам нужно связать тестовых пользователей с типом теста ТСОП. Для этого выполните следующую команду в командной консоли Lync Server:

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Обратите внимание на то, что результаты выполнения этой команды необходимо сохранить в переменной. В этом примере используется переменная $pstnTest.

На этом шаге можно использовать командлет **New-CsWatcherNodeConfiguration** , чтобы связать тип теста (хранящийся в переменной $pstnTest) с пулом Lync Server 2013. Например, следующая команда создает конфигурацию узла-наблюдателя для пула atl-cs-001.litwareinc.com, добавляет трех тестовых пользователей, созданных ранее, а также тест ТСОП.

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Обратите внимание на то, что предыдущая команда завершится с ошибками, если на компьютере узла-наблюдателя не установлены основные файлы Lync Server и база данных RTCLocal.

Чтобы протестировать несколько политик голосовой связи, вам нужно создать расширенный тест для каждой политики с помощью командлета **New-CsExtendedTest**. Для пользователей, назначенных этому тесту, следует настроить требуемые политики голосовой связи. После этого передайте расширенные тесты в командлет **New-CsWatcherNodeConfiguration** с помощью следующей команды.

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Так как командлет New-CsWatcherNodeConfiguration был вызван без параметра Tests, то для нового узла-наблюдателя будут включены только искусственные транзакции по умолчанию и указанные расширенные искусственные транзакции. Это означает, что узел-наблюдатель будет тестировать следующие компоненты:

  - Registration

  - "IM" (Обмен мгновенными сообщениями);

  - граупим

  - P2PAV (одноранговые аудио- и видеосеансы)

  - AvConference (аудио- и видеоконференции)

  - Присутствие

  - ABS (служба адресной книги)

  - ABWQ (веб-служба адресной книги)

  - ТСОП (звонки через шлюз ТСОП, определенные как расширенный тест; по умолчанию тест ТСОП отключен, но в этом случае он включен с помощью параметра ExtendedTests, используемого в команде)

Это также означает, что следующие компоненты не будут тестироваться по умолчанию:

  - аведжеконнективити

  - MCXP2PIM (обмен мгновенными сообщениями с помощью мобильных устройств)

  - ExumConnectivity (единая система обмена сообщениями Exchange)

  - жоинлаунчер

  - персистентчатмессаже

  - DataConference

  - ксмппим

  - унифиедконтактсторе

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>Добавление и удаление искусственных транзакций

После настройки узла-наблюдателя вы можете добавлять искусственные транзакции на узел-наблюдатель или удалять их с узла-наблюдателя с помощью командлета **Set-CsWatcherNodeConfiguration**. Например, чтобы добавить тест PersistentChatMessage на узел-наблюдатель, используйте следующую команду с методом Add.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

При указании нескольких тестов используйте запятые. Пример:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Имейте в виду, что если один или несколько этих тестов (например, DataConference) уже были включены на узле-наблюдателе, произойдет ошибка. В этом случае вы получите следующее сообщение.

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

Если произошла эта ошибка, изменения не применяются. Команду следует выполнить повторно, удалив повторяющийся тест.

Чтобы удалить искусственную транзакцию с узла-наблюдателя, вместо метода Add используйте метод Remove. Например, следующая команда удаляет тест ABWQ с узла-наблюдателя.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

С помощью метода Replace вы можете также заменить все тесты, включенные в настоящий момент, на один или несколько новых тестов. Например, если вы хотите, чтобы узел-наблюдатель выполнял только тест IM, вы можете использовать следующую команду.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

При выполнении предыдущей команды на указанном узле-наблюдателе отключаются все искусственные транзакции, кроме IM.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>Просмотр и тестирование конфигурации узла-наблюдателя

Чтобы просмотреть тесты, назначенные узлу-наблюдателю, используйте следующую команду.

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

Предыдущая команда возвращает сведения, схожие со следующими (с учетом искусственных транзакций, назначенных узлу).

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> Чтобы просмотреть искусственные транзакции в алфавитном порядке, используйте следующую команду.<BR>Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object



</div>

Чтобы проверить, был ли создан узел-наблюдатель, введите в командной консоли Lync Server следующую команду:

    Get-CsWatcherNodeConfiguration

Команда возвращает сведения, похожие на следующие.

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Чтобы убедиться в правильности настройки узла-наблюдателя, введите следующую команду в командной консоли Lync Server:

    Test-CsWatcherNodeConfiguration

Предыдущая команда проверяет каждый узел-наблюдатель в развертывании и сообщает следующие сведения:

  - установлена ли требуемая роль Регистратора;

  - созданы ли требуемые разделы реестра при запуске команды Set-CsWatcherNodeConfiguration;

  - На ваших серверах работает правильная версия Lync Server.

  - правильно ли настроены порты;

  - имеются ли у назначенных тестовых пользователей требуемые учетные данные.

</div>

</div>

<span> </span>

</div>

</div>

</div>

