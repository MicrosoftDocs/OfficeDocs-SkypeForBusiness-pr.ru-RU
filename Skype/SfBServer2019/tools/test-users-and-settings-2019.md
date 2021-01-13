---
title: Настройка тестовых пользователей и параметров узла-watcher
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Настройка тестовых учетных записей пользователей и параметров узлов-watcher для искусственных транзакций Skype для бизнеса Server.
ms.openlocfilehash: 6edce666345e4691d8850e5806eedbebc98e3743
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812769"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Настройка тестовых пользователей и параметров узла-watcher
 
**Сводка:** Настройте тестовые учетные записи пользователей и параметры узлов-watcher для искусственных транзакций Skype для бизнеса Server.
  
Настроив компьютер, который будет выступать в качестве узла-наблюдателя, выполните следующие действия.
  
1. [Настройте тестовые учетные записи пользователей](test-users-and-settings-2019.md#testuser) для использования этими узлами-watcher. Если вы используете проверку подлинности согласованием, вам также необходимо выполнить командлет **Set-CsTestUserCredential**, чтобы разрешить использование этих учетных записей узлом-наблюдателем.
    
2. Обновите параметры конфигурации узла-наблюдателя.
    
## <a name="configure-test-user-accounts"></a>Настройка тестовых учетных записей пользователей
<a name="testuser"> </a>

Тестовые учетные записи не обязательно должны представлять реальных пользователей, но они должны быть действительными учетными записями Active Directory. Кроме того, эти учетные записи должны быть включены для Skype для бизнеса Server, у них должны быть действительные SIP-адреса, а также для Корпоративная голосовая связь (для использования искусственной транзакции Test-CsPstnPeerToPeerCall). 
  
Если используется метод проверки подлинности TrustedServer, необходимо убедиться, что эти учетные записи существуют, и настроить их как отмечено. Следует назначить по крайней мере трех тестовых пользователей для каждого пула, который вы хотите протестировать. Если используется метод проверки подлинности Согласование, необходимо также использовать Set-CsTestUserCredential и skype for Business Server Management Shell, чтобы эти тестовые учетные записи могли работать с искусственных транзакций. Для этого с помощью следующей команды (эти команды предполагают, что три учетные записи пользователей Active Directory созданы и что эти учетные записи включены для Skype для бизнеса Server):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

Необходимо включить не только SIP-адрес, но и имя пользователя и пароль. Если пароль не включен, Set-CsTestUserCredential запросит ввод этой информации. Имя пользователя может быть указано с помощью формата доменного имени\имени пользователя, показанного в предыдущем блоке кода.
  
Чтобы убедиться, что учетные данные тестового пользователя созданы, запустите в командной оболочке Skype для бизнеса Server указанные команды:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

Для каждого пользователя будут возвращены сведения, похожие на эти:
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Настройка базового узла-watcher с помощью искусственных транзакций по умолчанию

После создания тестовых пользователей можно создать узел-watcher с помощью команды, похожей на данной:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

Эта команда создает узел-наблюдатель с параметрами по умолчанию, который выполняет набор искусственных транзакций по умолчанию. Для нового узла-наблюдателя используются тестовые пользователи watcher1@litwareinc.com, watcher2@litwareinc.com и watcher3@litwareinc.com. Если узел-watcher использует проверку подлинности TrustedServer, тремя тестовой учетной записью могут быть любые допустимые учетные записи пользователей, включенные для Active Directory и Skype для бизнеса Server. Если узел-watcher использует метод проверки подлинности Negotiate, эти учетные записи пользователей также должны быть включены для узла-Set-CsTestUserCredential.
  
Чтобы проверить, правильно ли настроено автоматическое обнаружение целевого пула для входов, а не нацелив пул напрямую, с помощью указанных ниже действий.
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Настройка расширенных тестов

Если вы хотите включить тест PSTN, который проверяет возможность подключения к телефонной сети общего параметров, при настройке узла-watcher необходимо создать дополнительную конфигурацию. Во-первых, необходимо связать тестовых пользователей с типом теста STN, выдав команду, аналогичную этой, из командной оболочки Skype для бизнеса Server:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Результаты этой команды должны храниться в переменной. В этом примере переменная называется $pstnTest. 
  
Далее можно использовать cmdlet **New-CsWatcherNodeConfiguration,** чтобы связать тип теста (хранимый в переменной $pstnTest) с пулом Skype для бизнеса Server. Например, следующая команда создает конфигурацию узла-atl-cs-001.litwareinc.com пула, добавляет трех тестовых пользователей, созданных ранее, и добавляет тестовый тип STN:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Если вы не установили основные файлы Skype для бизнеса Server и базу данных RTCLocal на компьютере узла-watcher, команда не будет работать. 
  
Чтобы протестировать несколько политик голосовой почты, можно создать расширенный тест для каждой политики с помощью cmdlet **New-CsExtendedTest.** Предоставленные пользователи должны быть настроены с помощью нужных политик голосовой связи. Расширенные тесты передаются в cmdlet **New-CsWatcherNodeConfiguration** с помощью запятой-delimiters, например:
  
-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}
  
