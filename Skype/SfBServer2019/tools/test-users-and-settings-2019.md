---
title: Настройка тестовых пользователей и параметров узлов просмотра
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
description: Сводка. Настройте тестовые учетные записи пользователей и параметры узлов просмотра для синтетических транзакций Skype для бизнес-сервера.
ms.openlocfilehash: fc581b5f9624d28e8cbeb906832dfcfba3fd19dd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120368"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="0b514-103">Настройка тестовых пользователей и параметров узлов просмотра</span><span class="sxs-lookup"><span data-stu-id="0b514-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="0b514-104">**Сводка:** Настройка тестовых учетных записей пользователей и параметров узлов просмотра для синтетических транзакций Skype для бизнес-сервера.</span><span class="sxs-lookup"><span data-stu-id="0b514-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="0b514-105">Настроив компьютер, который будет выступать в качестве узла-наблюдателя, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0b514-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="0b514-106">[Настройте тестовые учетные записи](test-users-and-settings-2019.md#testuser) пользователей, которые будут использоваться этими узлами просмотра.</span><span class="sxs-lookup"><span data-stu-id="0b514-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="0b514-107">Если вы используете проверку подлинности согласованием, вам также необходимо выполнить командлет **Set-CsTestUserCredential**, чтобы разрешить использование этих учетных записей узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="0b514-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="0b514-108">Обновите параметры конфигурации узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="0b514-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="0b514-109">Настройка учетных записей тестовых пользователей</span><span class="sxs-lookup"><span data-stu-id="0b514-109">Configure Test User Accounts</span></span>
<span data-ttu-id="0b514-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="0b514-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="0b514-111">Тестовые учетные записи не должны представлять реальных людей, но они должны быть действительными учетными записями Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0b514-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="0b514-112">Кроме того, эти учетные записи должны быть включены для Skype для бизнеса Server, они должны иметь действительные SIP-адреса, и они должны быть включены для Корпоративная голосовая связь (для использования Test-CsPstnPeerToPeerCall синтетической транзакции).</span><span class="sxs-lookup"><span data-stu-id="0b514-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="0b514-113">Если вы используете метод проверки подлинности TrustedServer, все, что вам нужно сделать, это убедиться, что эти учетные записи существуют и настроить их, как отмечено.</span><span class="sxs-lookup"><span data-stu-id="0b514-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="0b514-114">Для каждого пула, который необходимо протестировать, необходимо назначить не менее трех тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="0b514-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="0b514-115">Если используется метод проверки подлинности Negotiate, необходимо также использовать Set-CsTestUserCredential и оболочку управления Skype для бизнес-серверов, чтобы эти тестовые учетные записи могли работать с синтетическими транзакциями.</span><span class="sxs-lookup"><span data-stu-id="0b514-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="0b514-116">Делайте это, запуская команду, аналогичную следующей (эти команды предполагают, что созданы три учетные записи пользователей Active Directory и что эти учетные записи включены для Skype для бизнеса Server):</span><span class="sxs-lookup"><span data-stu-id="0b514-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="0b514-117">Необходимо включить не только SIP-адрес, но и имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="0b514-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="0b514-118">Если пароль не включен, Set-CsTestUserCredential будет предложено ввести эту информацию.</span><span class="sxs-lookup"><span data-stu-id="0b514-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="0b514-119">Имя пользователя можно укаварить с помощью формата имя домена\имя пользователя, показанного в предыдущем блоке кода.</span><span class="sxs-lookup"><span data-stu-id="0b514-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="0b514-120">Чтобы убедиться в том, что тестовые учетные данные пользователей были созданы, запустите эти команды из командной оболочки Skype для бизнес-серверов:</span><span class="sxs-lookup"><span data-stu-id="0b514-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="0b514-121">Сведения, аналогичные этому, будут возвращены каждому пользователю:</span><span class="sxs-lookup"><span data-stu-id="0b514-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="0b514-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="0b514-122">**UserName**</span></span>|<span data-ttu-id="0b514-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="0b514-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b514-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="0b514-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="0b514-125">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="0b514-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="0b514-126">Настройка базового узла для просмотра с помощью синтетических транзакций по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0b514-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="0b514-127">После создания тестовых пользователей можно создать узел просмотра с помощью команды, похожей на эту:</span><span class="sxs-lookup"><span data-stu-id="0b514-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="0b514-128">Эта команда создает узел-наблюдатель с параметрами по умолчанию, который выполняет набор искусственных транзакций по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b514-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="0b514-129">Для нового узла-наблюдателя используются тестовые пользователи watcher1@litwareinc.com, watcher2@litwareinc.com и watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="0b514-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="0b514-130">Если узел просмотра использует проверку подлинности TrustedServer, эти три тестовые учетные записи могут быть любыми допустимой учетной записью пользователя, включенной для Active Directory и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b514-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="0b514-131">Если узел просмотра использует метод проверки подлинности Negotiate, эти учетные записи пользователей также должны быть включены для узла просмотра с помощью Set-CsTestUserCredential cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0b514-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="0b514-132">Чтобы проверить, что автоматическое обнаружение целевого пула для регистрации настроено правильно, а не нацелившись непосредственно на пул, используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0b514-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="0b514-133">Настройка расширенных тестов</span><span class="sxs-lookup"><span data-stu-id="0b514-133">Configuring Extended Tests</span></span>

