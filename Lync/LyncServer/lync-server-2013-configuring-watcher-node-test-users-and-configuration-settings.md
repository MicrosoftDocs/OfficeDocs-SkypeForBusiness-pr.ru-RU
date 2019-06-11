---
title: Настройка пользователей и параметров конфигурации для проверки узлов-наблюдателей
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d446934e8d84a12a6eecd84fbc94a956d8ae95e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Настройка пользователей и параметров конфигурации для проверки узла-наблюдателя в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-07-29_

Настроив компьютер, который будет выступать в качестве узла-наблюдателя, выполните следующие действия.

1.  Создание тестовых учетных записей, которые будут использоваться этими узлами контрольного следа. Если вы используете проверку подлинности согласованием, вам также необходимо выполнить командлет [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)), чтобы разрешить использование этих учетных записей узлом-наблюдателем.

2.  Обновите параметры конфигурации узла-наблюдателя.

В этом разделе рассматриваются следующие вопросы:

  - Настройка тестовых учетных записей пользователей

  - Настройка основного узла наблюдения с синтетическими транзакциями по умолчанию

  - Настройка расширенных тестов

  - Добавление и удаление искусственных транзакций

  - Просмотр и тестирование конфигурации узла-наблюдателя

<div>

## <a name="configuring-test-user-accounts"></a>Настройка тестовых учетных записей пользователей

Тестовые пользователи не должны представлять реальных пользователей, но они должны быть действительными учетными записями доменных служб Active Directory; Кроме того, эти учетные записи должны быть включены для Lync Server 2013, они должны иметь действительные адреса SIP, и они должны быть включены для использования в корпоративных голосовых целях (чтобы использовать синтетическую транзакцию Test-Кспстнпиртопиркалл). При использовании метода проверки подлинности Трустедсервер все, что вам нужно сделать, — это убедиться, что эти учетные записи существуют и настроены указанным образом. You should assign at least three test users for each pool that you want to test.

Если вы используете метод проверки подлинности Negotiate, необходимо также использовать командлет **Set-кстестусеркредентиал** и командную консоль Lync Server, чтобы включить эти тестовые учетные записи для работы с искусственными транзакциями. Это можно сделать, выполнив команду, подобную следующей: (В этом разделе предполагается, что три учетные записи пользователей Active Directory уже созданы и что эти учетные записи включены для Lync Server 2013.):

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Обратите внимание, что необходимо указать не только адрес SIP, но и имя пользователя и пароль. Если пароль не указан, Кстестусеркредентиал предложит ввести эти данные. Имя пользователя можно указать с помощью формата доменных\\имен, показанного выше, или с помощью команды формат имени пользователя @ доменного имени; Например:

    -UserName "watcher3@litwareinc.com"

Чтобы убедиться, что учетные данные тестового пользователя были созданы, выполните эти команды в командной консоли Lync Server Management Shell.

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Данные, подобные этим, должны быть возвращены каждому пользователю:

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Настройка основного узла наблюдения с синтетическими транзакциями по умолчанию

После создания тестовых пользователей вы можете создать узел наблюдателя с помощью следующей команды:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Эта команда создает узел-наблюдатель с параметрами по умолчанию, который выполняет набор искусственных транзакций по умолчанию. Для нового узла-наблюдателя используются тестовые пользователи watcher1@litwareinc.com, watcher2@litwareinc.com и watcher3@litwareinc.com. Если узел наблюдателя использует проверку подлинности Трустедсервер, то три тестовых учетных записей могут быть любыми действительными учетными записями пользователей, включенными для службы каталогов Active Directory и Lync Server. Если узел наблюдателя использует метод проверки подлинности Negotiate, необходимо также включить эти учетные записи пользователей для узла наблюдателя с помощью командлета **Set-кстестусеркредентиал** .

</div>

<div>

## <a name="configuring-extended-tests"></a>Настройка расширенных тестов

Если вы хотите включить коммутируемую телефонную сеть с открытым коммутируемым подключением (для проверки PSTN), которая проверяет связь с телефонной сетью с открытым подключением, вам потребуется дополнительная настройка при настройке узла-наблюдателя. Сначала необходимо связать тестовых пользователей с типом проверки КТСОП. Для этого выполните следующую команду в командной консоли Lync Server.

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Обратите внимание, что результаты этой команды должны храниться в переменной. В этом примере это переменная с именем $pstnTest.

