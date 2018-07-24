---
title: Настройка тестовых пользователей узла-наблюдателя и параметров
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Сводка: Настройка тестовых учетных записей пользователей и параметры узла наблюдателя для Скайп для искусственных транзакций Business Server.'
ms.openlocfilehash: 3881fc1878ed3b248aa3109b79a3e384ec4a5fb7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989890"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="be510-103">Настройка тестовых пользователей узла-наблюдателя и параметров</span><span class="sxs-lookup"><span data-stu-id="be510-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="be510-104">**Сводка:** Настройка тестовых учетных записей пользователей и параметры узла наблюдателя для Скайп для искусственных транзакций Business Server.</span><span class="sxs-lookup"><span data-stu-id="be510-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="be510-105">Настроив компьютер, который будет выступать в качестве узла-наблюдателя, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="be510-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="be510-106">[Настройка тестовых учетных записей пользователей](test-users-and-settings.md#testuser) для использования этих узлах.</span><span class="sxs-lookup"><span data-stu-id="be510-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="be510-107">Если вы используете проверку подлинности согласованием, вам также необходимо выполнить командлет **Set-CsTestUserCredential**, чтобы разрешить использование этих учетных записей узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="be510-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="be510-108">Обновите параметры конфигурации узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="be510-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="be510-109">Настройка тестовых учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="be510-109">Configure Test User Accounts</span></span>
<span data-ttu-id="be510-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="be510-110"></span></span>

<span data-ttu-id="be510-111">Тестовые учетные записи не требуется представляют фактические людей, но они должны иметь допустимые учетные записи Active Directory.</span><span class="sxs-lookup"><span data-stu-id="be510-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="be510-112">Кроме того эти учетные записи должна быть включена поддержка Скайп для Business Server, они должны иметь допустимые адреса SIP и их необходимо включить для корпоративной голосовой связи (для использования искусственная транзакция Test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="be510-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="be510-113">При использовании метода проверки подлинности TrustedServer все, что вам нужно сделать — убедитесь в том, что эти учетные записи существует и настроить их как было указано.</span><span class="sxs-lookup"><span data-stu-id="be510-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="be510-114">Вы должны назначить по крайней мере три тестовых пользователей для каждого пула, который требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="be510-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="be510-115">При использовании метода проверки подлинности Negotiate, необходимо также использовать командлет Set-CsTestUserCredential и Скайп для Business Server командную консоль, чтобы включить их тестирование учетных записей для работы с искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="be510-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="be510-116">Это можно сделать с помощью команды, подобные приведенным ниже (эти команды предполагается, что были созданы три учетные записи пользователей Active Directory и включения этих учетных записей для Скайп для Business Server):</span><span class="sxs-lookup"><span data-stu-id="be510-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="be510-p104">Помимо SIP-адреса вам нужно также указать имя пользователя и пароль. Если вы не укажете пароль, командлет Set-CsTestUserCredential выведет соответствующий запрос. Имя пользователя можно указывать в формате "имя_домена\имя_пользователя", как показано выше.</span><span class="sxs-lookup"><span data-stu-id="be510-p104">You must include not only the SIP address, but also the user name and password. If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information. The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="be510-120">Чтобы убедиться в том, что были созданы учетных данных тестовых пользователей, выполните следующие команды Скайп для консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="be510-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="be510-121">Команды возвращают сведения о каждом пользователе, похожие на следующие.</span><span class="sxs-lookup"><span data-stu-id="be510-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="be510-122">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="be510-122">**UserName**</span></span>|<span data-ttu-id="be510-123">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="be510-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="be510-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="be510-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="be510-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="be510-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="be510-126">Настройка базового узла-наблюдателя, использующего искусственные транзакции по умолчанию</span><span class="sxs-lookup"><span data-stu-id="be510-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="be510-127">Создав тестовых пользователей, вы можете создать узел-наблюдатель с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="be510-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="be510-p105">Эта команда создает узел-наблюдатель с параметрами по умолчанию, который выполняет набор искусственных транзакций по умолчанию. Для нового узла-наблюдателя используются тестовые пользователи watcher1@litwareinc.com, watcher2@litwareinc.com и watcher3@litwareinc.com. Если узел-наблюдатель использует проверку подлинности TrustedServer, тестовые учетные записи могут представлять собой любые допустимые учетные записи, для которых включена поддержка Active Directory и Skype для бизнеса Server. Если узел-наблюдатель использует проверку подлинности согласованием, использование этих учетных записей пользователей также должно быть включено для узла-наблюдателя с помощью командлета Set-CsTestUserCredential.</span><span class="sxs-lookup"><span data-stu-id="be510-p105">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions. The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com. If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server. If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="be510-132">Чтобы проверить правильность настройки автоматического обнаружения целевого пула для входа в систему вместо непосредственного определения пула, используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="be510-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="be510-133">Настройка расширенных тестов</span><span class="sxs-lookup"><span data-stu-id="be510-133">Configuring Extended Tests</span></span>

<span data-ttu-id="be510-p106">Если вы хотите включить тест ТСОП, проверяющий подключение к телефонной сети общего пользования, вам потребуется произвести дополнительную настройку узла-наблюдателя. Во-первых, вам нужно связать тестовых пользователей с типом теста ТСОП, выполнив следующую команду командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="be510-p106">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node. First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="be510-p107">Результаты выполнения этой команды необходимо сохранить в переменной. В этом примере используется переменная $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="be510-p107">The results of this command must be stored in a variable. In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="be510-138">Теперь можно использовать командлет **New-CsWatcherNodeConfiguration** связывание тип теста (и сохраненная в переменной $pstnTest) для Скайп для пула Business Server.</span><span class="sxs-lookup"><span data-stu-id="be510-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="be510-139">Например, следующая команда создает конфигурацию узла-наблюдателя для пула atl-cs-001.litwareinc.com, добавляет трех тестовых пользователей, созданных ранее, а также тест ТСОП.</span><span class="sxs-lookup"><span data-stu-id="be510-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="be510-140">Если вы не установили основные файлы Skype для бизнеса Server и базу данных RTCLocal на компьютере узла-наблюдателя, то предыдущая команда завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="be510-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="be510-p109">Чтобы протестировать несколько политик голосовой связи, вам нужно создать расширенный тест для каждой политики с помощью командлета **New-CsExtendedTest**. Для пользователей, назначенных этому тесту, следует настроить требуемые политики голосовой связи. После этого передайте расширенные тесты в командлет **New-CsWatcherNodeConfiguration** с помощью следующих команды с разделителями запятыми.</span><span class="sxs-lookup"><span data-stu-id="be510-p109">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet. The users provided should be configured with the desired voice policies. The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="be510-144">-ExtendedTests @{добавьте = $pstnTest1, $pstnTest2, $pstnTest3}</span><span class="sxs-lookup"><span data-stu-id="be510-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="be510-p110">Так как командлет **New-CsWatcherNodeConfiguration** был вызван без параметра Tests, то для нового узла-наблюдателя будут включены только искусственные транзакции по умолчанию и указанные расширенные искусственные транзакции. Это означает, что узел-наблюдатель будет тестировать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="be510-p110">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node. Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="be510-147">Registration</span><span class="sxs-lookup"><span data-stu-id="be510-147">Registration</span></span>
    
- <span data-ttu-id="be510-148">IM</span><span class="sxs-lookup"><span data-stu-id="be510-148">IM</span></span>
    
- <span data-ttu-id="be510-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="be510-149">GroupIM</span></span>
    
- <span data-ttu-id="be510-150">P2PAV (одноранговые аудио- и видеосеансы)</span><span class="sxs-lookup"><span data-stu-id="be510-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="be510-151">AvConference (аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="be510-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="be510-152">Presence</span><span class="sxs-lookup"><span data-stu-id="be510-152">Presence</span></span>
    
- <span data-ttu-id="be510-153">ABS (служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="be510-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="be510-154">ABWQ (веб-служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="be510-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="be510-155">Следующие компоненты не будут тестироваться по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="be510-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="be510-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="be510-156">ASConference</span></span>
    
- <span data-ttu-id="be510-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="be510-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="be510-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="be510-158">DataConference</span></span>
    
- <span data-ttu-id="be510-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="be510-159">DialinConferencing</span></span>
    
- <span data-ttu-id="be510-160">ExumConnectivity (единая система обмена сообщениями Exchange)</span><span class="sxs-lookup"><span data-stu-id="be510-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="be510-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="be510-161">JoinLauncher</span></span>
    
- <span data-ttu-id="be510-162">MCXP2PIM (мобильных устройств обмен мгновенными сообщениями)</span><span class="sxs-lookup"><span data-stu-id="be510-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="be510-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="be510-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="be510-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="be510-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="be510-165">ТСОП (вызовы шлюза ТСОП, указанные как расширенный тест)</span><span class="sxs-lookup"><span data-stu-id="be510-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="be510-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="be510-166">UcwaConference</span></span>
    
- <span data-ttu-id="be510-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="be510-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="be510-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="be510-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="be510-169">Добавление и удаление искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="be510-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="be510-p111">После настройки узла-наблюдателя вы можете добавлять искусственные транзакции на узел-наблюдатель или удалять их с узла-наблюдателя с помощью командлета Set-CsWatcherNodeConfiguration. Например, чтобы добавить тест PersistentChatMessage на узел-наблюдатель, используйте следующую команду с методом Add.</span><span class="sxs-lookup"><span data-stu-id="be510-p111">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node. For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="be510-p112">При указании нескольких тестов используйте запятые. Пример:</span><span class="sxs-lookup"><span data-stu-id="be510-p112">Multiple tests can be added by separating the test names by using commas. For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="be510-p113">Если один или несколько этих тестов (например, DataConference) уже были включены на узле-наблюдателе, произойдет ошибка. В этом случае вы получите следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="be510-p113">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node. In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="be510-176">Set-CsWatcherNodeConfiguration : Существует повторяющаяся последовательность ключей 'DataConference' для ключа 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' или ограничение по уникальному идентификатору.</span><span class="sxs-lookup"><span data-stu-id="be510-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="be510-177">Если произошла эта ошибка, изменения не применяются.</span><span class="sxs-lookup"><span data-stu-id="be510-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="be510-178">Команду следует выполнить повторно, удалив повторяющийся тест.</span><span class="sxs-lookup"><span data-stu-id="be510-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="be510-p115">Чтобы удалить искусственную транзакцию с узла-наблюдателя, используйте метод Remove. Например, следующая команда удаляет тест ABWQ с узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="be510-p115">To remove a synthetic transaction from a watcher node, use the Remove method. For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="be510-p116">С помощью метода Replace вы можете заменить все тесты, включенные в настоящий момент, на один или несколько новых тестов. Например, если вы хотите, чтобы узел-наблюдатель только выполнял тест IM, вы можете использовать следующую команду.</span><span class="sxs-lookup"><span data-stu-id="be510-p116">You can use the Replace method to replace all the currently-enabled tests with one or more new tests. For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="be510-183">При выполнении этой команды на указанном узле-наблюдателе отключаются все искусственные транзакции, кроме IM.</span><span class="sxs-lookup"><span data-stu-id="be510-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="be510-184">Просмотр и тестирование конфигурации узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="be510-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="be510-185">Чтобы просмотреть тесты, назначенные узлу-наблюдателю, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="be510-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="be510-186">Данная команда возвращает сведения, схожие со следующими (с учетом искусственных транзакций, назначенных узлу).</span><span class="sxs-lookup"><span data-stu-id="be510-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="be510-187">Регистрация обмена мгновенными Сообщениями GroupIM P2PAV AvConference сведения о присутствии PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="be510-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="be510-188">Чтобы просмотреть искусственные транзакции в алфавитном порядке, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="be510-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="be510-189">Чтобы проверить, был ли создан узел-наблюдатель, введите в командную консоль Skype для бизнеса Server следующую команду.</span><span class="sxs-lookup"><span data-stu-id="be510-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="be510-190">Команда возвращает сведения, похожие на следующие.</span><span class="sxs-lookup"><span data-stu-id="be510-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="be510-191">Удостоверение: atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="be510-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="be510-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span><span class="sxs-lookup"><span data-stu-id="be510-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="be510-193">TargetFqdn: atl-cs-001.litwareinc.com PortNumber: 5061To убедитесь, что компьютер узла-наблюдателя настроен правильно, введите следующую команду из Скайп для консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="be510-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="be510-194">Данная команда проверяет каждый узел-наблюдатель в развертывании и подтверждает выполнение следующих действий:</span><span class="sxs-lookup"><span data-stu-id="be510-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="be510-195">установлена ли требуемая роль Регистратора;</span><span class="sxs-lookup"><span data-stu-id="be510-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="be510-196">созданы ли требуемые разделы реестра (выполняется при запуске команды Set-CsWatcherNodeConfiguration);</span><span class="sxs-lookup"><span data-stu-id="be510-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="be510-197">запущена ли на серверах требуемая версия Skype для бизнеса Server;</span><span class="sxs-lookup"><span data-stu-id="be510-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="be510-198">правильно ли настроены порты;</span><span class="sxs-lookup"><span data-stu-id="be510-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="be510-199">имеются ли у назначенных тестовых пользователей требуемые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="be510-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="be510-200">Управление узлами-наблюдателями</span><span class="sxs-lookup"><span data-stu-id="be510-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="be510-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="be510-201"></span></span>

<span data-ttu-id="be510-202">В дополнение к изменению искусственных транзакций, выполняемых на узле-наблюдателе, вы можете также использовать командлет **Set-CsWatcherNodeConfiguration** для выполнения двух других важных задач: включение/отключение узла-наблюдателя и настройка узла-наблюдателя для использования внутренних URL-адресов или внешних URL-адресов при проведении тестирования.</span><span class="sxs-lookup"><span data-stu-id="be510-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="be510-p118">По умолчанию узлы-наблюдатели периодически запускают все включенные искусственные транзакции. Однако иногда может потребоваться приостановка выполнения транзакций. Например, если узел-наблюдатель временно отключился от сети, у него больше нет причин запускать искусственные транзакции. Без сетевого подключения эти транзакции завершатся со сбоем. Для временного отключения узла-наблюдателя выполните команду, идентичную команде из командной консоли Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="be510-p118">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions. At times, however, you may want to suspend those transactions. For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions. Without network connectivity, those transactions will fail. To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="be510-p119">Эта команда приведет к отключению выполнения искусственных транзакций на узле-наблюдателе atl watcher 001.litwareinc.com. Чтобы возобновить выполнение искусственных транзакций, снова задайте для свойства Enabled значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="be510-p119">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="be510-p120">Свойство Enabled может использоваться для включения или отключения узлов-наблюдателей. Если нет необходимости временно удалять узел-наблюдатель, используйте командлет **Remove-CsWatcherNodeConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="be510-p120">The Enabled property can be used to turn watcher nodes on or off. If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="be510-212">Эта команда удаляет с указанного компьютера все параметры конфигурации узла-наблюдателя, что препятствует автоматическому запуску на этом компьютере искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="be510-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="be510-213">Тем не менее, команда не приводит к удалению Скайп для Business Server системные файлы или файлы агента System Center.</span><span class="sxs-lookup"><span data-stu-id="be510-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="be510-p122">По умолчанию узлы-наблюдатели используют при проведении тестов внешние URL-адреса. Однако узлы-наблюдатели можно настроить для использования внутренних URL-адресов организации. Это позволит администраторам проверить доступ к URL-адресам тех пользователей, которые находятся внутри сети периметра. Чтобы настроить узел-наблюдатель для использования внутренних URL-адресов вместо внешних URL-адресов, задайте для свойства UseInternalWebURls значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="be510-p122">By default, watcher nodes use an organization's external Web URLs when conducting tests. However, watcher nodes can also be configured to use the organization's internal Web URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="be510-218">Сброс этого свойства до значения по умолчанию False ($False) приведет к повторному использованию наблюдателем внешних URL-адресов:</span><span class="sxs-lookup"><span data-stu-id="be510-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="be510-219">Специальные инструкции по установке для искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="be510-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="be510-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="be510-220"></span></span>

<span data-ttu-id="be510-p123">Большинство искусственных транзакций может работать на узле-наблюдателе без изменений. То есть, как только искусственная транзакция добавляется в параметры конфигурации узла-наблюдателя, узел-наблюдатель может начать использовать эту искусственную транзакцию во время тестовых проходов. Однако существуют некоторые искусственные транзакции, которые нуждаются в специальных инструкциях. Такие транзакции обсуждаются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="be510-p123">Most synthetic transactions can run on a watcher node as-is. In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes. However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="be510-224">Искусственная транзакция в конференц-связи с передачей данных</span><span class="sxs-lookup"><span data-stu-id="be510-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="be510-225">Если компьютер узла-наблюдателя расположен за пределами сетевого периметра, скорее всего, невозможно будет запускать искусственные транзакции конференц-связи с передачей данных, если только не отключить сначала параметры прокси-сервера в интернет-браузере Windows Internet Explorer® для учетной записи сетевой службы, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="be510-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="be510-226">На компьютере узла-наблюдателя щелкните кнопку **Пуск**, последовательно щелкните пункты **Все программы**, **Стандартные**, щелкните правой кнопкой мыши значок **Командная строка** и в контекстном меню выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="be510-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="be510-227">В окне консоли введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="be510-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="be510-228">В окне командной строки отобразится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="be510-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="be510-p124">BITSAdmin является устаревшей, доступность для использования в следующих версиях Windows не гарантируется. Средства администрирования для службы BITS теперь предоставляются командлетами BITS PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be510-p124">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="be510-231">Для параметров прокси-сервера интернет-службы учетной записи NetworkService установлено значение NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="be510-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="be510-232">(подключение = по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="be510-232">(connection = default)</span></span>
  
<span data-ttu-id="be510-233">Это сообщение означает, что вы отключили параметры прокси-сервера браузера Internet Explorer для учетной записи сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="be510-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="be510-234">Искусственная транзакция единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="be510-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="be510-235">Искусственная транзакция обмена сообщениями Exchange (UM) проверяет, что тестовые пользователи могут подключаться к учетным записям голосовой почты, которые размещаются в Exchange.</span><span class="sxs-lookup"><span data-stu-id="be510-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="be510-236">Для этих тестовых пользователей должны быть предварительно настроены учетные записи голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="be510-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="be510-237">Искусственная транзакция сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="be510-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="be510-238">Чтобы воспользоваться искусственной транзакцией сохраняемого чата, необходимо сначала создать канал и предоставить тестовым пользователям разрешения для использования.</span><span class="sxs-lookup"><span data-stu-id="be510-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="be510-239">Искусственную транзакцию сохраняемого чата можно использовать для настройки следующего канала:</span><span class="sxs-lookup"><span data-stu-id="be510-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="be510-240">Эта задача настройки должна быть запущена изнутри предприятия:</span><span class="sxs-lookup"><span data-stu-id="be510-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="be510-241">Если запустить ее с компьютера, не являющегося сервером, пользователь, запустивший командлет должен являться членом роли CsPersistentChatAdministrators в соответствии с управлением доступом на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="be510-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="be510-242">Если выполнить непосредственно с самого сервера, пользователь, запустивший командлет, должен являться членом группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="be510-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="be510-243">Искусственная транзакция однорангового вызова ТСОП</span><span class="sxs-lookup"><span data-stu-id="be510-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="be510-244">Искусственная транзакция Test-CsPstnPeerToPeerCall проверяет возможность выполнять и принимать вызовы через телефонную сеть общего доступа (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="be510-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="be510-245">Чтобы запустить искусственную транзакцию, вы должны настроить следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="be510-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="be510-246">Два тестовых пользователя с поддержкой UC (вызывающий и вызываемый абонент).</span><span class="sxs-lookup"><span data-stu-id="be510-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="be510-247">Прямые входные номера для каждой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="be510-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="be510-248">Маршруты политики VoIP и голосовой связи, которые позволяют звонков на номер получателя для связи с шлюзом ТСОП.</span><span class="sxs-lookup"><span data-stu-id="be510-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="be510-249">Шлюз ТСОП, который принимает звонок и мультимедиа, который будет маршрутизации вызовов в домашний пул получателя в, зависит от числа набираемым.</span><span class="sxs-lookup"><span data-stu-id="be510-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="be510-250">Искусственная транзакция единой системы хранилища контактов</span><span class="sxs-lookup"><span data-stu-id="be510-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="be510-251">Искусственная транзакция единого хранилища контактов проверяет возможность Скайп Business Server для получения контактов от имени пользователя из Exchange.</span><span class="sxs-lookup"><span data-stu-id="be510-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="be510-252">Чтобы использовать эту искусственную транзакцию, следует выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="be510-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="be510-253">необходимо настроить проверку подлинности сервер-сервер Lyss-Exchange;</span><span class="sxs-lookup"><span data-stu-id="be510-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="be510-254">тестовые пользователи должны иметь допустимые почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="be510-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="be510-255">После этих условий, можно запустить следующий командлет Windows PowerShell, чтобы переносить списки контактов тестовых пользователей в Exchange:</span><span class="sxs-lookup"><span data-stu-id="be510-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="be510-256">Перенос списков контактов тестового пользователя в Exchange может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="be510-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="be510-257">Для проверки хода выполнения миграции, то же самое командной строки можно запустить без флага - программы установки:</span><span class="sxs-lookup"><span data-stu-id="be510-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="be510-258">Данная команда будет выполнена по завершении процесса миграции.</span><span class="sxs-lookup"><span data-stu-id="be510-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="be510-259">Искусственная транзакция XMPP</span><span class="sxs-lookup"><span data-stu-id="be510-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="be510-260">Искусственная транзакция мгновенных сообщений XMPP нуждается в настройке компонента XMPP с указанием одного или нескольких федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="be510-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="be510-261">Чтобы включить искусственную транзакцию XMPP, необходимо предоставить параметр XmppTestReceiverMailAddress, используя учетную запись пользователя в домене XMPP с поддержкой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="be510-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="be510-262">Пример:</span><span class="sxs-lookup"><span data-stu-id="be510-262">For example:</span></span>
  
```
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="be510-263">В этом примере Скайп для правила Business Server потребуется существует для маршрутизации сообщений для домена litwareinc.com на шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="be510-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="be510-264">XMPP шлюзов и прокси-серверы, доступные в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="be510-264">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="be510-265">Для получения дополнительных сведений в разделе [федерации XMPP миграции](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="be510-265">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="be510-266">Искусственная транзакция сервера видеовзаимодействия</span><span class="sxs-lookup"><span data-stu-id="be510-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="be510-267">Искусственная транзакция видео взаимодействия сервера по ДИАГОНАЛИ необходимо загрузить и установить файлы поддержки искусственная транзакция ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span><span class="sxs-lookup"><span data-stu-id="be510-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="be510-268">Чтобы установить VISSTSupportPackage.msi убедитесь, что зависимости для msi уже установлены (вкладка системных требований).</span><span class="sxs-lookup"><span data-stu-id="be510-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="be510-269">Запустите VISSTSupportPackage.msi для выполнения простой установки.</span><span class="sxs-lookup"><span data-stu-id="be510-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="be510-270">MSI-файла устанавливает все файлы по следующему пути: «%ProgramFiles%\VIS искусственная транзакция пакет поддержки».</span><span class="sxs-lookup"><span data-stu-id="be510-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="be510-271">Для получения дополнительных сведений о запуске искусственных транзакций VIS обратитесь к документации для командлета [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) .</span><span class="sxs-lookup"><span data-stu-id="be510-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="be510-272">Изменение частоты запуска искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="be510-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="be510-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="be510-273"></span></span>

<span data-ttu-id="be510-274">По умолчанию искусственные транзакции будут выполнятся для настроенных пользователей каждые 15 минут.</span><span class="sxs-lookup"><span data-stu-id="be510-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="be510-275">Искусственные транзакции выполняются последователь в пределах набора пользователей с целью предотвращения конфликтов между двумя искусственными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="be510-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="be510-276">Для выполнения всех искусственных транзакций необходимо указать более длительный интервал времени.</span><span class="sxs-lookup"><span data-stu-id="be510-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="be510-277">Если искусственные транзакции необходимо выполнять чаще, количество этих выполняемых для указанного набора пользователей транзакций необходимо уменьшить, чтобы тесты могли быть завершены в рамках требуемого периода времени с наличием небольшого запаса для случайных задержек в работе сети.</span><span class="sxs-lookup"><span data-stu-id="be510-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="be510-278">При необходимости выполнения большего количества искусственных транзакций создайте больше наборов пользователей для выполнения дополнительных искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="be510-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="be510-279">Чтобы изменить частоту выполнения искусственных транзакций, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="be510-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="be510-280">Открыть System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="be510-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="be510-281">Нажмите раздел "Создание".</span><span class="sxs-lookup"><span data-stu-id="be510-281">Click Authoring section.</span></span> <span data-ttu-id="be510-282">Выберите раздел правил (в разделе "Создание")</span><span class="sxs-lookup"><span data-stu-id="be510-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="be510-283">В разделе правила найти правило с именем «Основные искусственных транзакций средства выполнения производительности коллекции правила»</span><span class="sxs-lookup"><span data-stu-id="be510-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="be510-284">Правила, щелкните правой кнопкой мыши и выберите переопределений, установите переключатель в положение правило и выберите «для всех объектов класса: наблюдатель пула»</span><span class="sxs-lookup"><span data-stu-id="be510-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="be510-285">В окне Свойства переопределить выберите имя параметра «Частота» и установите значение переопределить нужную папку.</span><span class="sxs-lookup"><span data-stu-id="be510-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="be510-286">В том же окне выберите пакет управления, к которому будет применено данное переопределение</span><span class="sxs-lookup"><span data-stu-id="be510-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="be510-287">Использование подробного журнала для искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="be510-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="be510-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="be510-288"></span></span>

<span data-ttu-id="be510-289">Искусственные транзакции доказали свою огромную пользу в рамках помощи по определению неполадок в системе.</span><span class="sxs-lookup"><span data-stu-id="be510-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="be510-290">Например, командлет Test-CsRegistration может оповестить администраторов о наличии затруднений у пользователей во время регистрации в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="be510-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="be510-291">Однако для определения фактической причины неполадки могут потребоваться дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="be510-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="be510-p133">По этой причине искусственные транзакции предоставляют широкий набор возможностей ведения журнала. Благодаря этим возможностям для каждого активного действия искусственной транзакции записывается следующая информация:</span><span class="sxs-lookup"><span data-stu-id="be510-p133">For this reason, synthetic transactions provide rich logging. With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="be510-294">Время начала операции</span><span class="sxs-lookup"><span data-stu-id="be510-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="be510-295">Время завершения операции</span><span class="sxs-lookup"><span data-stu-id="be510-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="be510-296">Действие, которое было выполнено (например, создание конференции, присоединение к ней или выход, вход в Skype для бизнеса Server; отправка мгновенного сообщения)</span><span class="sxs-lookup"><span data-stu-id="be510-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="be510-297">Информационные, подробные сообщения, предупреждения или сообщения об ошибках, которые были созданы при выполнении операции</span><span class="sxs-lookup"><span data-stu-id="be510-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="be510-298">Сообщения о регистрации SIP</span><span class="sxs-lookup"><span data-stu-id="be510-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="be510-299">Записи об исключениях или диагностические коды, созданные при выполнении операции</span><span class="sxs-lookup"><span data-stu-id="be510-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="be510-300">Итоговый результат выполнения операции</span><span class="sxs-lookup"><span data-stu-id="be510-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="be510-p134">Эта информация создается автоматически при каждом запуске искусственной транзакции, но автоматическое отображение или сохранение сведений в файл журнала не выполняется. Если вы запустили искусственную транзакцию вручную, можно использовать параметр OutLoggerVariable для указания переменной Windows PowerShell, в которой будет сохраняться информация. Затем у вас есть возможность использования одного из двух методов, позволяющих сохранять и/или просматривать полный журнал сообщений об ошибках в формате XML или HTML.</span><span class="sxs-lookup"><span data-stu-id="be510-p134">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file. If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored. From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="be510-304">Чтобы извлечь информацию об устранении неполадки, укажите параметр OutLoggerVariable с последующим именем переменной по своему выбору:</span><span class="sxs-lookup"><span data-stu-id="be510-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="be510-305">: Имени имени переменной символ $.</span><span class="sxs-lookup"><span data-stu-id="be510-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="be510-306">Например, используйте имя переменной RegistrationTest, а не $RegistrationTest.</span><span class="sxs-lookup"><span data-stu-id="be510-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="be510-307">При выполнении данной команды будут отображены следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="be510-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="be510-308">Полное доменное имя целевого: atl-cs-001.litwareinc.com результатов: сбой задержка: 00:00:00 сообщение об ошибке: этот компьютер не имеет назначенного сертификаты.</span><span class="sxs-lookup"><span data-stu-id="be510-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="be510-309">Диагностика: можно получить доступ к намного более подробные сведения для Эта ошибка только сообщение об ошибке, показано ниже.</span><span class="sxs-lookup"><span data-stu-id="be510-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="be510-310">Для получения доступа к этой информации в формате HTML используйте команду, аналогичную этой, чтобы сохранить данные, хранящиеся в переменной RegistrationTest, в файл HTML:</span><span class="sxs-lookup"><span data-stu-id="be510-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="be510-311">Можно также использовать метод ToXML() для сохранения данных в файл XML:</span><span class="sxs-lookup"><span data-stu-id="be510-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="be510-312">Эти файлы затем можно просматривать с помощью Windows Internet Explorer, Microsoft Visual Studio или любого другого приложения, поддерживающего открытие файлов HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="be510-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="be510-313">Искусственные транзакции, выполните в System Center Operations Manager автоматически создаются файлы журнала для сбоев.</span><span class="sxs-lookup"><span data-stu-id="be510-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="be510-314">Эти журналы не будут созданы, если сбой выполнения произойдет до того, как PowerShell Skype для бизнеса Server загрузит и запустит искусственную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="be510-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="be510-315">По умолчанию Скайп для Business Server сохраняет файлы журналов в папку, которая не является общей.</span><span class="sxs-lookup"><span data-stu-id="be510-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="be510-316">Чтобы сделать эти журналы доступны, должны совместно использовать эту папку.</span><span class="sxs-lookup"><span data-stu-id="be510-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="be510-317">Например: \\atl-watcher-001.litwareinc.com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="be510-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 