<span data-ttu-id="0b514-134">Если вы хотите включить тест PSTN, который проверяет подключение к сети общедоступных переключеных телефонов, необходимо сделать некоторую дополнительную конфигурацию при настройке узла просмотра.</span><span class="sxs-lookup"><span data-stu-id="0b514-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="0b514-135">Сначала необходимо связать тестовых пользователей с типом тестирования PSTN, запуская команду, аналогичную этой, из командной оболочки Skype для бизнес-серверов:</span><span class="sxs-lookup"><span data-stu-id="0b514-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="0b514-136">Результаты этой команды должны храниться в переменной.</span><span class="sxs-lookup"><span data-stu-id="0b514-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="0b514-137">В этом примере переменная называется $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="0b514-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="0b514-138">Далее можно использовать комлет **New-CsWatcherNodeConfiguration,** чтобы связать тип теста (хранимый в переменной $pstnTest) с пулом Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b514-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="0b514-139">Например, следующая команда создает новую конфигурацию узла просмотра для пула atl-cs-001.litwareinc.com, добавляя трех тестовых пользователей, созданных ранее, и добавляя тип теста PSTN:</span><span class="sxs-lookup"><span data-stu-id="0b514-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="0b514-140">При не установке базовых файлов Skype для бизнес-сервера и базы данных RTCLocal на компьютере узла просмотра предыдущей команды сбой.</span><span class="sxs-lookup"><span data-stu-id="0b514-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="0b514-141">Чтобы протестировать несколько голосовых политик, можно создать расширенный тест для каждой политики с помощью cmdlet **New-CsExtendedTest.**</span><span class="sxs-lookup"><span data-stu-id="0b514-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="0b514-142">Предоставленные пользователи должны быть настроены с помощью нужных голосовых политик.</span><span class="sxs-lookup"><span data-stu-id="0b514-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="0b514-143">Расширенные тесты передаются в **cmdlet New-CsWatcherNodeConfiguration** с помощью запятой-делимитеров, таких как:</span><span class="sxs-lookup"><span data-stu-id="0b514-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="0b514-144">-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="0b514-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="0b514-145">Так как кодлет **New-CsWatcherNodeConfiguration** был вызван без использования параметра Tests, для нового узла просмотра будут включены только синтетические транзакции по умолчанию (и указанная расширенная синтетическая транзакция).</span><span class="sxs-lookup"><span data-stu-id="0b514-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="0b514-146">Таким образом, узел просмотра будет тестировать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="0b514-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="0b514-147">Registration</span><span class="sxs-lookup"><span data-stu-id="0b514-147">Registration</span></span>
    
- <span data-ttu-id="0b514-148">"IM" (Обмен мгновенными сообщениями);</span><span class="sxs-lookup"><span data-stu-id="0b514-148">IM</span></span>
    
- <span data-ttu-id="0b514-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="0b514-149">GroupIM</span></span>
    
- <span data-ttu-id="0b514-150">P2PAV (одноранговые аудио- и видеосеансы)</span><span class="sxs-lookup"><span data-stu-id="0b514-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="0b514-151">AvConference (аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="0b514-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="0b514-152">Присутствие</span><span class="sxs-lookup"><span data-stu-id="0b514-152">Presence</span></span>
    