На этом этапе можно с помощью командлета **New-ксватчернодеконфигуратион** связать тип теста (хранящийся в переменной $pstnTest) с пулом Lync Server 2013. Например, следующая команда создает новую конфигурацию узла-наблюдателя для пула atl-cs-001.litwareinc.com, добавляя трех тестовых пользователей, которые были созданы ранее, а также добавляя тип теста КТСОП.

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Обратите внимание на то, что предыдущая команда завершится сбоем, если вы не установили файлы основных файлов Lync Server и базу данных Ртклокал на компьютере с узлом-наблюдателем.

Чтобы протестировать несколько политик голосовой связи, необходимо создать расширенный тест для каждой политики с помощью командлета **New-ксекстендедтест** . Пользователи, которым вы назначили этот тест, должны настроить нужные политики голосовой связи. После этого Расширенные тесты передаются в командлет **New-ксватчернодеконфигуратион** с помощью команды, подобной приведенной ниже:

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Если метод New-Ксватчернодеконфигуратион вызывается без использования параметра "тесты", это означает, что для нового узла-наблюдателя будут включены только синтетические транзакции по умолчанию (и указанная расширенная виртуальная транзакция). Это означает, что узел наблюдателя будет тестировать следующие компоненты:

  - Registration

  - IM

  - GroupIM (групповые мгновенные сообщения)

  - P2PAV (одноранговые аудио- и видеосеансы)

  - AvConference (аудио- и видеоконференции)

  - Presence

  - ABS (служба адресной книги)

  - ABWQ (веб-служба адресной книги)

  - PSTN (коммутируемые звонки шлюза, заданные в виде расширенного теста. По умолчанию PSTN отключена. В этом случае проверка будет включена только в том случае, если команда включила протокол КТСОП с помощью параметра Екстендедтестс.)

Это также означает, что следующие компоненты не будут протестированы по умолчанию.

  - AVEdgeConnectivity

  - MCXP2PIM (обмен мгновенными сообщениями с помощью мобильных устройств)

  - ExumConnectivity (единая система обмена сообщениями Exchange)

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>Добавление и удаление искусственных транзакций

После настройки узла наблюдения можно использовать командлет **Set-ксватчернодеконфигуратион** , чтобы добавить или удалить из узла искусственные транзакции. Например, чтобы добавить тест PersistentChatMessage на узел-наблюдатель, используйте следующую команду с методом Add.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

При указании нескольких тестов используйте запятые. Пример:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Обратите внимание, что если один или несколько из этих тестов (например, "Конференция") уже включены на узле наблюдателя, произойдет ошибка. В этом случае вы получите следующее сообщение.

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

Если произошла эта ошибка, изменения не применяются. Команду следует повторно запустить с удаленным тестовым повторением.

Для удаления искусственной транзакции из узла-наблюдателя используйте метод Remove вместо метода Add. Например, следующая команда удаляет тест ABWQ с узла-наблюдателя.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

Вы также можете использовать метод Replace для замены всех текущих тестов на один или несколько новых тестов. Например, если вы хотите, чтобы узел наблюдателя мог выполнять тест IM, вы можете настроить его с помощью этой команды:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

При выполнении предыдущей команды все синтетические транзакции на указанном узле наблюдения будут отключены, кроме сообщений.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>Просмотр и тестирование конфигурации узла-наблюдателя

Чтобы просмотреть тесты, назначенные узлу-наблюдателю, используйте следующую команду.

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

Предыдущая команда возвращает такие сведения, в зависимости от искусственных транзакций, которые были назначены узлу.

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
> Чтобы просмотреть искусственные транзакции в алфавитном порядке, используйте следующую команду.<BR>Get-Ксватчернодеконфигуратион – Identity "atl-cs-001.litwareinc.com" | Select-Object – Експандпропертиные тесты | Sort (объект)



</div>

Чтобы убедиться в том, что узел-наблюдатель создан, введите следующую команду в командной консоли Lync Server Management Shell:

    Get-CsWatcherNodeConfiguration

Вы получите примерно такую информацию:

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Чтобы убедиться в правильности настройки узла-наблюдателя, введите в командной консоли Lync Server следующую команду:

    Test-CsWatcherNodeConfiguration

Предыдущая команда протестирует каждый узел контрольного просмотра в развертывании и сообщает сведения о том, что:

  - Была установлена обязательная роль регистратора.

  - Требуемый раздел реестра был создан при запуске Set-Ксватчернодеконфигуратион.

  - На ваших серверах работает нужная версия Lync Server.

  - Порты настроены правильно.

  - У назначенных тестовых пользователей есть необходимые учетные данные.

</div>

</div>

<span> </span>

</div>

</div>

</div>

