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
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="b9f63-103">Настройка тестовых пользователей и параметров узла-watcher</span><span class="sxs-lookup"><span data-stu-id="b9f63-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="b9f63-104">**Сводка:** Настройте тестовые учетные записи пользователей и параметры узлов-watcher для искусственных транзакций Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b9f63-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="b9f63-105">Настроив компьютер, который будет выступать в качестве узла-наблюдателя, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b9f63-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="b9f63-106">[Настройте тестовые учетные записи пользователей](test-users-and-settings-2019.md#testuser) для использования этими узлами-watcher.</span><span class="sxs-lookup"><span data-stu-id="b9f63-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="b9f63-107">Если вы используете проверку подлинности согласованием, вам также необходимо выполнить командлет **Set-CsTestUserCredential**, чтобы разрешить использование этих учетных записей узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="b9f63-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="b9f63-108">Обновите параметры конфигурации узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="b9f63-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="b9f63-109">Настройка тестовых учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="b9f63-109">Configure Test User Accounts</span></span>
<span data-ttu-id="b9f63-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="b9f63-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="b9f63-111">Тестовые учетные записи не обязательно должны представлять реальных пользователей, но они должны быть действительными учетными записями Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b9f63-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="b9f63-112">Кроме того, эти учетные записи должны быть включены для Skype для бизнеса Server, у них должны быть допустимые SIP-адреса, а также для Корпоративная голосовая связь (для использования искусственной транзакции Test-CsPstnPeerToPeerCall транзакций).</span><span class="sxs-lookup"><span data-stu-id="b9f63-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="b9f63-113">Если используется метод проверки подлинности TrustedServer, необходимо убедиться, что эти учетные записи существуют, и настроить их как отмечено.</span><span class="sxs-lookup"><span data-stu-id="b9f63-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="b9f63-114">Следует назначить по крайней мере трех тестовых пользователей для каждого пула, который вы хотите протестировать.</span><span class="sxs-lookup"><span data-stu-id="b9f63-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="b9f63-115">Если используется метод проверки подлинности Согласование, необходимо также использовать Set-CsTestUserCredential и skype for Business Server Management Shell, чтобы эти тестовые учетные записи могли работать с искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="b9f63-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="b9f63-116">Для этого с помощью следующей команды (эти команды предполагают, что три учетные записи пользователей Active Directory созданы и что эти учетные записи включены для Skype для бизнеса Server):</span><span class="sxs-lookup"><span data-stu-id="b9f63-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="b9f63-117">Необходимо включить не только SIP-адрес, но и имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="b9f63-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="b9f63-118">Если пароль не включен, Set-CsTestUserCredential запросит ввод этой информации.</span><span class="sxs-lookup"><span data-stu-id="b9f63-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="b9f63-119">Имя пользователя может быть указано с помощью формата доменного имени\имени пользователя, показанного в предыдущем блоке кода.</span><span class="sxs-lookup"><span data-stu-id="b9f63-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="b9f63-120">Чтобы убедиться, что учетные данные тестового пользователя созданы, запустите в командной оболочке Skype для бизнеса Server указанные команды:</span><span class="sxs-lookup"><span data-stu-id="b9f63-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="b9f63-121">Для каждого пользователя будут возвращены сведения, похожие на эти:</span><span class="sxs-lookup"><span data-stu-id="b9f63-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="b9f63-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="b9f63-122">**UserName**</span></span>|<span data-ttu-id="b9f63-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="b9f63-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9f63-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="b9f63-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="b9f63-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="b9f63-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="b9f63-126">Настройка базового узла-watcher с помощью искусственных транзакций по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b9f63-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="b9f63-127">После создания тестовых пользователей можно создать узел-watcher с помощью команды, похожей на данной:</span><span class="sxs-lookup"><span data-stu-id="b9f63-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="b9f63-128">Эта команда создает узел-наблюдатель с параметрами по умолчанию, который выполняет набор искусственных транзакций по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b9f63-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="b9f63-129">Для нового узла-наблюдателя используются тестовые пользователи watcher1@litwareinc.com, watcher2@litwareinc.com и watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b9f63-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="b9f63-130">Если узел-watcher использует проверку подлинности TrustedServer, тремя тестовой учетной записью могут быть любые допустимые учетные записи пользователей, включенные для Active Directory и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b9f63-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="b9f63-131">Если узел-watcher использует метод проверки подлинности Согласование, эти учетные записи пользователей также должны быть включены для узла-Set-CsTestUserCredential.</span><span class="sxs-lookup"><span data-stu-id="b9f63-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="b9f63-132">Чтобы проверить, правильно ли настроено автоматическое обнаружение целевого пула для входов, а не нацелив пул напрямую, с помощью указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="b9f63-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="b9f63-133">Настройка расширенных тестов</span><span class="sxs-lookup"><span data-stu-id="b9f63-133">Configuring Extended Tests</span></span>