Так как для нового узла-смотрителя был вызван новый узел-watcher с помощью параметра Tests, для нового **узла-смотрителя** был вызван только новый синтетский транзакций по умолчанию (и указанной расширенной искусственной транзакции). Поэтому узел-watcher будет тестировать следующие компоненты:
  
- Registration
    
- "IM" (Обмен мгновенными сообщениями);
    
- GroupIM
    
- P2PAV (одноранговые аудио- и видеосеансы)
    
- AvConference (аудио- и видеоконференции)
    
- Присутствие
    
- ABS (служба адресной книги)
    
- ABWQ (веб-служба адресной книги)
    
Следующие компоненты не будут тестироваться по умолчанию:
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (единая система обмена сообщениями Exchange)
    
- JoinLauncher
    
- MCXP2PIM (обмен мгновенными сообщениями с устаревших мобильных устройств)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (вызовы шлюза STN, указанные в качестве расширенного теста)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>Добавление и удаление искусственных транзакций

После настройки узла-наблюдателя вы можете добавлять искусственные транзакции на узел-наблюдатель или удалять их с узла-наблюдателя с помощью командлета Set-CsWatcherNodeConfiguration. Например, чтобы добавить тест PersistentChatMessage на узел-наблюдатель, используйте следующую команду с методом Add.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

При указании нескольких тестов используйте запятые. Пример:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

Ошибка возникает, если один или несколько из этих тестов (например, DataConference) уже включены на узле-watcher. В этом случае вы получите следующее сообщение.
  
Set-CsWatcherNodeConfiguration: существует повторяемая последовательность ключей "DataConference" для ключа "urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName" или уникальное ограничение удостоверения.
  
Если произошла эта ошибка, изменения не применяются. Команду следует повторно выполнить с удалением дубликата теста.
  
Чтобы удалить искусственную транзакцию из узла-watcher, используйте метод Remove. Например, следующая команда удаляет тест ABWQ с узла-наблюдателя.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Вы можете использовать метод Replace, чтобы заменить все тесты, включенные в текущий момент, на один или несколько новых тестов. Например, если вы хотите, чтобы узел-watcher только запускал тест im, вы можете настроить его с помощью этой команды:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

При запуске этой команды все искусственные транзакции на указанном узле-просмотре будут отключены, кроме мгновенных сообщений.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Просмотр и тестирование конфигурации узла-наблюдателя

Чтобы просмотреть тесты, назначенные узлу-наблюдателю, используйте следующую команду.
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Эта команда возвращает сведения, похожие на эти, в зависимости от искусственных транзакций, которые были назначены узлу:
  
Регистрация IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference
> [!TIP]
> Чтобы просмотреть искусственные транзакции в алфавитном порядке, используйте следующую команду. 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Чтобы убедиться, что узел-watcher создан, введите следующую команду в командной оболочке Skype для бизнеса Server:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Вы получите сведения, похожие на эти:
  
Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...} ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN Test; Te...} TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Эта команда будет тестировать каждый узел-watcher в развертывании и подтверждать, выполнены ли следующие действия:
  
- Установлена необходимая роль регистратора
    
- Создается необходимый ключ реестра (завершится при Set-CsWatcherNodeConfiguration управления)
    