- <span data-ttu-id="0b514-153">ABS (служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="0b514-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="0b514-154">ABWQ (веб-служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="0b514-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="0b514-155">Следующие компоненты не будут протестироваться по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="0b514-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="0b514-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="0b514-156">ASConference</span></span>
    
- <span data-ttu-id="0b514-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="0b514-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="0b514-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="0b514-158">DataConference</span></span>
    
- <span data-ttu-id="0b514-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="0b514-159">DialinConferencing</span></span>
    
- <span data-ttu-id="0b514-160">ExumConnectivity (единая система обмена сообщениями Exchange)</span><span class="sxs-lookup"><span data-stu-id="0b514-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="0b514-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="0b514-161">JoinLauncher</span></span>
    
- <span data-ttu-id="0b514-162">MCXP2PIM (устаревший обмен мгновенными сообщениями на мобильных устройствах)</span><span class="sxs-lookup"><span data-stu-id="0b514-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="0b514-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="0b514-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="0b514-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="0b514-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="0b514-165">PSTN (вызовы шлюза PSTN, указанные в качестве расширенного теста)</span><span class="sxs-lookup"><span data-stu-id="0b514-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="0b514-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="0b514-166">UcwaConference</span></span>
    
- <span data-ttu-id="0b514-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="0b514-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="0b514-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="0b514-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="0b514-169">Добавление и удаление искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="0b514-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="0b514-170">После настройки узла-наблюдателя вы можете добавлять искусственные транзакции на узел-наблюдатель или удалять их с узла-наблюдателя с помощью командлета Set-CsWatcherNodeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="0b514-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="0b514-171">Например, чтобы добавить тест PersistentChatMessage на узел-наблюдатель, используйте следующую команду с методом Add.</span><span class="sxs-lookup"><span data-stu-id="0b514-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="0b514-172">При указании нескольких тестов используйте запятые.</span><span class="sxs-lookup"><span data-stu-id="0b514-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="0b514-173">Пример:</span><span class="sxs-lookup"><span data-stu-id="0b514-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="0b514-174">Ошибка будет возникать, если один или несколько из этих тестов (например, DataConference) уже включены в узел просмотра.</span><span class="sxs-lookup"><span data-stu-id="0b514-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="0b514-175">В этом случае вы получите следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="0b514-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="0b514-176">Set-CsWatcherNodeConfiguration. Существует дублирующая последовательность ключей "DataConference" для ключа "urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName" или уникального ограничения удостоверений.</span><span class="sxs-lookup"><span data-stu-id="0b514-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="0b514-177">Если произошла эта ошибка, изменения не применяются.</span><span class="sxs-lookup"><span data-stu-id="0b514-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="0b514-178">Команду следует повторно запустить с удалением дубликата теста.</span><span class="sxs-lookup"><span data-stu-id="0b514-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="0b514-179">Чтобы удалить синтетическую транзакцию из узла просмотра, используйте метод Remove.</span><span class="sxs-lookup"><span data-stu-id="0b514-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="0b514-180">Например, следующая команда удаляет тест ABWQ с узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="0b514-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="0b514-181">Вы можете использовать метод Replace, чтобы заменить все тесты, включенные в настоящее время, одним или более новыми тестами.</span><span class="sxs-lookup"><span data-stu-id="0b514-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="0b514-182">Например, если вы хотите, чтобы узел просмотра только запускал тест im, вы можете настроить его с помощью этой команды:</span><span class="sxs-lookup"><span data-stu-id="0b514-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="0b514-183">При запуске этой команды все синтетические транзакции на указанном узле просмотра будут отключены, за исключением im.</span><span class="sxs-lookup"><span data-stu-id="0b514-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="0b514-184">Просмотр и тестирование конфигурации узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="0b514-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="0b514-185">Чтобы просмотреть тесты, назначенные узлу-наблюдателю, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="0b514-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="0b514-186">Эта команда возвращает сведения, аналогичные этому, в зависимости от синтетической транзакции, назначенной узлу:</span><span class="sxs-lookup"><span data-stu-id="0b514-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="0b514-187">Регистрация IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span><span class="sxs-lookup"><span data-stu-id="0b514-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="0b514-188">Чтобы просмотреть искусственные транзакции в алфавитном порядке, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="0b514-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="0b514-189">Чтобы убедиться, что узел для просмотра создан, введите следующую команду из командной оболочки Skype для бизнес-серверов:</span><span class="sxs-lookup"><span data-stu-id="0b514-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="0b514-190">Вы получите сведения, похожие на эту:</span><span class="sxs-lookup"><span data-stu-id="0b514-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="0b514-191">Identity : atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="0b514-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="0b514-192">ExtendedTests: {TestUsers=IList<System.String>; Тест Name=PSTN; Te...}</span><span class="sxs-lookup"><span data-stu-id="0b514-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="0b514-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To убедитесь, что узел для просмотра настроен правильно, введите следующую команду из командной оболочки Skype для бизнес-серверов:</span><span class="sxs-lookup"><span data-stu-id="0b514-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="0b514-194">Эта команда протестировать каждый узел просмотра в развертывании и проверить, завершены ли следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0b514-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="0b514-195">Установлена роль обязательного регистратора</span><span class="sxs-lookup"><span data-stu-id="0b514-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="0b514-196">Создается необходимый ключ реестра (завершаемая при Set-CsWatcherNodeConfiguration)</span><span class="sxs-lookup"><span data-stu-id="0b514-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="0b514-197">На ваших серверах запущена правильная версия Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0b514-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="0b514-198">Порты настроены правильно</span><span class="sxs-lookup"><span data-stu-id="0b514-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="0b514-199">Назначенные тестовые пользователи имеют необходимые учетные данные</span><span class="sxs-lookup"><span data-stu-id="0b514-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="0b514-200">Управление узлами-наблюдателями</span><span class="sxs-lookup"><span data-stu-id="0b514-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="0b514-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="0b514-201"><a name="testuser"> </a></span></span>

<span data-ttu-id="0b514-202">Кроме изменения синтетических транзакций, которые выполняются на узле просмотра, вы также можете использовать комлет **Set-CsWatcherNodeConfiguration** для выполнения двух других важных задач: включения и отключения узла просмотра и настройки узла просмотра для использования внутренних URL-адресов веб-сайтов или внешних ВЕБ-адресов при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="0b514-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="0b514-203">По умолчанию узлы-наблюдатели периодически запускают все включенные искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="0b514-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="0b514-204">Однако иногда может потребоваться приостановить эти транзакции.</span><span class="sxs-lookup"><span data-stu-id="0b514-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="0b514-205">Например, если узел-наблюдатель временно отключился от сети, у него больше нет причин запускать искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="0b514-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="0b514-206">Без подключения к сети эти транзакции не будут работать.</span><span class="sxs-lookup"><span data-stu-id="0b514-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="0b514-207">Чтобы временно отключить узел просмотра, запустите команду, аналогичную этой, из командной оболочки Skype для бизнес-серверов:</span><span class="sxs-lookup"><span data-stu-id="0b514-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="0b514-208">Эта команда отключит выполнение синтетических транзакций в сторожевом узле atl watcher 001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="0b514-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="0b514-209">Чтобы возобновить выполнение искусственных транзакций, снова задайте для свойства Enabled значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="0b514-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="0b514-210">Свойство Enabled может использоваться для включения или отключения узлов-наблюдателей.</span><span class="sxs-lookup"><span data-stu-id="0b514-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="0b514-211">Если нет необходимости временно удалять узел-наблюдатель, используйте командлет **Remove-CsWatcherNodeConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="0b514-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="0b514-212">Эта команда удаляет все параметры конфигурации узла просмотра с указанного компьютера, что не позволяет компьютеру автоматически запускать синтетические транзакции.</span><span class="sxs-lookup"><span data-stu-id="0b514-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="0b514-213">Однако команда не будет удалить файлы агентов System Center или системные файлы Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b514-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="0b514-214">По умолчанию узлы просмотра используют внешние веб-URL-адреса организации при проведении тестов.</span><span class="sxs-lookup"><span data-stu-id="0b514-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="0b514-215">Однако узлы для просмотра также можно настроить для использования внутренних веб-URL-адресов организации.</span><span class="sxs-lookup"><span data-stu-id="0b514-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="0b514-216">Это позволит администраторам проверить доступ к URL-адресам тех пользователей, которые находятся внутри сети периметра.</span><span class="sxs-lookup"><span data-stu-id="0b514-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="0b514-217">Чтобы настроить узел просмотра для использования внутренних URL-адресов вместо внешних URL-адресов, установите свойство UseInternalWebURls true ($True):</span><span class="sxs-lookup"><span data-stu-id="0b514-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="0b514-218">Сброс этого свойства к значению false ($False) приведет к тому, что он снова будет использовать внешние URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="0b514-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="0b514-219">Специальные инструкции по установке для искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="0b514-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="0b514-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="0b514-220"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="0b514-221">Большинство синтетических транзакций может работать на узле просмотра как есть.</span><span class="sxs-lookup"><span data-stu-id="0b514-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="0b514-222">В большинстве случаев, как только синтетическая транзакция добавляется в параметры конфигурации узла просмотра, узел просмотра может приступить к использованию этой синтетической транзакции во время ее тестовых пропусков.</span><span class="sxs-lookup"><span data-stu-id="0b514-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="0b514-223">Однако существуют некоторые синтетические транзакции, которые требуют специальных инструкций по настройке, как это было рассмотрено в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="0b514-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="0b514-224">Синтетическая транзакция для конференций данных</span><span class="sxs-lookup"><span data-stu-id="0b514-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="0b514-225">Если ваш узел просмотра находится за пределами сети периметра, вы, вероятно, не сможете выполнить синтетическую транзакцию по конференциям данных, если сначала не отключите параметры прокси-сервера браузера Windows для учетной записи сетевой службы® завершив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0b514-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="0b514-226">На компьютере узла просмотра нажмите кнопку **Начните,** нажмите кнопку Все **программы,** щелкните Аксессуары, щелкните правой кнопкой **Командная** подсказка, а затем нажмите **кнопку Запустить в качестве администратора**.</span><span class="sxs-lookup"><span data-stu-id="0b514-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="0b514-227">В окне консоли введите следующую команду и нажмите кнопку ENTER.</span><span class="sxs-lookup"><span data-stu-id="0b514-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="0b514-228">В окне команды отображается следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="0b514-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="0b514-229">BITSAdmin является обесценителем и не гарантируется, что он будет доступен в будущих версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="0b514-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="0b514-230">Средства администрирования для службы BITS теперь предоставлены cmdlets BITS PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b514-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="0b514-231">Параметры прокси-сервера в Интернете для учетной записи NetworkService NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="0b514-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="0b514-232">(подключение = по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0b514-232">(connection = default)</span></span>
  
<span data-ttu-id="0b514-233">В этом сообщении указывается, что вы отключили параметры прокси-сервера Internet Explorer для учетной записи сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="0b514-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="0b514-234">Синтетическая транзакция exchange единой системы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="0b514-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="0b514-235">Синтетическая транзакция Exchange Unified Messaging (ЕДИНОЙ системы обмена сообщениями) проверяет, что проверяющие пользователи могут подключаться к учетным записям голосовой почты, которые были в Exchange.</span><span class="sxs-lookup"><span data-stu-id="0b514-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="0b514-236">Тестовые пользователи должны быть предварительно сконфигурированы с учетными записями голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="0b514-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="0b514-237">Сохраняемая синтетическая транзакция чата</span><span class="sxs-lookup"><span data-stu-id="0b514-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="0b514-238">Чтобы использовать синтетическую транзакцию Persistent Chat, сначала необходимо создать канал и предоставить тестующих пользователей разрешения на его использование.</span><span class="sxs-lookup"><span data-stu-id="0b514-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="0b514-239">Для настройки этого канала можно использовать синтетическую транзакцию Persistent Chat:</span><span class="sxs-lookup"><span data-stu-id="0b514-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="0b514-240">Необходимо выполнить эту задачу установки изнутри предприятия:</span><span class="sxs-lookup"><span data-stu-id="0b514-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="0b514-241">Если выполняется с несерверной машины, пользователь, который выполняет этот код, должен быть членом роли CsPersistentChatAdministrators для Role-Based управления доступом (RBAC).</span><span class="sxs-lookup"><span data-stu-id="0b514-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="0b514-242">При запуске с самого сервера пользователь, который выполняет этот код, должен быть членом группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0b514-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="0b514-243">Синтетическая транзакция PSTN одноранговых вызовов</span><span class="sxs-lookup"><span data-stu-id="0b514-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="0b514-244">Синтетическая транзакция Test-CsPstnPeerToPeerCall проверяет возможность разместить и принимать вызовы через общедоступные телефонные сети с переключениями (PSTN).</span><span class="sxs-lookup"><span data-stu-id="0b514-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="0b514-245">Чтобы выполнить эту синтетическую транзакцию, необходимо настроить:</span><span class="sxs-lookup"><span data-stu-id="0b514-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="0b514-246">Два тестовых пользователя с поддержкой UC (вызываемая и приемная).</span><span class="sxs-lookup"><span data-stu-id="0b514-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="0b514-247">Прямые входные номера для каждой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b514-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="0b514-248">Политики VoIP и маршруты голосовой почты, позволяющие вызовам на номер приемного телефона достичь шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="0b514-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="0b514-249">Шлюз PSTN, который принимает вызовы и носители, которые будут маршрутить вызовы обратно в домашний пул приемник в зависимости от набраного номера.</span><span class="sxs-lookup"><span data-stu-id="0b514-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="0b514-250">Синтетическая транзакция Единого магазина контактов</span><span class="sxs-lookup"><span data-stu-id="0b514-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="0b514-251">Синтетическая транзакция Единого магазина контактов проверяет возможность Skype для бизнес-сервера получать контакты от имени пользователя из Exchange.</span><span class="sxs-lookup"><span data-stu-id="0b514-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="0b514-252">Чтобы использовать эту искусственную транзакцию, следует выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="0b514-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="0b514-253">Lyss-Exchange сервер для проверки подлинности сервера необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="0b514-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="0b514-254">У тестовых пользователей должен быть допустимый почтовый ящик Exchange.</span><span class="sxs-lookup"><span data-stu-id="0b514-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="0b514-255">После того как эти условия будут выполнены, можно выполнить следующий Windows PowerShell для переноса списков контактов тестовых пользователей в Exchange:</span><span class="sxs-lookup"><span data-stu-id="0b514-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="0b514-256">Может потребоваться некоторое время, чтобы списки контактов тестовых пользователей мигрировали в Exchange.</span><span class="sxs-lookup"><span data-stu-id="0b514-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="0b514-257">Чтобы отслеживать ход миграции, можно запустить ту же командную строку без флага -Setup:</span><span class="sxs-lookup"><span data-stu-id="0b514-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="0b514-258">Эта командная строка завершится успешно после завершения миграции.</span><span class="sxs-lookup"><span data-stu-id="0b514-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="0b514-259">Синтетическая транзакция XMPP</span><span class="sxs-lookup"><span data-stu-id="0b514-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="0b514-260">Синтетическая транзакция по синтетическому протоколу обмена сообщениями и присутствия (XMPP) требует настройки функции XMPP с одним или более федерационными доменами.</span><span class="sxs-lookup"><span data-stu-id="0b514-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="0b514-261">Чтобы включить синтетическую транзакцию XMPP, необходимо предоставить параметр XmppTestReceiverMailAddress с учетной записью пользователя в маршрутивом домене XMPP.</span><span class="sxs-lookup"><span data-stu-id="0b514-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="0b514-262">Например:</span><span class="sxs-lookup"><span data-stu-id="0b514-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="0b514-263">В этом примере необходимо существовать правило Skype для бизнес-сервера для маршрутов сообщений для litwareinc.com к шлюзу XMPP.</span><span class="sxs-lookup"><span data-stu-id="0b514-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="0b514-264">Шлюзы и прокси-серверы XMPP были доступны в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0b514-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0b514-265">Дополнительные сведения см. в дополнительных сведениях о переносе федерации [XMPP.](../migration/migrating-xmpp-federation.md)</span><span class="sxs-lookup"><span data-stu-id="0b514-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="0b514-266">Синтетическая транзакция Video Interop Server (VIS)</span><span class="sxs-lookup"><span data-stu-id="0b514-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="0b514-267">Синтетическая транзакция Video Interop Server (VIS) требует скачивания и установки файлов поддержки синтетических[ транзакций (VISSTSupportPackage.msi). ](https://www.microsoft.com/download/details.aspx?id=46921)</span><span class="sxs-lookup"><span data-stu-id="0b514-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="0b514-268">Чтобы установить VISSTSupportPackage.msi, уже установлены зависимости (в соответствии с требованиями системы) для msi.</span><span class="sxs-lookup"><span data-stu-id="0b514-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="0b514-269">Запустите VISSTSupportPackage.msi, чтобы выполнить простую установку.</span><span class="sxs-lookup"><span data-stu-id="0b514-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="0b514-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span><span class="sxs-lookup"><span data-stu-id="0b514-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="0b514-271">Дополнительные сведения о запуске синтетической транзакции VIS см. в документации для [cmdlet Test-CsP2PVideoInteropServerSipTrunkAV.](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV)</span><span class="sxs-lookup"><span data-stu-id="0b514-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="0b514-272">Изменение частоты запуска для синтетических транзакций</span><span class="sxs-lookup"><span data-stu-id="0b514-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="0b514-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="0b514-273"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="0b514-274">По умолчанию синтетические транзакции будут запускаться с настроенными пользователями каждые 15 минут.</span><span class="sxs-lookup"><span data-stu-id="0b514-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="0b514-275">Синтетические транзакции последовательно запускаются в наборе пользователей, чтобы избежать конфликта двух синтетических транзакций друг с другом.</span><span class="sxs-lookup"><span data-stu-id="0b514-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="0b514-276">Для обеспечения времени выполнения всех синтетических транзакций требуется более длительный интервал.</span><span class="sxs-lookup"><span data-stu-id="0b514-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="0b514-277">Если желательно чаще запускать синтетические транзакции, количество синтетических транзакций, запускаемых с заданным набором пользователей, должно быть уменьшено, чтобы тесты могли завершиться в нужном диапазоне времени с некоторым буфером для случайных задержек сети.</span><span class="sxs-lookup"><span data-stu-id="0b514-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="0b514-278">Если желательно выполнить больше синтетических транзакций, создайте дополнительные наборы пользователей для запуска дополнительных синтетических транзакций.</span><span class="sxs-lookup"><span data-stu-id="0b514-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="0b514-279">Чтобы изменить частоту запуска синтетических транзакций, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0b514-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="0b514-280">Open System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="0b514-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="0b514-281">Щелкните Раздел Авторинг.</span><span class="sxs-lookup"><span data-stu-id="0b514-281">Click Authoring section.</span></span> <span data-ttu-id="0b514-282">Щелкните раздел Правила (в разделе Авторство)</span><span class="sxs-lookup"><span data-stu-id="0b514-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="0b514-283">В разделе Правила найдите правило с именем "Главное правило сбора производительности бегуна синтетических транзакций"</span><span class="sxs-lookup"><span data-stu-id="0b514-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="0b514-284">Щелкните правой кнопкой мыши правило и выберите переопределения, выберите Переопределять правило, а затем выберите "Для всех объектов класса: наблюдатель пула"</span><span class="sxs-lookup"><span data-stu-id="0b514-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="0b514-285">В окне Override Properties выберите имя параметра "Частота" и установите значение Переопределения к нужному.</span><span class="sxs-lookup"><span data-stu-id="0b514-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="0b514-286">В том же окне выберите пакет Управления, к которому необходимо применить этот переопределения</span><span class="sxs-lookup"><span data-stu-id="0b514-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="0b514-287">Использование подробного журнала для искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="0b514-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="0b514-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="0b514-288"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="0b514-289">Синтетические транзакции очень полезны для выявления проблем с системой.</span><span class="sxs-lookup"><span data-stu-id="0b514-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="0b514-290">Например, этот Test-CsRegistration может предупреждать администраторов о том, что пользователи с трудом регистрируются в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0b514-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="0b514-291">Однако для определения фактической причины сбоя могут потребоваться дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="0b514-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="0b514-292">По этой причине синтетические транзакции обеспечивают богатый журнал.</span><span class="sxs-lookup"><span data-stu-id="0b514-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="0b514-293">При богатом журнале для каждого действия, которое проводит синтетическая транзакция, записывают следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="0b514-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="0b514-294">Время начала действия.</span><span class="sxs-lookup"><span data-stu-id="0b514-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="0b514-295">Время завершения действия.</span><span class="sxs-lookup"><span data-stu-id="0b514-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="0b514-296">Выполненное действие (например, создание, присоединение или выход из конференции; вход в Skype для бизнеса Server; отправка мгновенных сообщений).</span><span class="sxs-lookup"><span data-stu-id="0b514-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="0b514-297">Информационные, подробные сообщения, предупреждения или сообщения об ошибках, которые были созданы при выполнении операции</span><span class="sxs-lookup"><span data-stu-id="0b514-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="0b514-298">Сообщения регистрации SIP.</span><span class="sxs-lookup"><span data-stu-id="0b514-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="0b514-299">Записи исключений или диагностические коды, созданные при действии.</span><span class="sxs-lookup"><span data-stu-id="0b514-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="0b514-300">Чистый результат запуска действия.</span><span class="sxs-lookup"><span data-stu-id="0b514-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="0b514-301">Эти сведения автоматически создаются при каждом запуске синтетической транзакции, но не отображаются автоматически и не сохраняются в файле журнала.</span><span class="sxs-lookup"><span data-stu-id="0b514-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="0b514-302">При ручном управлении синтетической транзакцией можно использовать параметр OutLoggerVariable, чтобы указать переменную Windows PowerShell, в которой будут храниться сведения.</span><span class="sxs-lookup"><span data-stu-id="0b514-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="0b514-303">Оттуда можно использовать один из двух методов для сохранения и/или просмотра сообщений об ошибках в богатом журнале в формате XML или HTML.</span><span class="sxs-lookup"><span data-stu-id="0b514-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="0b514-304">Чтобы получить сведения о устранении неполадок, укажите параметр OutLoggerVariable, за которым следует переменное имя, которое вы выберете:</span><span class="sxs-lookup"><span data-stu-id="0b514-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="0b514-305">: Не предисловие переменного имени с символом $.</span><span class="sxs-lookup"><span data-stu-id="0b514-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="0b514-306">Используйте переменное имя, например RegistrationTest (не $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="0b514-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="0b514-307">При запуске этой команды вы увидите выход, похожий на этот:</span><span class="sxs-lookup"><span data-stu-id="0b514-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="0b514-308">Целевой Fqdn : atl-cs-001.litwareinc.com результат : Задержка сбоя : 00:00:00 Сообщение об ошибке: эта машина не имеет никаких присвоенных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="0b514-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="0b514-309">Диагностика: Вы можете получить доступ к гораздо более подробным сведениям для этой ошибки, чем просто сообщение об ошибке, показанное здесь.</span><span class="sxs-lookup"><span data-stu-id="0b514-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="0b514-310">Чтобы получить доступ к этим сведениям в формате HTML, используйте команду, аналогичную этой, чтобы сохранить сведения, хранимые в переменной RegistrationTest для HTML-файла:</span><span class="sxs-lookup"><span data-stu-id="0b514-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="0b514-311">Можно также использовать метод ToXML() для сохранения данных в файл XML:</span><span class="sxs-lookup"><span data-stu-id="0b514-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="0b514-312">Эти файлы можно просмотреть с помощью Обозревателя Windows Internet Explorer, Microsoft Visual Studio или любого другого приложения, способного открывать HTML/XML-файлы.</span><span class="sxs-lookup"><span data-stu-id="0b514-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="0b514-313">Синтетические транзакции, которые запускаются изнутри system Center Operations Manager, автоматически создают эти файлы журналов для сбоев.</span><span class="sxs-lookup"><span data-stu-id="0b514-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="0b514-314">Эти журналы не будут созданы, если выполнение не удастся выполнить до того, как Skype для бизнеса Server PowerShell сможет загружать и запускать синтетическую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="0b514-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0b514-315">По умолчанию Skype для бизнеса Server сохраняет файлы журналов в папке, которая не является общей.</span><span class="sxs-lookup"><span data-stu-id="0b514-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="0b514-316">Чтобы сделать эти журналы доступными, следует поделиться этой папкой.</span><span class="sxs-lookup"><span data-stu-id="0b514-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="0b514-317">Например: \\ atl-watcher-001.litwareinc.com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="0b514-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>