<span data-ttu-id="b9f63-134">Если вы хотите включить тест PSTN, который проверяет возможность подключения к телефонной сети общего параметров, при настройке узла-watcher необходимо создать дополнительную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b9f63-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="b9f63-135">Во-первых, необходимо связать тестовых пользователей с типом теста STN, выдав команду, аналогичную этой, из командной оболочки Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="b9f63-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="b9f63-136">Результаты этой команды должны храниться в переменной.</span><span class="sxs-lookup"><span data-stu-id="b9f63-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="b9f63-137">В этом примере переменная называется $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="b9f63-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="b9f63-138">Далее можно использовать cmdlet **New-CsWatcherNodeConfiguration,** чтобы связать тип теста (хранимый в переменной $pstnTest) с пулом Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b9f63-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="b9f63-139">Например, следующая команда создает конфигурацию узла-atl-cs-001.litwareinc.com пула, добавляет трех тестовых пользователей, созданных ранее, и добавляет тестовый тип STN:</span><span class="sxs-lookup"><span data-stu-id="b9f63-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="b9f63-140">Если основные файлы Skype для бизнеса Server и база данных RTCLocal на компьютере узла-watcher не установлены, то команда не будет работать.</span><span class="sxs-lookup"><span data-stu-id="b9f63-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="b9f63-141">Чтобы протестировать несколько политик голосовой почты, можно создать расширенный тест для каждой политики с помощью cmdlet **New-CsExtendedTest.**</span><span class="sxs-lookup"><span data-stu-id="b9f63-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="b9f63-142">Предоставленные пользователи должны быть настроены с помощью нужных политик голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b9f63-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="b9f63-143">Расширенные тесты передаются в cmdlet **New-CsWatcherNodeConfiguration** с помощью запятой-delimiters, например:</span><span class="sxs-lookup"><span data-stu-id="b9f63-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="b9f63-144">-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="b9f63-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="b9f63-145">Так как для нового узла-смотрителя был вызван новый узел-watcher с помощью параметра Tests, для нового **узла-смотрителя** был вызван только новый синтетский транзакций по умолчанию (и указанной расширенной искусственной транзакции).</span><span class="sxs-lookup"><span data-stu-id="b9f63-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="b9f63-146">Поэтому узел-watcher будет тестировать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="b9f63-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="b9f63-147">Registration</span><span class="sxs-lookup"><span data-stu-id="b9f63-147">Registration</span></span>
    
- <span data-ttu-id="b9f63-148">"IM" (Обмен мгновенными сообщениями);</span><span class="sxs-lookup"><span data-stu-id="b9f63-148">IM</span></span>
    
- <span data-ttu-id="b9f63-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="b9f63-149">GroupIM</span></span>
    
- <span data-ttu-id="b9f63-150">P2PAV (одноранговые аудио- и видеосеансы)</span><span class="sxs-lookup"><span data-stu-id="b9f63-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="b9f63-151">AvConference (аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="b9f63-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="b9f63-152">Присутствие</span><span class="sxs-lookup"><span data-stu-id="b9f63-152">Presence</span></span>
    