- На серверах работает правильная версия Skype для бизнеса Server
    
- Порты настроены правильно
    
- Назначенная тестовая учетная возможность пользователей имеет необходимые учетные данные
    
## <a name="managing-watcher-nodes"></a>Управление узлами-наблюдателями
<a name="testuser"> </a>

Помимо изменения искусственных транзакций, которые выполняются на узле-watcher,  можно также использовать для выполнения двух других важных задач: включение и отключение узла-watcher, а также настройку узла-watcher для использования внутренних или внешних ВЕБ-URL-адресов при выполнении тестов.
  
По умолчанию узлы-наблюдатели периодически запускают все включенные искусственные транзакции. Однако иногда может потребоваться приостановить эти транзакции. Например, если узел-наблюдатель временно отключился от сети, у него больше нет причин запускать искусственные транзакции. Без сетевого подключения эти транзакции не будут работать. Чтобы временно отключить узел-watcher, в командной оболочке Skype для бизнеса Server запустите команду, аналогичную этой:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Эта команда отключит выполнение искусственных транзакций на узле-001.litwareinc.com. Чтобы возобновить выполнение искусственных транзакций, снова задайте для свойства Enabled значение True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Свойство Enabled может использоваться для включения или отключения узлов-наблюдателей. Если нет необходимости временно удалять узел-наблюдатель, используйте командлет **Remove-CsWatcherNodeConfiguration**:
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Эта команда удаляет все параметры конфигурации узла-watcher с указанного компьютера, что не позволяет компьютеру автоматически запускать искусственные транзакции. Однако команда не будет удалить файлы агента System Center или системные файлы Skype для бизнеса Server.
  
По умолчанию узлы-пользователи-watcher используют внешние ВЕБ-URL-адреса организации при проведении тестов. Однако узлы-пользователи-watcher также могут быть настроены для использования внутренних URL-адресов веб-сайтов организации. Это позволит администраторам проверить доступ к URL-адресам тех пользователей, которые находятся внутри сети периметра. Чтобы настроить узел-watcher на использование внутренних URL-адресов вместо внешних URL-адресов, установите для свойства UseInternalWebURls $True:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

Сброс этого свойства до значения по умолчанию False ($False) приведет к повторному использованию внешними URL-адресами для watcher:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Специальные инструкции по установке для искусственных транзакций
<a name="special_synthetictrans"> </a>

Большинство искусственных транзакций могут запускаться на узле-watcher как есть. В большинстве случаев, как только искусственная транзакция добавляется в параметры конфигурации узла-watcher, узел-watcher может начать использовать эту искусственную транзакцию во время тестирования. Однако некоторые искусственные транзакции требуют специальных инструкций по настройке, как было рассмотрено в следующих разделах.
  
### <a name="data-conferencing-synthetic-transaction"></a>Искусственная транзакция для видеоконференций

Если компьютер узла-watcher находится за пределами сети периметра, возможно, вы не сможете запустить искусственную транзакцию для передачи данных, если только не отключите параметры прокси-сервера браузера Windows Internet Explorer® для учетной записи сетевой службы, выполив следующие действия:
  
1. На компьютере узла-watcher нажмите кнопку "Начните", щелкните "Все программы", выберите "Программы доступа", щелкните правой кнопкой мыши командную подсказку **и** выберите команду "Запуск от прав **администратора".**   
    
2. В окне консоли введите следующую команду и нажмите ввод. 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

В командном окне отобразилось следующее сообщение:
  
BITSAdmin является неподдергодным и не гарантируется, что будет доступен в будущих версиях Windows. Средства администрирования для службы BITS теперь предоставляются с помощью bitS PowerShell.
  
Параметры прокси-сервера Интернета для учетной записи NetworkService NO_PROXY. 
  
(подключение = по умолчанию)
  
Это сообщение означает, что вы отключили параметры прокси-сервера Internet Explorer для учетной записи сетевой службы.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Искусственная транзакция единой системы обмена сообщениями Exchange

Искусственная транзакция единой системы обмена сообщениями Exchange проверяет, могут ли тестовые пользователи подключаться к учетным записям голосовой почты, которые есть в Exchange.
  
