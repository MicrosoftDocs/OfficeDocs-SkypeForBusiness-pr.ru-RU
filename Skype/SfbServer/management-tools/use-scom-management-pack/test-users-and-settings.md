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
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: Сводка. Настройка тестовых учетных записей пользователей и параметров узлов-watcher для искусственных транзакций Skype для бизнеса Server.
ms.openlocfilehash: 687aec65089939d2f4cb7b110b4139eca28433fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814839"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="bd651-103">Настройка тестовых пользователей и параметров узла-watcher</span><span class="sxs-lookup"><span data-stu-id="bd651-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="bd651-104">**Сводка:** Настройте тестовые учетные записи пользователей и параметры узлов-watcher для искусственных транзакций Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bd651-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="bd651-105">Настроив компьютер, который будет выступать в качестве узла-наблюдателя, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bd651-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="bd651-106">[Настройте тестовые учетные записи пользователей](test-users-and-settings.md#testuser) для использования этими узлами-watcher.</span><span class="sxs-lookup"><span data-stu-id="bd651-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="bd651-107">Если вы используете проверку подлинности согласованием, вам также необходимо выполнить командлет **Set-CsTestUserCredential**, чтобы разрешить использование этих учетных записей узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="bd651-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="bd651-108">Обновите параметры конфигурации узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="bd651-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="bd651-109">Настройка тестовых учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="bd651-109">Configure Test User Accounts</span></span>
<span data-ttu-id="bd651-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="bd651-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="bd651-111">Тестовые учетные записи не обязательно должны представлять реальных пользователей, но они должны быть действительными учетными записями Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bd651-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="bd651-112">Кроме того, эти учетные записи должны быть включены для Skype для бизнеса Server, у них должны быть допустимые SIP-адреса, а также для Корпоративная голосовая связь (для использования искусственной транзакции Test-CsPstnPeerToPeerCall транзакций).</span><span class="sxs-lookup"><span data-stu-id="bd651-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="bd651-113">Если используется метод проверки подлинности TrustedServer, необходимо убедиться, что эти учетные записи существуют, и настроить их как отмечено.</span><span class="sxs-lookup"><span data-stu-id="bd651-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="bd651-114">Необходимо назначить по крайней мере двух тестовых пользователей для каждого пула, который вы хотите протестировать.</span><span class="sxs-lookup"><span data-stu-id="bd651-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="bd651-115">Если используется метод проверки подлинности Согласование, необходимо также использовать Set-CsTestUserCredential и skype for Business Server Management Shell, чтобы эти тестовые учетные записи могли работать с искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="bd651-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="bd651-116">Для этого необходимо использовать следующую команду (эти команды предполагают, что две учетные записи пользователей Active Directory созданы и что эти учетные записи включены для Skype для бизнеса Server):</span><span class="sxs-lookup"><span data-stu-id="bd651-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="bd651-117">Необходимо включить не только SIP-адрес, но и имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="bd651-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="bd651-118">Если пароль не включен, Set-CsTestUserCredential запросит ввод этой информации.</span><span class="sxs-lookup"><span data-stu-id="bd651-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="bd651-119">Имя пользователя может быть указано с помощью формата доменного имени\имени пользователя, показанного в предыдущем блоке кода.</span><span class="sxs-lookup"><span data-stu-id="bd651-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="bd651-120">Чтобы убедиться, что учетные данные тестового пользователя созданы, запустите в командной оболочке Skype для бизнеса Server указанные команды:</span><span class="sxs-lookup"><span data-stu-id="bd651-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="bd651-121">Для каждого пользователя будут возвращены сведения, похожие на эти:</span><span class="sxs-lookup"><span data-stu-id="bd651-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="bd651-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="bd651-122">**UserName**</span></span>|<span data-ttu-id="bd651-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="bd651-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bd651-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="bd651-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="bd651-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="bd651-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="bd651-126">Настройка базового узла-watcher с помощью искусственных транзакций по умолчанию</span><span class="sxs-lookup"><span data-stu-id="bd651-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="bd651-127">После создания тестовых пользователей можно создать узел-watcher с помощью команды, похожей на данной:</span><span class="sxs-lookup"><span data-stu-id="bd651-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="bd651-128">Эта команда создает узел-наблюдатель с параметрами по умолчанию, который выполняет набор искусственных транзакций по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bd651-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="bd651-129">Новый узел-watcher также использует тестовых пользователей watcher1@litwareinc.com и watcher2@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="bd651-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="bd651-130">Если узел-watcher использует проверку подлинности TrustedServer, двумя тестовыми учетными записями могут быть любые допустимые учетные записи пользователей, включенные для Active Directory и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bd651-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="bd651-131">Если узел-watcher использует метод проверки подлинности Negotiate, эти учетные записи пользователей также должны быть включены для узла-Set-CsTestUserCredential.</span><span class="sxs-lookup"><span data-stu-id="bd651-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="bd651-132">Чтобы проверить, правильно ли настроено автоматическое обнаружение целевого пула для входов, а не нацелив пул напрямую, с помощью указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="bd651-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="bd651-133">Настройка расширенных тестов</span><span class="sxs-lookup"><span data-stu-id="bd651-133">Configuring Extended Tests</span></span>

<span data-ttu-id="bd651-134">Если вы хотите включить тест PSTN, который проверяет возможность подключения к телефонной сети общего параметров, при настройке узла-watcher необходимо создать дополнительную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="bd651-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="bd651-135">Во-первых, необходимо связать тестовых пользователей с типом теста STN, выдав команду, аналогичную этой, из командной оболочки Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="bd651-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="bd651-136">Результаты этой команды должны храниться в переменной.</span><span class="sxs-lookup"><span data-stu-id="bd651-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="bd651-137">В этом примере переменная называется $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="bd651-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="bd651-138">Далее можно использовать cmdlet **New-CsWatcherNodeConfiguration,** чтобы связать тип теста (хранимый в переменной $pstnTest) с пулом Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bd651-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="bd651-139">Например, следующая команда создает конфигурацию узла-atl-cs-001.litwareinc.com пула, добавляет двух тестовых пользователей, созданных ранее, и добавляет тестовый тип STN:</span><span class="sxs-lookup"><span data-stu-id="bd651-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="bd651-140">Если вы не установили основные файлы Skype для бизнеса Server и базу данных RTCLocal на компьютере узла-watcher, команда не будет работать.</span><span class="sxs-lookup"><span data-stu-id="bd651-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="bd651-141">Чтобы протестировать несколько политик голосовой почты, можно создать расширенный тест для каждой политики с помощью cmdlet **New-CsExtendedTest.**</span><span class="sxs-lookup"><span data-stu-id="bd651-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="bd651-142">Предоставленные пользователи должны быть настроены с помощью нужных политик голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="bd651-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="bd651-143">Расширенные тесты передаются в cmdlet **New-CsWatcherNodeConfiguration** с помощью запятой-delimiters, например:</span><span class="sxs-lookup"><span data-stu-id="bd651-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="bd651-144">-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="bd651-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="bd651-145">Так как для нового **узла-смотрителя** был вызван только синтетическая транзакция по умолчанию (и указанная расширенная искусственная транзакция) без параметра Tests, то для нового узла-watcher будет включен только указанный расширенный искусственный транзакций.</span><span class="sxs-lookup"><span data-stu-id="bd651-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="bd651-146">Поэтому узел-watcher будет тестировать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="bd651-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="bd651-147">Registration</span><span class="sxs-lookup"><span data-stu-id="bd651-147">Registration</span></span>
    
- <span data-ttu-id="bd651-148">"IM" (Обмен мгновенными сообщениями);</span><span class="sxs-lookup"><span data-stu-id="bd651-148">IM</span></span>
    
- <span data-ttu-id="bd651-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="bd651-149">GroupIM</span></span>
    
- <span data-ttu-id="bd651-150">P2PAV (одноранговые аудио- и видеосеансы)</span><span class="sxs-lookup"><span data-stu-id="bd651-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="bd651-151">AvConference (аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="bd651-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="bd651-152">Присутствие</span><span class="sxs-lookup"><span data-stu-id="bd651-152">Presence</span></span>
    
- <span data-ttu-id="bd651-153">ABS (служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="bd651-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="bd651-154">ABWQ (веб-служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="bd651-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="bd651-155">Следующие компоненты не будут тестироваться по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="bd651-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="bd651-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="bd651-156">ASConference</span></span>
    
- <span data-ttu-id="bd651-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="bd651-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="bd651-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="bd651-158">DataConference</span></span>
    
- <span data-ttu-id="bd651-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="bd651-159">DialinConferencing</span></span>
    
- <span data-ttu-id="bd651-160">ExumConnectivity (единая система обмена сообщениями Exchange)</span><span class="sxs-lookup"><span data-stu-id="bd651-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="bd651-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="bd651-161">JoinLauncher</span></span>
    
- <span data-ttu-id="bd651-162">MCXP2PIM (обмен мгновенными сообщениями с устаревших мобильных устройств)</span><span class="sxs-lookup"><span data-stu-id="bd651-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="bd651-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="bd651-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="bd651-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="bd651-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="bd651-165">PSTN (вызовы шлюза STN, указанные в качестве расширенного теста)</span><span class="sxs-lookup"><span data-stu-id="bd651-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="bd651-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="bd651-166">UcwaConference</span></span>
    
- <span data-ttu-id="bd651-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="bd651-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="bd651-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="bd651-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="bd651-169">Добавление и удаление искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="bd651-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="bd651-170">После настройки узла-наблюдателя вы можете добавлять искусственные транзакции на узел-наблюдатель или удалять их с узла-наблюдателя с помощью командлета Set-CsWatcherNodeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="bd651-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="bd651-171">Например, чтобы добавить тест PersistentChatMessage на узел-наблюдатель, используйте следующую команду с методом Add.</span><span class="sxs-lookup"><span data-stu-id="bd651-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="bd651-172">При указании нескольких тестов используйте запятые.</span><span class="sxs-lookup"><span data-stu-id="bd651-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="bd651-173">Пример:</span><span class="sxs-lookup"><span data-stu-id="bd651-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="bd651-174">Ошибка возникает, если один или несколько из этих тестов (например, DataConference) уже включены на узле-watcher.</span><span class="sxs-lookup"><span data-stu-id="bd651-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="bd651-175">В этом случае вы получите следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="bd651-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="bd651-176">Set-CsWatcherNodeConfiguration: имеется повторяемая последовательность ключей "DataConference" для ключа "urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName" или уникальное ограничение удостоверения.</span><span class="sxs-lookup"><span data-stu-id="bd651-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="bd651-177">Если произошла эта ошибка, изменения не применяются.</span><span class="sxs-lookup"><span data-stu-id="bd651-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="bd651-178">Команду следует повторно выполнить с удалением дубликата теста.</span><span class="sxs-lookup"><span data-stu-id="bd651-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="bd651-179">Чтобы удалить искусственную транзакцию из узла-watcher, используйте метод Remove.</span><span class="sxs-lookup"><span data-stu-id="bd651-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="bd651-180">Например, следующая команда удаляет тест ABWQ с узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="bd651-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="bd651-181">Вы можете использовать метод Replace, чтобы заменить все тесты, включенные в текущий момент, на один или несколько новых тестов.</span><span class="sxs-lookup"><span data-stu-id="bd651-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="bd651-182">Например, если вы хотите, чтобы узел-watcher только запускал тест im, вы можете настроить его с помощью этой команды:</span><span class="sxs-lookup"><span data-stu-id="bd651-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="bd651-183">При запуске этой команды все искусственные транзакции на указанном узле-просмотре будут отключены, кроме мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="bd651-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="bd651-184">Просмотр и тестирование конфигурации узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="bd651-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="bd651-185">Чтобы просмотреть тесты, назначенные узлу-наблюдателю, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="bd651-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="bd651-186">Эта команда возвращает сведения, похожие на эти, в зависимости от искусственных транзакций, которые были назначены узлу:</span><span class="sxs-lookup"><span data-stu-id="bd651-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="bd651-187">Регистрация IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="bd651-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="bd651-188">Чтобы просмотреть искусственные транзакции в алфавитном порядке, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="bd651-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="bd651-189">Чтобы убедиться, что узел-watcher создан, введите следующую команду в командной оболочке Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="bd651-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="bd651-190">Вы получите сведения, похожие на эти:</span><span class="sxs-lookup"><span data-stu-id="bd651-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="bd651-191">Identity : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bd651-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="bd651-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="bd651-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="bd651-193">ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN Test; Te...}</span><span class="sxs-lookup"><span data-stu-id="bd651-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="bd651-194">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bd651-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="bd651-195">PortNumber : 5061</span><span class="sxs-lookup"><span data-stu-id="bd651-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="bd651-196">Чтобы убедиться, что узел-watcher настроен правильно, введите в командной оболочке Skype для бизнеса Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bd651-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="bd651-197">Эта команда будет тестировать каждый узел-watcher в развертывании и подтверждать, выполнены ли следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bd651-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="bd651-198">Установлена необходимая роль регистратора.</span><span class="sxs-lookup"><span data-stu-id="bd651-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="bd651-199">Создается необходимый ключ реестра (завершится при Set-CsWatcherNodeConfiguration управления).</span><span class="sxs-lookup"><span data-stu-id="bd651-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="bd651-200">На серверах работает правильная версия Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bd651-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="bd651-201">Порты настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="bd651-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="bd651-202">имеются ли у назначенных тестовых пользователей требуемые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="bd651-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="bd651-203">Управление узлами-наблюдателями</span><span class="sxs-lookup"><span data-stu-id="bd651-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="bd651-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="bd651-204"><a name="testuser"> </a></span></span>

<span data-ttu-id="bd651-205">Помимо изменения искусственных транзакций, которые выполняются на узле-просмотре,  можно также использовать для выполнения двух других важных задач: включение и отключение узла-watcher, а также настройку узла-watcher для использования внутренних или внешних ВЕБ-URL-адресов при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="bd651-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="bd651-206">По умолчанию узлы-наблюдатели периодически запускают все включенные искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="bd651-206">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="bd651-207">Однако иногда может потребоваться приостановить эти транзакции.</span><span class="sxs-lookup"><span data-stu-id="bd651-207">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="bd651-208">Например, если узел-наблюдатель временно отключился от сети, у него больше нет причин запускать искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="bd651-208">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="bd651-209">Без сетевого подключения эти транзакции не будут работать.</span><span class="sxs-lookup"><span data-stu-id="bd651-209">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="bd651-210">Чтобы временно отключить узел-watcher, в командной оболочке Skype для бизнеса Server запустите команду, аналогичную этой:</span><span class="sxs-lookup"><span data-stu-id="bd651-210">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="bd651-211">Эта команда отключит выполнение искусственных транзакций на узле-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="bd651-211">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="bd651-212">Чтобы возобновить выполнение искусственных транзакций, снова задайте для свойства Enabled значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="bd651-212">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="bd651-213">Свойство Enabled может использоваться для включения или отключения узлов-наблюдателей.</span><span class="sxs-lookup"><span data-stu-id="bd651-213">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="bd651-214">Если нет необходимости временно удалять узел-наблюдатель, используйте командлет **Remove-CsWatcherNodeConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="bd651-214">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="bd651-215">Эта команда удаляет все параметры конфигурации узла-watcher с указанного компьютера, что не позволяет компьютеру автоматически запускать искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="bd651-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="bd651-216">Однако эта команда не будет удалить файлы агента System Center или системные файлы Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bd651-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="bd651-217">По умолчанию узлы-пользователи-watcher используют внешние ВЕБ-URL-адреса организации при проведении тестов.</span><span class="sxs-lookup"><span data-stu-id="bd651-217">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="bd651-218">Однако узлы-watcher также можно настроить для использования внутренних ВЕБ-URL-адресов организации.</span><span class="sxs-lookup"><span data-stu-id="bd651-218">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="bd651-219">Это позволит администраторам проверить доступ к URL-адресам тех пользователей, которые находятся внутри сети периметра.</span><span class="sxs-lookup"><span data-stu-id="bd651-219">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="bd651-220">Чтобы настроить узел-watcher на использование внутренних URL-адресов вместо внешних URL-адресов, установите для свойства UseInternalWebURls $True:</span><span class="sxs-lookup"><span data-stu-id="bd651-220">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="bd651-221">Сброс этого свойства до значения по умолчанию False ($False) приведет к повторному использованию внешними URL-адресами для watcher:</span><span class="sxs-lookup"><span data-stu-id="bd651-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="bd651-222">Специальные инструкции по установке для искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="bd651-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="bd651-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="bd651-223"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="bd651-224">Большинство искусственных транзакций могут запускаться на узле-watcher как есть.</span><span class="sxs-lookup"><span data-stu-id="bd651-224">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="bd651-225">В большинстве случаев, как только искусственная транзакция добавляется в параметры конфигурации узла-watcher, узел-watcher может начать использовать эту искусственную транзакцию во время тестирования.</span><span class="sxs-lookup"><span data-stu-id="bd651-225">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="bd651-226">Однако некоторые искусственные транзакции требуют специальных инструкций по настройке, как было рассмотрено в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="bd651-226">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="bd651-227">Искусственная транзакция для видеоконференций</span><span class="sxs-lookup"><span data-stu-id="bd651-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="bd651-228">Если компьютер узла-watcher находится за пределами сети периметра, возможно, вы не сможете запустить искусственную транзакцию для передачи данных, если только вы не отключите параметры прокси-сервера Браузера Windows Internet Explorer® для учетной записи сетевой службы, выполив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bd651-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="bd651-229">На компьютере узла-watcher нажмите кнопку "Начните", выберите пункт "Все программы", выберите "Программы доступа", щелкните правой кнопкой мыши командную подсказку **и** выберите команду "Запуск от прав **администратора".**   </span><span class="sxs-lookup"><span data-stu-id="bd651-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="bd651-230">В окне консоли введите следующую команду и нажмите ввод.</span><span class="sxs-lookup"><span data-stu-id="bd651-230">In the console window, type the following command and then press ENTER.</span></span> 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    <span data-ttu-id="bd651-231">В командном окне отобразилось следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="bd651-231">You will see the following message displayed in the command window:</span></span>

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    <span data-ttu-id="bd651-232">Это сообщение означает, что вы отключили параметры прокси-сервера Internet Explorer для учетной записи сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="bd651-232">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="bd651-233">Искусственная транзакция единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="bd651-233">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="bd651-234">Искусственная транзакция единой системы обмена сообщениями Exchange проверяет, могут ли тестовые пользователи подключаться к учетным записям голосовой почты, которые есть в Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd651-234">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="bd651-235">Тестовые пользователи должны быть предварительно сконфигурированы с помощью учетных записей голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="bd651-235">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="bd651-236">Искусственная транзакция сохраняемой беседы</span><span class="sxs-lookup"><span data-stu-id="bd651-236">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="bd651-237">Чтобы использовать искусственную транзакцию сохраняемого чата, необходимо сначала создать канал и предоставить тест-пользователям разрешения на его использование.</span><span class="sxs-lookup"><span data-stu-id="bd651-237">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="bd651-238">Для настройки этого канала можно использовать искусственную транзакцию Persistent Chat:</span><span class="sxs-lookup"><span data-stu-id="bd651-238">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="bd651-239">Эту задачу установки необходимо запустить внутри предприятия:</span><span class="sxs-lookup"><span data-stu-id="bd651-239">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="bd651-240">При запуске с компьютера, не относящавшегося к серверу, пользователь, выполнивший этот запуск, должен быть членом роли CsPersistentChatAdministrators для Role-Based Access Control (RBAC).</span><span class="sxs-lookup"><span data-stu-id="bd651-240">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="bd651-241">При запуске с самого сервера пользователь, выполнивший этот запуск, должен быть членом группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bd651-241">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="bd651-242">Искусственная транзакция одноранговых вызовов STN</span><span class="sxs-lookup"><span data-stu-id="bd651-242">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="bd651-243">Искусственная транзакция Test-CsPstnPeerToPeerCall возможность совершения и получения вызовов через телефонную сеть общего звонков (STN).</span><span class="sxs-lookup"><span data-stu-id="bd651-243">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="bd651-244">Чтобы запустить эту искусственную транзакцию, необходимо настроить:</span><span class="sxs-lookup"><span data-stu-id="bd651-244">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="bd651-245">Два тестовых пользователя с включенной поддержкой UC (вызываемая и приемная).</span><span class="sxs-lookup"><span data-stu-id="bd651-245">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="bd651-246">Прямые входные номера для каждой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd651-246">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="bd651-247">Политики VoIP и маршруты голосовой почты, которые позволяют звонкам на номер приемник достигать шлюза STN.</span><span class="sxs-lookup"><span data-stu-id="bd651-247">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="bd651-248">Шлюз STN, который принимает вызовы и носители, которые будут перенапорять вызовы обратно в домашний пул приемник в зависимости от набраного номера.</span><span class="sxs-lookup"><span data-stu-id="bd651-248">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="bd651-249">Искусственная транзакция единого магазина контактов</span><span class="sxs-lookup"><span data-stu-id="bd651-249">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="bd651-250">Искусственная транзакция единого магазина контактов проверяет возможность Skype для бизнеса Server получать контакты от имени пользователя из Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd651-250">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="bd651-251">Чтобы использовать эту искусственную транзакцию, следует выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="bd651-251">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="bd651-252">Lyss-Exchange необходимо настроить проверку подлинности между серверами.</span><span class="sxs-lookup"><span data-stu-id="bd651-252">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="bd651-253">У тестовых пользователей должен быть действительный почтовый ящик Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd651-253">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="bd651-254">После этого можно выполнить следующий Windows PowerShell для переноса списков контактов тестовых пользователей в Exchange:</span><span class="sxs-lookup"><span data-stu-id="bd651-254">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="bd651-255">Миграция тестовых списков контактов пользователей в Exchange может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="bd651-255">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="bd651-256">Для отслеживания хода миграции можно запустить ту же командную строку без флага -Setup:</span><span class="sxs-lookup"><span data-stu-id="bd651-256">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="bd651-257">Эта командная строка завершится успешно после завершения миграции.</span><span class="sxs-lookup"><span data-stu-id="bd651-257">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="bd651-258">Искусственная транзакция XMPP</span><span class="sxs-lookup"><span data-stu-id="bd651-258">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="bd651-259">Искусственная транзакция обмена мгновенными сообщениями XMPP требует настройки функции XMPP с одним или более федерационными доменами.</span><span class="sxs-lookup"><span data-stu-id="bd651-259">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="bd651-260">Чтобы включить искусственную транзакцию XMPP, необходимо предоставить параметр XmppTestReceiverMailAddress с учетной записью пользователя в домене XMPP с маршрутией.</span><span class="sxs-lookup"><span data-stu-id="bd651-260">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="bd651-261">Например:</span><span class="sxs-lookup"><span data-stu-id="bd651-261">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="bd651-262">В этом примере потребуется правило Skype для бизнеса Server, чтобы отправлять сообщения для litwareinc.com на шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="bd651-262">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="bd651-263">Шлюзы и прокси-серверы XMPP доступны в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bd651-263">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="bd651-264">Дополнительные сведения см. в переносе [федерации XMPP.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)</span><span class="sxs-lookup"><span data-stu-id="bd651-264">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="bd651-265">Искусственная транзакция сервера видеосвязи (VIS)</span><span class="sxs-lookup"><span data-stu-id="bd651-265">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="bd651-266">Искусственная транзакция сервера видеосвязи (VIS) требует загрузки и установки файлов поддержки[ искусственных транзакций (VISSTSupportPackage.msi). ](https://www.microsoft.com/download/details.aspx?id=46921)</span><span class="sxs-lookup"><span data-stu-id="bd651-266">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="bd651-267">Чтобы установить VISSTSupportPackage.msi убедитесь, что зависимости (в соответствии с требованиями к системе) для MSI уже установлены.</span><span class="sxs-lookup"><span data-stu-id="bd651-267">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="bd651-268">Запустите VISSTSupportPackage.msi, чтобы выполнить простую установку.</span><span class="sxs-lookup"><span data-stu-id="bd651-268">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="bd651-269">MSI устанавливает все файлы по следующему пути: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span><span class="sxs-lookup"><span data-stu-id="bd651-269">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="bd651-270">Дополнительные сведения о запуске искусственной транзакции VIS см. в документации по [cmdlet Test-CsP2PVideoInteropServerSipTrunkAV.](https://technet.microsoft.com/library/dn985894.aspx)</span><span class="sxs-lookup"><span data-stu-id="bd651-270">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="bd651-271">Изменение частоты запуска искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="bd651-271">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="bd651-272"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="bd651-272"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="bd651-273">По умолчанию искусственные транзакции будут запускаться с настроенными пользователями каждые 15 минут.</span><span class="sxs-lookup"><span data-stu-id="bd651-273">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="bd651-274">Искусственные транзакции последовательно запускаются в наборе пользователей, чтобы избежать конфликта двух искусственных транзакций друг с другом.</span><span class="sxs-lookup"><span data-stu-id="bd651-274">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="bd651-275">Для обеспечения времени выполнения всех искусственных транзакций требуется более длительный интервал.</span><span class="sxs-lookup"><span data-stu-id="bd651-275">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="bd651-276">Если требуется чаще запускать искусственные транзакции, число искусственных транзакций, запускаемых с заданным набором пользователей, должно быть уменьшено, чтобы тесты могли быть завершены в нужном диапазоне времени с некоторым буфером для периодических сетевых задержек.</span><span class="sxs-lookup"><span data-stu-id="bd651-276">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="bd651-277">Если необходимо выполнить дополнительные искусственные транзакции, создайте дополнительные наборы пользователей для запуска дополнительных искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="bd651-277">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="bd651-278">Чтобы изменить частоту запуска искусственных транзакций, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bd651-278">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="bd651-279">Откройте System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="bd651-279">Open System Center Operations Manager.</span></span> <span data-ttu-id="bd651-280">Щелкните раздел "Автор".</span><span class="sxs-lookup"><span data-stu-id="bd651-280">Click Authoring section.</span></span> <span data-ttu-id="bd651-281">Щелкните раздел "Правила" (в разделе "Авторинг").</span><span class="sxs-lookup"><span data-stu-id="bd651-281">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="bd651-282">В разделе "Правила" найдите правило с именем "Main Synthetic Transaction Runner Performance Collection Rule".</span><span class="sxs-lookup"><span data-stu-id="bd651-282">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="bd651-283">Щелкните правило правой кнопкой мыши и выберите "Переопределения", выберите "Переопредить правило", а затем выберите "Для всех объектов класса: "Pool Watcher".</span><span class="sxs-lookup"><span data-stu-id="bd651-283">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="bd651-284">В окне "Переопределения свойств" выберите имя параметра "Частота" и задав нужное значение переопределения.</span><span class="sxs-lookup"><span data-stu-id="bd651-284">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="bd651-285">В том же окне выберите пакет управления, к которому необходимо применить это переопределения.</span><span class="sxs-lookup"><span data-stu-id="bd651-285">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="bd651-286">Использование подробного журнала для искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="bd651-286">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="bd651-287"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="bd651-287"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="bd651-288">Искусственные транзакции очень полезны для выявления проблем в системе.</span><span class="sxs-lookup"><span data-stu-id="bd651-288">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="bd651-289">Например, Test-CsRegistration может оповещать администраторов о том, что пользователи с трудом регистрируются в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bd651-289">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="bd651-290">Однако для определения фактической причины сбоя могут потребоваться дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="bd651-290">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="bd651-291">По этой причине искусственные транзакции предоставляют богатый объем ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="bd651-291">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="bd651-292">При этом для каждого действия, которое осуществляется искусственной транзакцией, записываются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="bd651-292">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="bd651-293">Время начала действия.</span><span class="sxs-lookup"><span data-stu-id="bd651-293">The time that the activity started.</span></span>
    
- <span data-ttu-id="bd651-294">Время завершения действия.</span><span class="sxs-lookup"><span data-stu-id="bd651-294">The time that the activity finished.</span></span>
    
- <span data-ttu-id="bd651-295">Выполненное действие (например, создание, присоединение или выход из конференции, вход в Skype для бизнеса Server; отправка мгновенного сообщения).</span><span class="sxs-lookup"><span data-stu-id="bd651-295">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="bd651-296">Информационные, подробные, предупреждения или сообщения об ошибках, созданные при действии.</span><span class="sxs-lookup"><span data-stu-id="bd651-296">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="bd651-297">Сообщения о регистрации SIP.</span><span class="sxs-lookup"><span data-stu-id="bd651-297">SIP registration messages.</span></span>
    
- <span data-ttu-id="bd651-298">Записи исключений или коды диагностики, созданные при окнаности действия.</span><span class="sxs-lookup"><span data-stu-id="bd651-298">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="bd651-299">Net result of running the activity.</span><span class="sxs-lookup"><span data-stu-id="bd651-299">The net result of running the activity.</span></span>
    
<span data-ttu-id="bd651-300">Эти сведения создаются автоматически при каждом запуске искусственной транзакции, но не отображаются автоматически или не сохраняются в файле журнала.</span><span class="sxs-lookup"><span data-stu-id="bd651-300">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="bd651-301">Если искусственная транзакция запущена вручную, можно использовать параметр OutLoggerVariable, чтобы указать переменную Windows PowerShell, в которой будут храниться сведения.</span><span class="sxs-lookup"><span data-stu-id="bd651-301">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="bd651-302">Здесь можно использовать один из двух методов сохранения и/или просмотра сообщений об ошибках в формате XML или HTML.</span><span class="sxs-lookup"><span data-stu-id="bd651-302">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="bd651-303">Чтобы получить сведения об устранении неполадок, укажите параметр OutLoggerVariable, а затем выберите имя переменной:</span><span class="sxs-lookup"><span data-stu-id="bd651-303">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="bd651-304">Имени переменной не должен предшествовать символ $.</span><span class="sxs-lookup"><span data-stu-id="bd651-304">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="bd651-305">Используйте имя переменной, например RegistrationTest (не $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="bd651-305">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="bd651-306">При запуске этой команды вы увидите выходные данные, аналогичные этому:</span><span class="sxs-lookup"><span data-stu-id="bd651-306">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="bd651-307">Целевое Fqdn : atl-cs-001.litwareinc.com result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span><span class="sxs-lookup"><span data-stu-id="bd651-307">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="bd651-308">Диагностика: вы можете получить доступ к гораздо более подробным сведениям об этой ошибке, чем только к показанным здесь сообщением об ошибке.</span><span class="sxs-lookup"><span data-stu-id="bd651-308">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="bd651-309">Чтобы получить доступ к этим сведениям в формате HTML, используйте команду, аналогичную этой, чтобы сохранить данные, хранимые в переменной RegistrationTest, в HTML-файл:</span><span class="sxs-lookup"><span data-stu-id="bd651-309">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="bd651-310">Можно также использовать метод ToXML() для сохранения данных в файл XML:</span><span class="sxs-lookup"><span data-stu-id="bd651-310">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="bd651-311">Эти файлы можно просмотреть с помощью Windows Internet Explorer, Microsoft Visual Studio или любого другого приложения, которое может открывать HTML-или XML-файлы.</span><span class="sxs-lookup"><span data-stu-id="bd651-311">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="bd651-312">Искусственные транзакции, которые запускаются изнутри System Center Operations Manager, автоматически создают эти файлы журналов для сбоев.</span><span class="sxs-lookup"><span data-stu-id="bd651-312">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="bd651-313">Эти журналы не будут созданы, если выполнение не удастся, прежде чем Skype для бизнеса Server PowerShell сможет загрузить и запустить искусственную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="bd651-313">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="bd651-314">По умолчанию Skype для бизнеса Server сохраняет файлы журналов в папку, доступ к которая не является общей.</span><span class="sxs-lookup"><span data-stu-id="bd651-314">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="bd651-315">Чтобы сделать эти журналы доступными, необходимо поделиться этой папкой.</span><span class="sxs-lookup"><span data-stu-id="bd651-315">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="bd651-316">Например: \\ atl-watcher-001.litwareinc.com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="bd651-316">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