- <span data-ttu-id="b9f63-153">ABS (служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="b9f63-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="b9f63-154">ABWQ (веб-служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="b9f63-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="b9f63-155">Следующие компоненты не будут тестироваться по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="b9f63-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="b9f63-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="b9f63-156">ASConference</span></span>
    
- <span data-ttu-id="b9f63-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="b9f63-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="b9f63-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="b9f63-158">DataConference</span></span>
    
- <span data-ttu-id="b9f63-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="b9f63-159">DialinConferencing</span></span>
    
- <span data-ttu-id="b9f63-160">ExumConnectivity (единая система обмена сообщениями Exchange)</span><span class="sxs-lookup"><span data-stu-id="b9f63-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="b9f63-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="b9f63-161">JoinLauncher</span></span>
    
- <span data-ttu-id="b9f63-162">MCXP2PIM (обмен мгновенными сообщениями с устаревших мобильных устройств)</span><span class="sxs-lookup"><span data-stu-id="b9f63-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="b9f63-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="b9f63-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="b9f63-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="b9f63-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="b9f63-165">PSTN (вызовы шлюза STN, указанные в качестве расширенного теста)</span><span class="sxs-lookup"><span data-stu-id="b9f63-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="b9f63-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="b9f63-166">UcwaConference</span></span>
    
- <span data-ttu-id="b9f63-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="b9f63-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="b9f63-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="b9f63-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="b9f63-169">Добавление и удаление искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="b9f63-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="b9f63-170">После настройки узла-наблюдателя вы можете добавлять искусственные транзакции на узел-наблюдатель или удалять их с узла-наблюдателя с помощью командлета Set-CsWatcherNodeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b9f63-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="b9f63-171">Например, чтобы добавить тест PersistentChatMessage на узел-наблюдатель, используйте следующую команду с методом Add.</span><span class="sxs-lookup"><span data-stu-id="b9f63-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="b9f63-172">При указании нескольких тестов используйте запятые.</span><span class="sxs-lookup"><span data-stu-id="b9f63-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="b9f63-173">Пример:</span><span class="sxs-lookup"><span data-stu-id="b9f63-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="b9f63-174">Ошибка возникает, если один или несколько из этих тестов (например, DataConference) уже включены на узле-watcher.</span><span class="sxs-lookup"><span data-stu-id="b9f63-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="b9f63-175">В этом случае вы получите следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="b9f63-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="b9f63-176">Set-CsWatcherNodeConfiguration: существует повторяемая последовательность ключей "DataConference" для ключа "urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName" или уникальное ограничение удостоверения.</span><span class="sxs-lookup"><span data-stu-id="b9f63-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="b9f63-177">Если произошла эта ошибка, изменения не применяются.</span><span class="sxs-lookup"><span data-stu-id="b9f63-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="b9f63-178">Команду следует повторно выполнить с удалением дубликата теста.</span><span class="sxs-lookup"><span data-stu-id="b9f63-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="b9f63-179">Чтобы удалить искусственную транзакцию из узла-watcher, используйте метод Remove.</span><span class="sxs-lookup"><span data-stu-id="b9f63-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="b9f63-180">Например, следующая команда удаляет тест ABWQ с узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="b9f63-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="b9f63-181">Вы можете использовать метод Replace, чтобы заменить все тесты, включенные в текущий момент, на один или несколько новых тестов.</span><span class="sxs-lookup"><span data-stu-id="b9f63-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="b9f63-182">Например, если вы хотите, чтобы узел-watcher только запускал тест im, вы можете настроить его с помощью этой команды:</span><span class="sxs-lookup"><span data-stu-id="b9f63-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="b9f63-183">При запуске этой команды все искусственные транзакции на указанном узле-просмотре будут отключены, кроме мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="b9f63-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="b9f63-184">Просмотр и тестирование конфигурации узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="b9f63-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="b9f63-185">Чтобы просмотреть тесты, назначенные узлу-наблюдателю, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b9f63-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="b9f63-186">Эта команда возвращает сведения, похожие на эти, в зависимости от искусственных транзакций, которые были назначены узлу:</span><span class="sxs-lookup"><span data-stu-id="b9f63-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="b9f63-187">Регистрация IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="b9f63-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="b9f63-188">Чтобы просмотреть искусственные транзакции в алфавитном порядке, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b9f63-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="b9f63-189">Чтобы убедиться, что узел-watcher создан, введите следующую команду в командной оболочке Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="b9f63-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="b9f63-190">Вы получите сведения, похожие на эти:</span><span class="sxs-lookup"><span data-stu-id="b9f63-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="b9f63-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span><span class="sxs-lookup"><span data-stu-id="b9f63-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="b9f63-192">ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN Test; Te...}</span><span class="sxs-lookup"><span data-stu-id="b9f63-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="b9f63-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="b9f63-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="b9f63-194">Эта команда будет тестировать каждый узел-watcher в развертывании и подтверждать, выполнены ли следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b9f63-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="b9f63-195">Установлена необходимая роль регистратора</span><span class="sxs-lookup"><span data-stu-id="b9f63-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="b9f63-196">Создается необходимый ключ реестра (завершится при Set-CsWatcherNodeConfiguration управления)</span><span class="sxs-lookup"><span data-stu-id="b9f63-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="b9f63-197">На серверах работает правильная версия Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b9f63-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="b9f63-198">Порты настроены правильно</span><span class="sxs-lookup"><span data-stu-id="b9f63-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="b9f63-199">Назначенная тестовая учетная возможность пользователей имеет необходимые учетные данные</span><span class="sxs-lookup"><span data-stu-id="b9f63-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="b9f63-200">Управление узлами-наблюдателями</span><span class="sxs-lookup"><span data-stu-id="b9f63-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="b9f63-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="b9f63-201"><a name="testuser"> </a></span></span>

<span data-ttu-id="b9f63-202">Помимо изменения искусственных транзакций, которые выполняются на узле-watcher,  можно также использовать для выполнения двух других важных задач: включение и отключение узла-watcher, а также настройку узла-watcher для использования внутренних или внешних ВЕБ-URL-адресов при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="b9f63-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="b9f63-203">По умолчанию узлы-наблюдатели периодически запускают все включенные искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="b9f63-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="b9f63-204">Однако иногда может потребоваться приостановить эти транзакции.</span><span class="sxs-lookup"><span data-stu-id="b9f63-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="b9f63-205">Например, если узел-наблюдатель временно отключился от сети, у него больше нет причин запускать искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="b9f63-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="b9f63-206">Без сетевого подключения эти транзакции не будут работать.</span><span class="sxs-lookup"><span data-stu-id="b9f63-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="b9f63-207">Чтобы временно отключить узел-watcher, в командной оболочке Skype для бизнеса Server запустите команду, аналогичную этой:</span><span class="sxs-lookup"><span data-stu-id="b9f63-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="b9f63-208">Эта команда отключит выполнение искусственных транзакций на узле-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b9f63-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="b9f63-209">Чтобы возобновить выполнение искусственных транзакций, снова задайте для свойства Enabled значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="b9f63-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="b9f63-210">Свойство Enabled может использоваться для включения или отключения узлов-наблюдателей.</span><span class="sxs-lookup"><span data-stu-id="b9f63-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="b9f63-211">Если нет необходимости временно удалять узел-наблюдатель, используйте командлет **Remove-CsWatcherNodeConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="b9f63-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="b9f63-212">Эта команда удаляет все параметры конфигурации узла-watcher с указанного компьютера, что не позволяет компьютеру автоматически запускать искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="b9f63-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="b9f63-213">Однако команда не будет удалить файлы агента System Center или системные файлы Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b9f63-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="b9f63-214">По умолчанию узлы-пользователи-watcher используют внешние ВЕБ-URL-адреса организации при проведении тестов.</span><span class="sxs-lookup"><span data-stu-id="b9f63-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="b9f63-215">Однако узлы-пользователи-watcher также могут быть настроены для использования внутренних URL-адресов веб-сайтов организации.</span><span class="sxs-lookup"><span data-stu-id="b9f63-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="b9f63-216">Это позволит администраторам проверить доступ к URL-адресам тех пользователей, которые находятся внутри сети периметра.</span><span class="sxs-lookup"><span data-stu-id="b9f63-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="b9f63-217">Чтобы настроить узел-watcher на использование внутренних URL-адресов вместо внешних URL-адресов, установите для свойства UseInternalWebURls $True:</span><span class="sxs-lookup"><span data-stu-id="b9f63-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="b9f63-218">Сброс этого свойства до значения по умолчанию False ($False) приведет к повторному использованию внешними URL-адресами для watcher:</span><span class="sxs-lookup"><span data-stu-id="b9f63-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="b9f63-219">Специальные инструкции по установке для искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="b9f63-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="b9f63-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="b9f63-220"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="b9f63-221">Большинство искусственных транзакций могут запускаться на узле-watcher как есть.</span><span class="sxs-lookup"><span data-stu-id="b9f63-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="b9f63-222">В большинстве случаев, как только искусственная транзакция добавляется в параметры конфигурации узла-watcher, узел-watcher может начать использовать эту искусственную транзакцию во время тестирования.</span><span class="sxs-lookup"><span data-stu-id="b9f63-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="b9f63-223">Однако некоторые искусственные транзакции требуют специальных инструкций по настройке, как было рассмотрено в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b9f63-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="b9f63-224">Искусственная транзакция для видеоконференций</span><span class="sxs-lookup"><span data-stu-id="b9f63-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="b9f63-225">Если компьютер узла-watcher находится за пределами сети периметра, возможно, вы не сможете запустить искусственную транзакцию для передачи данных, если только не отключите параметры прокси-сервера браузера Windows Internet Explorer® для учетной записи сетевой службы, выполив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b9f63-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="b9f63-226">На компьютере узла-watcher нажмите кнопку "Начните", щелкните "Все программы", выберите "Программы доступа", щелкните правой кнопкой мыши командную подсказку **и** выберите команду "Запуск от прав **администратора".**   </span><span class="sxs-lookup"><span data-stu-id="b9f63-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="b9f63-227">В окне консоли введите следующую команду и нажмите ввод.</span><span class="sxs-lookup"><span data-stu-id="b9f63-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="b9f63-228">В командном окне отобразилось следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="b9f63-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="b9f63-229">BITSAdmin является неподдергодным и не гарантируется, что будет доступен в будущих версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="b9f63-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="b9f63-230">Средства администрирования для службы BITS теперь предоставляются с помощью bitS PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9f63-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="b9f63-231">Параметры прокси-сервера Интернета для учетной записи NetworkService NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="b9f63-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="b9f63-232">(подключение = по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b9f63-232">(connection = default)</span></span>
  
<span data-ttu-id="b9f63-233">Это сообщение означает, что вы отключили параметры прокси-сервера Internet Explorer для учетной записи сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="b9f63-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="b9f63-234">Искусственная транзакция единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="b9f63-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="b9f63-235">Искусственная транзакция единой системы обмена сообщениями Exchange проверяет, могут ли тестовые пользователи подключаться к учетным записям голосовой почты, которые есть в Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9f63-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="b9f63-236">Тестовые пользователи должны быть предварительно сконфигурированы с помощью учетных записей голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="b9f63-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="b9f63-237">Искусственная транзакция сохраняемой беседы</span><span class="sxs-lookup"><span data-stu-id="b9f63-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="b9f63-238">Чтобы использовать искусственную транзакцию сохраняемого чата, необходимо сначала создать канал и предоставить тест-пользователям разрешения на его использование.</span><span class="sxs-lookup"><span data-stu-id="b9f63-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="b9f63-239">Для настройки этого канала можно использовать искусственную транзакцию Persistent Chat:</span><span class="sxs-lookup"><span data-stu-id="b9f63-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="b9f63-240">Эту задачу установки необходимо запустить внутри предприятия:</span><span class="sxs-lookup"><span data-stu-id="b9f63-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="b9f63-241">При запуске с компьютера, не на который выполняется сервер, пользователь, выполнивший этот запуск, должен быть членом роли CsPersistentChatAdministrators для Role-Based Access Control (RBAC).</span><span class="sxs-lookup"><span data-stu-id="b9f63-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="b9f63-242">При запуске с самого сервера пользователь, выполнивший этот запуск, должен быть членом группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b9f63-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="b9f63-243">Искусственная транзакция одноранговых вызовов STN</span><span class="sxs-lookup"><span data-stu-id="b9f63-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="b9f63-244">Искусственная транзакция Test-CsPstnPeerToPeerCall возможность совершения и получения вызовов через телефонную сеть общего звонков (STN).</span><span class="sxs-lookup"><span data-stu-id="b9f63-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="b9f63-245">Чтобы запустить эту искусственную транзакцию, необходимо настроить:</span><span class="sxs-lookup"><span data-stu-id="b9f63-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="b9f63-246">Два тестовых пользователя с включенной поддержкой UC (вызываемая и приемная).</span><span class="sxs-lookup"><span data-stu-id="b9f63-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="b9f63-247">Прямые входные номера для каждой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="b9f63-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="b9f63-248">Политики VoIP и маршруты голосовой почты, которые позволяют звонкам на номер приемник достигать шлюза STN.</span><span class="sxs-lookup"><span data-stu-id="b9f63-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="b9f63-249">Шлюз STN, который принимает вызовы и носители, которые будут перенапорять вызовы обратно в домашний пул приемник в зависимости от набраного номера.</span><span class="sxs-lookup"><span data-stu-id="b9f63-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="b9f63-250">Искусственная транзакция единого магазина контактов</span><span class="sxs-lookup"><span data-stu-id="b9f63-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="b9f63-251">Искусственная транзакция единого магазина контактов проверяет возможность Skype для бизнеса Server получать контакты от имени пользователя из Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9f63-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="b9f63-252">Чтобы использовать эту искусственную транзакцию, следует выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="b9f63-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="b9f63-253">Lyss-Exchange необходимо настроить проверку подлинности между серверами.</span><span class="sxs-lookup"><span data-stu-id="b9f63-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="b9f63-254">У тестовых пользователей должен быть действительный почтовый ящик Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9f63-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="b9f63-255">После этого можно выполнить следующий Windows PowerShell для переноса списков контактов тестовых пользователей в Exchange:</span><span class="sxs-lookup"><span data-stu-id="b9f63-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="b9f63-256">Миграция тестовых списков контактов пользователей в Exchange может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="b9f63-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="b9f63-257">Для отслеживания хода миграции можно запустить ту же командную строку без флага -Setup:</span><span class="sxs-lookup"><span data-stu-id="b9f63-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="b9f63-258">Эта командная строка завершится успешно после завершения миграции.</span><span class="sxs-lookup"><span data-stu-id="b9f63-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="b9f63-259">Искусственная транзакция XMPP</span><span class="sxs-lookup"><span data-stu-id="b9f63-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="b9f63-260">Искусственная транзакция обмена мгновенными сообщениями XMPP требует настройки функции XMPP с одним или более федерационными доменами.</span><span class="sxs-lookup"><span data-stu-id="b9f63-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="b9f63-261">Чтобы включить искусственную транзакцию XMPP, необходимо предоставить параметр XmppTestReceiverMailAddress с учетной записью пользователя в домене XMPP с маршрутией.</span><span class="sxs-lookup"><span data-stu-id="b9f63-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="b9f63-262">Пример:</span><span class="sxs-lookup"><span data-stu-id="b9f63-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="b9f63-263">В этом примере потребуется правило Skype для бизнеса Server, чтобы отправлять сообщения для litwareinc.com на шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="b9f63-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="b9f63-264">Шлюзы и прокси-серверы XMPP были доступны в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b9f63-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b9f63-265">Дополнительные сведения см. в переносе [федерации XMPP.](../migration/migrating-xmpp-federation.md)</span><span class="sxs-lookup"><span data-stu-id="b9f63-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="b9f63-266">Искусственная транзакция сервера видеосвязи (VIS)</span><span class="sxs-lookup"><span data-stu-id="b9f63-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="b9f63-267">Искусственная транзакция сервера видеосвязи (VIS) требует загрузки и установки файлов поддержки искусственных транзакций[ (VISSTSupportPackage.msi). ](https://www.microsoft.com/download/details.aspx?id=46921)</span><span class="sxs-lookup"><span data-stu-id="b9f63-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="b9f63-268">Чтобы установить VISSTSupportPackage.msi убедитесь, что зависимости (в соответствии с требованиями к системе) для MSI уже установлены.</span><span class="sxs-lookup"><span data-stu-id="b9f63-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="b9f63-269">Запустите VISSTSupportPackage.msi, чтобы выполнить простую установку.</span><span class="sxs-lookup"><span data-stu-id="b9f63-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="b9f63-270">MSI устанавливает все файлы по следующему пути: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span><span class="sxs-lookup"><span data-stu-id="b9f63-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="b9f63-271">Дополнительные сведения о запуске искусственной транзакции VIS см. в документации по [cmdlet Test-CsP2PVideoInteropServerSipTrunkAV.](https://technet.microsoft.com/library/dn985894.aspx)</span><span class="sxs-lookup"><span data-stu-id="b9f63-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="b9f63-272">Изменение частоты запуска искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="b9f63-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="b9f63-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="b9f63-273"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="b9f63-274">По умолчанию искусственные транзакции будут запускаться с настроенными пользователями каждые 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b9f63-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="b9f63-275">Искусственные транзакции последовательно запускаются в наборе пользователей, чтобы избежать конфликта двух искусственных транзакций друг с другом.</span><span class="sxs-lookup"><span data-stu-id="b9f63-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="b9f63-276">Для выполнения всех искусственных транзакций требуется более длительный интервал.</span><span class="sxs-lookup"><span data-stu-id="b9f63-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="b9f63-277">Если требуется чаще запускать искусственные транзакции, число искусственных транзакций, запускаемых с заданным набором пользователей, должно быть уменьшено, чтобы тесты могли быть завершены в нужном диапазоне времени с некоторым буфером для периодических сетевых задержек.</span><span class="sxs-lookup"><span data-stu-id="b9f63-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="b9f63-278">Если необходимо выполнить дополнительные искусственные транзакции, создайте дополнительные наборы пользователей для запуска дополнительных искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="b9f63-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="b9f63-279">Чтобы изменить частоту запуска искусственных транзакций, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b9f63-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="b9f63-280">Откройте System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b9f63-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="b9f63-281">Щелкните раздел "Автор".</span><span class="sxs-lookup"><span data-stu-id="b9f63-281">Click Authoring section.</span></span> <span data-ttu-id="b9f63-282">Раздел "Правила нажатия" (в разделе "Авторинг")</span><span class="sxs-lookup"><span data-stu-id="b9f63-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="b9f63-283">В разделе "Правила" найдите правило с именем "Main Synthetic Transaction Runner Performance Collection Rule"</span><span class="sxs-lookup"><span data-stu-id="b9f63-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="b9f63-284">Щелкните правило правой кнопкой мыши и выберите "Переопределения", выберите "Переопредить правило", а затем выберите "Для всех объектов класса: просмотр пула"</span><span class="sxs-lookup"><span data-stu-id="b9f63-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="b9f63-285">В окне "Переопределения свойств" выберите имя параметра "Частота" и задав нужное значение переопределения.</span><span class="sxs-lookup"><span data-stu-id="b9f63-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="b9f63-286">В том же окне выберите пакет управления, к которому необходимо применить это переопределения</span><span class="sxs-lookup"><span data-stu-id="b9f63-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="b9f63-287">Использование подробного журнала для искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="b9f63-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="b9f63-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="b9f63-288"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="b9f63-289">Искусственные транзакции кажутся очень полезными при определении проблем с системой.</span><span class="sxs-lookup"><span data-stu-id="b9f63-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="b9f63-290">Например, Test-CsRegistration может оповещать администраторов о том, что пользователи с трудом регистрируются в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b9f63-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="b9f63-291">Однако для определения фактической причины сбоя могут потребоваться дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="b9f63-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="b9f63-292">По этой причине искусственные транзакции предоставляют богатый объем ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="b9f63-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="b9f63-293">В результате ведения журнала для каждого действия, которое осуществляется искусственной транзакцией, записываются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="b9f63-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="b9f63-294">Время начала действия.</span><span class="sxs-lookup"><span data-stu-id="b9f63-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="b9f63-295">Время завершения действия.</span><span class="sxs-lookup"><span data-stu-id="b9f63-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="b9f63-296">Выполненное действие (например, создание, присоединение или выход из конференции, вход в Skype для бизнеса Server; отправка мгновенного сообщения).</span><span class="sxs-lookup"><span data-stu-id="b9f63-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="b9f63-297">Информационные, подробные сообщения, предупреждения или сообщения об ошибках, которые были созданы при выполнении операции</span><span class="sxs-lookup"><span data-stu-id="b9f63-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="b9f63-298">Сообщения о регистрации SIP.</span><span class="sxs-lookup"><span data-stu-id="b9f63-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="b9f63-299">Записи исключений или коды диагностики, созданные при окнаности действия.</span><span class="sxs-lookup"><span data-stu-id="b9f63-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="b9f63-300">Net result of running the activity.</span><span class="sxs-lookup"><span data-stu-id="b9f63-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="b9f63-301">Эти сведения создаются автоматически при каждом запуске искусственной транзакции, но не отображаются автоматически или не сохраняются в файле журнала.</span><span class="sxs-lookup"><span data-stu-id="b9f63-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="b9f63-302">Если искусственная транзакция запущена вручную, можно использовать параметр OutLoggerVariable, чтобы указать переменную Windows PowerShell, в которой будут храниться сведения.</span><span class="sxs-lookup"><span data-stu-id="b9f63-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="b9f63-303">Здесь можно использовать один из двух методов сохранения и/или просмотра сообщений об ошибках в формате XML или HTML.</span><span class="sxs-lookup"><span data-stu-id="b9f63-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="b9f63-304">Чтобы получить сведения об устранении неполадок, укажите параметр OutLoggerVariable, а затем выберите имя переменной:</span><span class="sxs-lookup"><span data-stu-id="b9f63-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="b9f63-305">: не преисоставить имя переменной с помощью символа $.</span><span class="sxs-lookup"><span data-stu-id="b9f63-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="b9f63-306">Используйте имя переменной, например RegistrationTest (не $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="b9f63-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="b9f63-307">При запуске этой команды вы увидите выходные данные, аналогичные:</span><span class="sxs-lookup"><span data-stu-id="b9f63-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="b9f63-308">Целевое Fqdn : atl-cs-001.litwareinc.com result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span><span class="sxs-lookup"><span data-stu-id="b9f63-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="b9f63-309">Диагностика: вы можете получить доступ к гораздо более подробным сведениям об этом сбое, чем к показанным здесь сообщениям об ошибке.</span><span class="sxs-lookup"><span data-stu-id="b9f63-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="b9f63-310">Чтобы получить доступ к этим сведениям в формате HTML, используйте команду, аналогичную этой, чтобы сохранить данные, хранимые в переменной RegistrationTest, в HTML-файл:</span><span class="sxs-lookup"><span data-stu-id="b9f63-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="b9f63-311">Можно также использовать метод ToXML() для сохранения данных в файл XML:</span><span class="sxs-lookup"><span data-stu-id="b9f63-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="b9f63-312">Эти файлы можно просмотреть с помощью Windows Internet Explorer, Microsoft Visual Studio или любого другого приложения, которое может открывать HTML-или XML-файлы.</span><span class="sxs-lookup"><span data-stu-id="b9f63-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="b9f63-313">Искусственные транзакции, которые запускаются изнутри System Center Operations Manager, автоматически создают эти файлы журналов для сбоев.</span><span class="sxs-lookup"><span data-stu-id="b9f63-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="b9f63-314">Эти журналы не будут созданы, если выполнение не удастся, прежде чем Skype для бизнеса Server PowerShell сможет загрузить и запустить искусственную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="b9f63-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b9f63-315">По умолчанию Skype для бизнеса Server сохраняет файлы журналов в папку, доступ к которая не является общей.</span><span class="sxs-lookup"><span data-stu-id="b9f63-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="b9f63-316">Чтобы сделать эти журналы доступными, необходимо поделиться этой папкой.</span><span class="sxs-lookup"><span data-stu-id="b9f63-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="b9f63-317">Например: \\ atl-watcher-001.litwareinc.com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="b9f63-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