Тестовые пользователи должны быть предварительно сконфигурированы с помощью учетных записей голосовой почты. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Искусственная транзакция сохраняемой беседы

Чтобы использовать искусственную транзакцию сохраняемого чата, необходимо сначала создать канал и предоставить тест-пользователям разрешения на его использование.
  
Для настройки этого канала можно использовать искусственную транзакцию Persistent Chat: 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Эту задачу установки необходимо запустить внутри предприятия:
  
- При запуске с компьютера, не относящавшегося к серверу, пользователь, выполнивший этот запуск, должен быть членом роли CsPersistentChatAdministrators для Role-Based Access Control (RBAC).
    
- При запуске с самого сервера пользователь, выполнивший этот запуск, должен быть членом группы RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Искусственная транзакция одноранговых вызовов STN

Искусственная транзакция Test-CsPstnPeerToPeerCall возможность совершения и получения вызовов через телефонную сеть общего звонков (STN).
  
Чтобы запустить эту искусственную транзакцию, необходимо настроить:
  
- Два тестовых пользователя с включенной поддержкой UC (вызываемая и приемная).
    
- Прямые входные номера для каждой учетной записи пользователя.
    
- Политики VoIP и маршруты голосовой почты, которые позволяют звонкам на номер приемник достичь шлюза STN.
    
- Шлюз STN, который принимает вызовы и мультимедиа, которые будут маршрутизовы обратно в домашний пул приемник, в зависимости от набраного номера.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Искусственная транзакция единого магазина контактов

Искусственная транзакция единого магазина контактов проверяет возможность Skype для бизнеса Server получать контакты от имени пользователя из Exchange.
  
Чтобы использовать эту искусственную транзакцию, следует выполнить следующие условия:
  
- Lyss-Exchange необходимо настроить проверку подлинности между серверами.
    
- У тестовых пользователей должен быть действительный почтовый ящик Exchange.
    
После этого можно выполнить следующий Windows PowerShell для переноса списков контактов тестовых пользователей в Exchange:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Миграция тестовых списков контактов пользователей в Exchange может занять некоторое время. Для отслеживания хода миграции можно запустить ту же командную строку без флага -Setup:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Эта командная строка завершится успешно после завершения миграции.
  
### <a name="xmpp-synthetic-transaction"></a>Искусственная транзакция XMPP

Искусственная транзакция обмена мгновенными сообщениями XMPP требует настройки функции XMPP с одним или более федерационными доменами.
  
Чтобы включить искусственную транзакцию XMPP, необходимо предоставить параметр XmppTestReceiverMailAddress с учетной записью пользователя в домене XMPP с маршрутией. Например:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

В этом примере потребуется правило Skype для бизнеса Server, чтобы отправлять сообщения для litwareinc.com на шлюз XMPP.

> [!NOTE]
> Шлюзы и прокси-серверы XMPP были доступны в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019. Дополнительные сведения см. в переносе [федерации XMPP.](../migration/migrating-xmpp-federation.md)
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Искусственная транзакция сервера видеосвязи (VIS)

