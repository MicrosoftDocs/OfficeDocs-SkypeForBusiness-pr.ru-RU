---
title: 'Lync Server 2013: специальные инструкции по настройке для искусственных транзакций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c92786b50bc0b29fe5bc7f6b5b8ac978a17085aa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Специальные инструкции по настройке для искусственных транзакций в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2015-11-16_

Большинство искусственных транзакций может работать на узле-наблюдателе без изменений. То есть, как только искусственная транзакция добавляется в параметры конфигурации узла-наблюдателя, узел-наблюдатель может начать использовать эту искусственную транзакцию во время тестовых проходов. Однако это не относится ко всем искусственным транзакциям. Исключением являются искусственные транзакции, которые нуждаются в специальных инструкциях. Такие транзакции обсуждаются в следующих разделах.

<div>

## <a name="dealing-with-server-timeout-errors"></a>Работа с ошибками времени ожидания сервера

В некоторых случаях может возникнуть сбой искусственных транзакций с ошибками времени ожидания сервера (код ошибки 504). Эти ошибки обычно возникают из-за проблем с брандмауэром. При выполнении искусственной транзакции эта транзакция выполняется в процессе Мониторингхост. exe; в свою очередь, Мониторингхост. exe запускает экземпляр процесса PowerShell. exe. Если брандмауэр блокирует Мониторингхост. exe или PowerShell. exe, искусственная транзакция завершится ошибкой, и будет выдаваться сообщение об ошибке 504.

Чтобы устранить эту проблему, необходимо вручную создать правила брандмауэра для входящих подключений для Мониторингхост. exe и PowerShell. exe на локальном компьютере. Это можно сделать с помощью брандмауэра Windows или стороннего локального брандмауэра в зависимости от имеющейся конфигурации сервера.

Если вы используете устройство сетевого брандмауэра между виртуальным компьютером искусственной транзакции и серверами Lync, которые вы пытаетесь отслеживать, вы должны считать его клиентским компьютером, а все требования к портам [и протоколам брандмауэра для внутренних серверов в Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>Искусственные транзакции в конференц-связи с передачей данных

Если компьютер узла-наблюдателя находится вне сети периметра, то, возможно, не удастся запустить искусственную транзакцию конференц-связи с данными, пока не будет сначала отключен параметр прокси-сервера Internet Explorer для учетной записи сетевой службы. Чтобы отключить параметры прокси-сервера для этой службы, выполните следующую процедуру:

1.  На компьютере узла-наблюдателя в меню **Пуск** щелкните **Все программы**, выберите **Стандартные**, щелкните правой кнопкой мыши **Командная строка**, а затем выберите команду **Запуск от имени администратора**.

2.  В окне консоли введите следующую команду и нажмите клавишу ВВОД:
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

В окне командной строки отобразится следующее сообщение:

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Это сообщение означает, что вы отключили параметры прокси-сервера Internet Explorer для учетной записи сетевой службы.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Искусственные транзакции единой системы обмена сообщениями Exchange

Искусственная транзакция единой системы обмена сообщениями Exchange удостоверяется в том, что тестовые пользователи могут подключаться к учетным записям голосовой почты, размещенным в Exchange. Для этих тестовых пользователей должны быть предварительно настроены учетные записи голосовой почты, прежде чем можно будет применять тесты единой системы обмена сообщениями Exchange.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>Искусственные транзакции сохраняемого чата

Чтобы использовать искусственную транзакцию сохраняемого чата, администраторы должны сначала создать канал и предоставить тестовым пользователям разрешения на его использование. Для правильной настройки этих тестовых пользователей можно использовать командлет [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) :

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Эта задача настройки должна быть запущена изнутри предприятия:

  - Если запустить ее с компьютера, не являющегося сервером, пользователь, запустивший командлет должен являться членом роли PersistentChatAdministrators в соответствии с управлением доступом на основе ролей.

  - Если запустить непосредственно с самого сервера, пользователь, запустивший командлет, должен являться членом группы RTCUniversalServerAdmins.

В предыдущей команде параметр Setup был включен и задан как True ($True). Если вы включаете параметр Setup, Test-CsPersistentChatMessage создаст специальную комнату сохраняемого чата и заполнит эту комнату тестовыми пользователями. Это обеспечит доступность комнаты чата для тестирования. Обратите внимание, что параметр Setup должен выполняться только с сервера переднего плана.

Комната чата, созданная командлетом Test-CsPersistentChatMessage, может быть удалена администратором.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>Искусственные транзакции одноранговых вызовов ТСОП

Искусственная транзакция [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) проверяет возможность помещать и принимать вызовы через телефонную сеть общего пользования (PSTN).

Чтобы запустить искусственную транзакцию, администраторы должны настроить следующие элементы:

  - Два тестовых пользователя (вызывающий абонент и получатель), включенные для корпоративной голосовой связи.

  - Прямые входные номера для каждой учетной записи пользователя.

  - Политики голосовой связи и маршруты голосовой связи, которые позволяют получать вызовам уходить на шлюз ТСОП.

  - Шлюз ТСОП, который принимает вызовы и среда обратных вызовов в домашний пул получателя в зависимости от набранного номера.

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>Искусственные транзакции единой системы обмена сообщениями

Искусственная транзакция в едином хранилище контактов проверяет, что Lync Server 2013 может получить контакты от имени пользователя из Microsoft Exchange Server 2013.

Чтобы использовать эту искусственную транзакцию, следует выполнить следующие условия:

  - [Управление проверкой подлинности между серверами (OAuth) и партнерским приложениями в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) необходимо настроить между Lync Server 2013 и Exchange 2013.

  - Тестовые пользователи должны иметь действительный почтовый ящик Exchange 2013.

После выполнения этих требований администраторы могут запустить следующую команду для проверки возможности получения пользователем с SIP-адресом kenmyer@litwareinc.com своих контактов из единого хранилища контактов:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Обратите внимание на использование параметра Setup в предыдущей команде. Если параметр Setup включен при выполнении Test-CsUnifiedContactStore, то контакты указанного пользователя (в нашем случае sip:kenmyer@litwareinc.com) будут перемещены в единое хранилище контактов. (Конечно, если контакты пользователя уже находятся в едином хранилище контактов, их не нужно перемещать). Параметр Setup обычно используется только один раз (при первом запуске test-CsUnifiedContactStore), и его следует использовать только с тестовыми пользователями; то есть учетные записи пользователей, которые никогда не будут входить в систему на Lync Server. После миграции тестового пользователя в единое хранилище контактов можно проверить возможность получения контактов пользователя, вызвав командлет Test-CsUnifiedContactStore без параметра Setup:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>Искусственные транзакции XMPP

Искусственная транзакция мгновенных сообщений XMPP нуждается в настройке компонента XMPP с указанием одного или нескольких федеративных доменов.

Чтобы включить искусственную транзакцию XMPP, необходимо предоставить параметр XmppTestReceiverMailAddress, используя учетную запись пользователя в домене XMPP с поддержкой маршрутизации. Пример:

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

В этом примере для маршрутизации сообщений litwareinc.com на шлюз XMPP необходимо наличие правила Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