Искусственная транзакция сервера видеосвязи (VIS) требует загрузки и установки файлов поддержки искусственных транзакций[ (VISSTSupportPackage.msi). ](https://www.microsoft.com/download/details.aspx?id=46921) 
  
Чтобы установить VISSTSupportPackage.msi убедитесь, что зависимости (в соответствии с требованиями к системе) для MSI уже установлены. Запустите VISSTSupportPackage.msi, чтобы выполнить простую установку. MSI устанавливает все файлы по следующему пути: "%ProgramFiles%\VIS Synthetic Transaction Support Package".
  
Дополнительные сведения о запуске искусственной транзакции VIS см. в документации по [cmdlet Test-CsP2PVideoInteropServerSipTrunkAV.](https://technet.microsoft.com/library/dn985894.aspx)
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Изменение частоты запуска искусственных транзакций
<a name="special_synthetictrans"> </a>

По умолчанию искусственные транзакции будут запускаться с настроенными пользователями каждые 15 минут. Искусственные транзакции последовательно запускаются в наборе пользователей, чтобы избежать конфликта двух искусственных транзакций друг с другом. Для выполнения всех искусственных транзакций требуется более длительный интервал.
  
Если требуется чаще запускать искусственные транзакции, число искусственных транзакций, запускаемых с заданным набором пользователей, должно быть уменьшено, чтобы тесты могли завершиться в нужном диапазоне времени с некоторым буфером для периодических сетевых задержек. Если необходимо выполнить дополнительные искусственные транзакции, создайте дополнительные наборы пользователей для запуска дополнительных искусственных транзакций.
  
Чтобы изменить частоту запуска искусственных транзакций, выполните следующие действия.
  
1. Откройте System Center Operations Manager. Щелкните раздел "Автор". Раздел "Правила нажатия" (в разделе "Авторинг")
    
2. В разделе "Правила" найдите правило с именем "Main Synthetic Transaction Runner Performance Collection Rule"
    
3. Щелкните правило правой кнопкой мыши и выберите "Переопределения", выберите "Переопредить правило", а затем выберите "Для всех объектов класса: просмотр пула"
    
4. В окне "Переопределения свойств" выберите имя параметра "Частота" и задав нужное значение переопределения.
    
5. В том же окне выберите пакет управления, к которому необходимо применить это переопределения
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Использование подробного журнала для искусственных транзакций
<a name="special_synthetictrans"> </a>

Искусственные транзакции очень полезны для выявления проблем в системе. Например, Test-CsRegistration может оповещать администраторов о том, что пользователи с трудом регистрируются в Skype для бизнеса Server. Однако для определения фактической причины сбоя могут потребоваться дополнительные сведения.
  
По этой причине искусственные транзакции предоставляют богатый объем ведения журнала. В результате ведения журнала для каждого действия, которое осуществляется искусственной транзакцией, записываются следующие сведения:
  
- Время начала действия.
    
- Время завершения действия.
    
- Выполненное действие (например, создание, присоединение или выход из конференции, вход в Skype для бизнеса Server; отправка мгновенного сообщения).
    
- Информационные, подробные сообщения, предупреждения или сообщения об ошибках, которые были созданы при выполнении операции
    
- Сообщения о регистрации SIP.
    
- Записи исключений или коды диагностики, созданные при окнаности действия.
    
- Net result of running the activity.
    
Эти сведения создаются автоматически при каждом запуске искусственной транзакции, но не отображаются автоматически или не сохраняются в файле журнала. Если искусственная транзакция запущена вручную, можно использовать параметр OutLoggerVariable, чтобы указать переменную Windows PowerShell, в которой будут храниться сведения. Здесь можно использовать один из двух методов сохранения и/или просмотра сообщений об ошибках в формате XML или HTML. 
  
Чтобы получить сведения об устранении неполадок, укажите параметр OutLoggerVariable, а затем выберите имя переменной:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> : не преисоставить имя переменной с помощью символа $. Используйте имя переменной, например RegistrationTest (не $RegistrationTest). 
  
При запуске этой команды вы увидите выходные данные, аналогичные:
  
Целевое Fqdn : atl-cs-001.litwareinc.com result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates. Диагностика: вы можете получить доступ к гораздо более подробным сведениям об этом сбое, чем к показанным здесь сообщениям об ошибке. Чтобы получить доступ к этим сведениям в формате HTML, используйте команду, аналогичную этой, чтобы сохранить данные, хранимые в переменной RegistrationTest, в HTML-файл:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Можно также использовать метод ToXML() для сохранения данных в файл XML:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Эти файлы можно просмотреть с помощью Windows Internet Explorer, Microsoft Visual Studio или любого другого приложения, способного открывать HTML-или XML-файлы.
  
Искусственные транзакции, которые запускаются внутри System Center Operations Manager, автоматически создают эти файлы журналов для сбоев. Эти журналы не будут созданы, если выполнение не удастся, прежде чем Skype для бизнеса Server PowerShell сможет загрузить и запустить искусственную транзакцию. 
  
> [!IMPORTANT]
> По умолчанию Skype для бизнеса Server сохраняет файлы журналов в папку, доступ к которая не является общей. Чтобы сделать эти журналы доступными, необходимо поделиться этой папкой. Например: \\ atl-watcher-001.litwareinc.com\WatcherNode. 
