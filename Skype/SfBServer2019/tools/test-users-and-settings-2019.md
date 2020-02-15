---
title: Настройка тестовых пользователей и параметров узла-наблюдателя
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Настройка тестовых учетных записей пользователей и параметров узла-наблюдателя для искусственных транзакций Skype для бизнеса Server.
ms.openlocfilehash: f13680d16a248be339ee7cd4a085d7d0894146dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033678"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="32f9c-103">Настройка тестовых пользователей и параметров узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="32f9c-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="32f9c-104">**Сводка:** Настройка тестовых учетных записей пользователей и параметров узла-наблюдателя для искусственных транзакций Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="32f9c-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="32f9c-105">Настроив компьютер, который будет выступать в качестве узла-наблюдателя, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="32f9c-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="32f9c-106">[Настройка тестовых учетных записей пользователей](test-users-and-settings-2019.md#testuser) для использования этими узлами-наблюдателями.</span><span class="sxs-lookup"><span data-stu-id="32f9c-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="32f9c-107">Если вы используете проверку подлинности согласованием, вам также необходимо выполнить командлет **Set-CsTestUserCredential**, чтобы разрешить использование этих учетных записей узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="32f9c-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="32f9c-108">Обновите параметры конфигурации узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="32f9c-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="32f9c-109">Настройка тестовых учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="32f9c-109">Configure Test User Accounts</span></span>
<span data-ttu-id="32f9c-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="32f9c-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="32f9c-111">Тестовые учетные записи не должны представлять реальных людей, но они должны быть действительными учетными записями Active Directory.</span><span class="sxs-lookup"><span data-stu-id="32f9c-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="32f9c-112">Кроме того, эти учетные записи должны быть включены в Skype для бизнеса Server, они должны иметь действительные адреса SIP, а также должны быть включены для корпоративной голосовой связи (для использования искусственной транзакции test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="32f9c-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="32f9c-113">При использовании метода проверки подлинности TrustedServer все, что нужно сделать, — убедиться, что эти учетные записи существуют, и настроить их так, как указано.</span><span class="sxs-lookup"><span data-stu-id="32f9c-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="32f9c-114">Необходимо назначить по крайней мере трех тестовых пользователей для каждого пула, который необходимо протестировать.</span><span class="sxs-lookup"><span data-stu-id="32f9c-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="32f9c-115">При использовании метода проверки подлинности Negotiate также необходимо использовать командлет Set-CsTestUserCredential и командную консоль Skype для бизнеса Server, чтобы включить эти тестовые учетные записи для работы с искусственными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="32f9c-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="32f9c-116">Для этого выполните следующую команду (в этих командах предполагается, что созданы три учетные записи пользователей Active Directory и для них включены Skype для бизнеса Server):</span><span class="sxs-lookup"><span data-stu-id="32f9c-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="32f9c-117">Необходимо указать не только SIP адрес, но и имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="32f9c-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="32f9c-118">Если вы не включите пароль, командлет Set – CsTestUserCredential предложит ввести эту информацию.</span><span class="sxs-lookup"><span data-stu-id="32f9c-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="32f9c-119">Имя пользователя можно указать с помощью формата имени домена наме\усер, показанного в предыдущем блоке кода.</span><span class="sxs-lookup"><span data-stu-id="32f9c-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="32f9c-120">Чтобы убедиться, что учетные данные тестового пользователя были созданы, выполните следующие команды в командной консоли Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="32f9c-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="32f9c-121">Для каждого пользователя будет возвращена информация, подобная этой:</span><span class="sxs-lookup"><span data-stu-id="32f9c-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="32f9c-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="32f9c-122">**UserName**</span></span>|<span data-ttu-id="32f9c-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="32f9c-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="32f9c-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="32f9c-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="32f9c-125">System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="32f9c-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="32f9c-126">Настройка базового узла-наблюдателя с искусственными транзакциями по умолчанию</span><span class="sxs-lookup"><span data-stu-id="32f9c-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="32f9c-127">После создания тестовых пользователей можно создать узел-наблюдатель с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="32f9c-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="32f9c-128">Эта команда создает узел-наблюдатель с параметрами по умолчанию, который выполняет набор искусственных транзакций по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="32f9c-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="32f9c-129">Для нового узла-наблюдателя используются тестовые пользователи watcher1@litwareinc.com, watcher2@litwareinc.com и watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="32f9c-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="32f9c-130">Если узел-наблюдатель использует проверку подлинности TrustedServer, три тестовые учетные записи могут быть любыми допустимыми учетными записями пользователей, включенными для Active Directory и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="32f9c-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="32f9c-131">Если узел-наблюдатель использует метод проверки подлинности Negotiate, эти учетные записи пользователей также должны быть включены для узла-наблюдателя с помощью командлета Set-CsTestUserCredential.</span><span class="sxs-lookup"><span data-stu-id="32f9c-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="32f9c-132">Чтобы проверить, правильно ли настроено автоматическое обнаружение конечного пула, а не нацеливание на пул напрямую, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="32f9c-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="32f9c-133">Настройка расширенных тестов</span><span class="sxs-lookup"><span data-stu-id="32f9c-133">Configuring Extended Tests</span></span>

<span data-ttu-id="32f9c-134">Если вы хотите включить тест PSTN, который проверяет связь с телефонной сетью общего пользования, вам потребуется дополнительная настройка узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="32f9c-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="32f9c-135">Для начала необходимо связать тестовых пользователей с типом проверки PSTN, выполнив следующую команду в командной консоли Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="32f9c-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="32f9c-136">Результаты этой команды должны храниться в переменной.</span><span class="sxs-lookup"><span data-stu-id="32f9c-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="32f9c-137">В этом примере переменной присвоено имя $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="32f9c-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="32f9c-138">Затем можно использовать командлет **New-CsWatcherNodeConfiguration** , чтобы связать тип теста (хранящийся в переменной $pstnTest) с пулом Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="32f9c-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="32f9c-139">Например, следующая команда создает новую конфигурацию узла-наблюдателя для пула atl-cs-001.litwareinc.com, добавляя трех тестовых пользователей, созданных ранее, и добавляя тип проверки PSTN:</span><span class="sxs-lookup"><span data-stu-id="32f9c-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="32f9c-140">Предыдущая команда завершится с ошибками, если на компьютере узла-наблюдателя не установлены основные файлы Skype для бизнеса Server и база данных RTCLocal.</span><span class="sxs-lookup"><span data-stu-id="32f9c-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="32f9c-141">Чтобы протестировать несколько политик голосовой связи, можно создать расширенный тест для каждой политики с помощью командлета **New-CsExtendedTest** .</span><span class="sxs-lookup"><span data-stu-id="32f9c-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="32f9c-142">Предоставленные пользователи должны быть настроены с использованием требуемых политик голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="32f9c-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="32f9c-143">Расширенные тесты передаются в командлет **New – CsWatcherNodeConfiguration** с помощью разделителей запятыми, таких как:</span><span class="sxs-lookup"><span data-stu-id="32f9c-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="32f9c-144">— Екстендедтестс @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="32f9c-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="32f9c-145">Так как командлет **New-CsWatcherNodeConfiguration** был вызван без параметра Tests, для нового узла-наблюдателя будут включены только синтетические транзакции по умолчанию (и указанная Расширенная искусственная транзакция).</span><span class="sxs-lookup"><span data-stu-id="32f9c-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="32f9c-146">Таким образом, узел-наблюдатель будет тестировать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="32f9c-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="32f9c-147">Зарегистрировал</span><span class="sxs-lookup"><span data-stu-id="32f9c-147">Registration</span></span>
    
- <span data-ttu-id="32f9c-148">"IM" (Обмен мгновенными сообщениями);</span><span class="sxs-lookup"><span data-stu-id="32f9c-148">IM</span></span>
    
- <span data-ttu-id="32f9c-149">граупим</span><span class="sxs-lookup"><span data-stu-id="32f9c-149">GroupIM</span></span>
    
- <span data-ttu-id="32f9c-150">P2PAV (одноранговые аудио- и видеосеансы)</span><span class="sxs-lookup"><span data-stu-id="32f9c-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="32f9c-151">AvConference (аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="32f9c-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="32f9c-152">Присутствие</span><span class="sxs-lookup"><span data-stu-id="32f9c-152">Presence</span></span>
    
- <span data-ttu-id="32f9c-153">ABS (служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="32f9c-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="32f9c-154">ABWQ (веб-служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="32f9c-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="32f9c-155">Следующие компоненты не будут тестироваться по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="32f9c-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="32f9c-156">асконференце</span><span class="sxs-lookup"><span data-stu-id="32f9c-156">ASConference</span></span>
    
- <span data-ttu-id="32f9c-157">аведжеконнективити</span><span class="sxs-lookup"><span data-stu-id="32f9c-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="32f9c-158">DataConference</span><span class="sxs-lookup"><span data-stu-id="32f9c-158">DataConference</span></span>
    
- <span data-ttu-id="32f9c-159">диалинконференЦинг</span><span class="sxs-lookup"><span data-stu-id="32f9c-159">DialinConferencing</span></span>
    
- <span data-ttu-id="32f9c-160">ExumConnectivity (единая система обмена сообщениями Exchange)</span><span class="sxs-lookup"><span data-stu-id="32f9c-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="32f9c-161">жоинлаунчер</span><span class="sxs-lookup"><span data-stu-id="32f9c-161">JoinLauncher</span></span>
    
- <span data-ttu-id="32f9c-162">MCXP2PIM (устаревшие обмен мгновенными сообщениями для мобильных устройств)</span><span class="sxs-lookup"><span data-stu-id="32f9c-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="32f9c-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="32f9c-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="32f9c-164">персистентчатмессаже</span><span class="sxs-lookup"><span data-stu-id="32f9c-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="32f9c-165">PSTN (звонки шлюза PSTN, которые задаются в качестве расширенного теста)</span><span class="sxs-lookup"><span data-stu-id="32f9c-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="32f9c-166">укваконференце</span><span class="sxs-lookup"><span data-stu-id="32f9c-166">UcwaConference</span></span>
    
- <span data-ttu-id="32f9c-167">унифиедконтактсторе</span><span class="sxs-lookup"><span data-stu-id="32f9c-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="32f9c-168">ксмппим</span><span class="sxs-lookup"><span data-stu-id="32f9c-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="32f9c-169">Добавление и удаление искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="32f9c-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="32f9c-170">После настройки узла-наблюдателя вы можете добавлять искусственные транзакции на узел-наблюдатель или удалять их с узла-наблюдателя с помощью командлета Set-CsWatcherNodeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="32f9c-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="32f9c-171">Например, чтобы добавить тест PersistentChatMessage на узел-наблюдатель, используйте следующую команду с методом Add.</span><span class="sxs-lookup"><span data-stu-id="32f9c-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="32f9c-172">При указании нескольких тестов используйте запятые.</span><span class="sxs-lookup"><span data-stu-id="32f9c-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="32f9c-173">Пример:</span><span class="sxs-lookup"><span data-stu-id="32f9c-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="32f9c-174">Если в узле-наблюдателе уже были включены какие-либо из этих тестов (например, для конференц-связи), произойдет ошибка.</span><span class="sxs-lookup"><span data-stu-id="32f9c-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="32f9c-175">В этом случае вы получите следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="32f9c-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="32f9c-176">Set-CsWatcherNodeConfiguration: существует повторяющаяся последовательность ключей ' Conference ' для ' urn: schema: Microsoft. RTC. Management. Settings. WatcherNode. 2010: Тестнаме ' key или UNIQUE Identity Constraint.</span><span class="sxs-lookup"><span data-stu-id="32f9c-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="32f9c-177">Если произошла эта ошибка, изменения не применяются.</span><span class="sxs-lookup"><span data-stu-id="32f9c-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="32f9c-178">Эту команду необходимо выполнить повторно с удалением тестового дубликата.</span><span class="sxs-lookup"><span data-stu-id="32f9c-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="32f9c-179">Чтобы удалить искусственную транзакцию из узла-наблюдателя, используйте метод Remove.</span><span class="sxs-lookup"><span data-stu-id="32f9c-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="32f9c-180">Например, следующая команда удаляет тест ABWQ с узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="32f9c-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="32f9c-181">Метод Replace можно использовать для замены всех включенных в данный момент тестов на один или несколько новых тестов.</span><span class="sxs-lookup"><span data-stu-id="32f9c-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="32f9c-182">Например, если вы хотите, чтобы узел-наблюдатель выполнял проверку IM, вы можете настроить его с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="32f9c-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="32f9c-183">При выполнении этой команды все искусственные транзакции на заданном узле-наблюдателе будут отключены, кроме IM.</span><span class="sxs-lookup"><span data-stu-id="32f9c-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="32f9c-184">Просмотр и тестирование конфигурации узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="32f9c-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="32f9c-185">Чтобы просмотреть тесты, назначенные узлу-наблюдателю, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="32f9c-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="32f9c-186">Эта команда возвращает такие сведения, как, в зависимости от искусственных транзакций, назначенных узлу:</span><span class="sxs-lookup"><span data-stu-id="32f9c-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="32f9c-187">Регистрация IM Граупим P2PAV Авконференце сведения о присутствии Персистентчатмессаже-Конференция</span><span class="sxs-lookup"><span data-stu-id="32f9c-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="32f9c-188">Чтобы просмотреть искусственные транзакции в алфавитном порядке, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="32f9c-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="32f9c-189">Чтобы проверить, был ли создан узел-наблюдатель, введите в командной консоли Skype для бизнеса Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="32f9c-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="32f9c-190">Будет выведена информация, похожая на приведенную ниже.</span><span class="sxs-lookup"><span data-stu-id="32f9c-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="32f9c-191">Identity: atl-cs-001.litwareinc.com Тестусерс: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="32f9c-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="32f9c-192">Екстендедтестс: {Тестусерс = IList<System. String>; Name = PSTN-тест; TE...}</span><span class="sxs-lookup"><span data-stu-id="32f9c-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="32f9c-193">TargetFqdn: atl-cs-001.litwareinc.com номер_порта: 5061To Проверьте правильность настройки узла-наблюдателя, введите следующую команду в командной консоли Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="32f9c-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="32f9c-194">Эта команда проверяет каждый узел-наблюдатель в развертывании и проверяет, выполняются ли следующие действия:</span><span class="sxs-lookup"><span data-stu-id="32f9c-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="32f9c-195">Установлена необходимая роль регистратора;</span><span class="sxs-lookup"><span data-stu-id="32f9c-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="32f9c-196">Создается необходимый раздел реестра (завершается при выполнении командлета Set-CsWatcherNodeConfiguration)</span><span class="sxs-lookup"><span data-stu-id="32f9c-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="32f9c-197">На ваших серверах работает правильная версия Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="32f9c-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="32f9c-198">Порты настроены правильно</span><span class="sxs-lookup"><span data-stu-id="32f9c-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="32f9c-199">У назначенных тестовых пользователей есть необходимые учетные данные</span><span class="sxs-lookup"><span data-stu-id="32f9c-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="32f9c-200">Управление узлами-наблюдателями</span><span class="sxs-lookup"><span data-stu-id="32f9c-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="32f9c-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="32f9c-201"><a name="testuser"> </a></span></span>

<span data-ttu-id="32f9c-202">В дополнение к изменению искусственных транзакций, выполняемых на узле-наблюдателе, можно также использовать командлет **Set-CsWatcherNodeConfiguration** для выполнения двух других важных задач: Включение и отключение узла-наблюдателя, а также настройка узла-наблюдателя для использования внутренних URL-адресов или внешних веб-URL-адресов при выполнении тестов.</span><span class="sxs-lookup"><span data-stu-id="32f9c-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="32f9c-203">По умолчанию узлы-наблюдатели периодически запускают все включенные искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="32f9c-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="32f9c-204">Однако иногда может потребоваться приостановить эти транзакции.</span><span class="sxs-lookup"><span data-stu-id="32f9c-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="32f9c-205">Например, если узел-наблюдатель временно отключился от сети, у него больше нет причин запускать искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="32f9c-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="32f9c-206">Без подключения к сети эти транзакции завершатся с ошибками.</span><span class="sxs-lookup"><span data-stu-id="32f9c-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="32f9c-207">Чтобы временно отключить узел-наблюдатель, выполните следующую команду в командной консоли Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="32f9c-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="32f9c-208">Эта команда отключит выполнение искусственных транзакций на узле-наблюдателе ATL-наблюдателя 001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="32f9c-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="32f9c-209">Чтобы возобновить выполнение искусственных транзакций, снова задайте для свойства Enabled значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="32f9c-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="32f9c-210">Свойство Enabled может использоваться для включения или отключения узлов-наблюдателей.</span><span class="sxs-lookup"><span data-stu-id="32f9c-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="32f9c-211">Если нет необходимости временно удалять узел-наблюдатель, используйте командлет **Remove-CsWatcherNodeConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="32f9c-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="32f9c-212">Эта команда удаляет все параметры конфигурации узла-наблюдателя с указанного компьютера, что запрещает этому компьютеру автоматически запускать синтетические транзакции.</span><span class="sxs-lookup"><span data-stu-id="32f9c-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="32f9c-213">Однако команда не удаляет файлы агента System Center или файлы системы Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="32f9c-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="32f9c-214">По умолчанию узлы-наблюдатели при проведении тестов используют внешние URL-адреса в Организации.</span><span class="sxs-lookup"><span data-stu-id="32f9c-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="32f9c-215">Однако узлы-наблюдатели также можно настроить на использование внутренних URL-адресов организации.</span><span class="sxs-lookup"><span data-stu-id="32f9c-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="32f9c-216">Это позволит администраторам проверить доступ к URL-адресам тех пользователей, которые находятся внутри сети периметра.</span><span class="sxs-lookup"><span data-stu-id="32f9c-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="32f9c-217">Чтобы настроить узел-наблюдатель для использования внутренних URL-адресов вместо внешних URL-адресов, задайте для свойства Усеинтерналвебурлс значение true ($True):</span><span class="sxs-lookup"><span data-stu-id="32f9c-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="32f9c-218">Сброс этого свойства к значению по умолчанию "false" ($False) приведет к тому, что наблюдатель снова будет использовать внешние URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="32f9c-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="32f9c-219">Специальные инструкции по установке для искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="32f9c-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="32f9c-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="32f9c-220"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="32f9c-221">Большинство искусственных транзакций могут выполняться на узле-наблюдателе как есть.</span><span class="sxs-lookup"><span data-stu-id="32f9c-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="32f9c-222">В большинстве случаев, как только искусственная транзакция добавляется в параметры конфигурации узла-наблюдателя, узел-наблюдатель может начать использовать эту искусственную транзакцию во время тестовых этапов.</span><span class="sxs-lookup"><span data-stu-id="32f9c-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="32f9c-223">Однако некоторые искусственные транзакции требуют специальных инструкций по настройке, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="32f9c-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="32f9c-224">Искусственная транзакция конференц-связи с данными</span><span class="sxs-lookup"><span data-stu-id="32f9c-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="32f9c-225">Если компьютер узла-наблюдателя находится вне сети периметра, то, возможно, не удастся запустить искусственную транзакцию конференц-связи с данными, пока не будет предварительно отключена Windows Internet Explorer® прокси-сервера браузера Internet Explorer для сети. Учетную запись службы, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="32f9c-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="32f9c-226">На компьютере узла-наблюдателя нажмите кнопку **Пуск**, выберите **все программы**, **стандартные**, щелкните правой кнопкой мыши **Командная строка**и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="32f9c-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="32f9c-227">В окне консоли введите следующую команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="32f9c-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="32f9c-228">В окне командной строки отобразится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="32f9c-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="32f9c-229">Битсадмин является устаревшим и не гарантируется доступным в будущих версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="32f9c-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="32f9c-230">Средства администрирования для службы BITS теперь предоставляются командлетами PowerShell BITS.</span><span class="sxs-lookup"><span data-stu-id="32f9c-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="32f9c-231">Параметры прокси-сервера в Интернете для учетной записи NetworkService имеют значение NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="32f9c-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="32f9c-232">(подключение = по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="32f9c-232">(connection = default)</span></span>
  
<span data-ttu-id="32f9c-233">Это сообщение указывает на то, что вы отключили параметры прокси-сервера Internet Explorer для учетной записи сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="32f9c-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="32f9c-234">Искусственная транзакция единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="32f9c-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="32f9c-235">Искусственная транзакция единой системы обмена сообщениями Exchange удостоверяется в том, что тестовые пользователи могут подключаться к учетным записям голосовой почты, размещенным в Exchange.</span><span class="sxs-lookup"><span data-stu-id="32f9c-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="32f9c-236">Тестовые пользователи должны быть предварительно настроены с помощью учетных записей голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="32f9c-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="32f9c-237">Искусственная транзакция сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="32f9c-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="32f9c-238">Чтобы использовать искусственную транзакцию сохраняемого чата, необходимо сначала создать канал и предоставить тестовым пользователям разрешения на его использование.</span><span class="sxs-lookup"><span data-stu-id="32f9c-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="32f9c-239">Для настройки этого канала можно использовать искусственную транзакцию сохраняемого чата:</span><span class="sxs-lookup"><span data-stu-id="32f9c-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="32f9c-240">Эту задачу установки необходимо запускать на предприятии, находящегося на предприятии:</span><span class="sxs-lookup"><span data-stu-id="32f9c-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="32f9c-241">При запуске с компьютера, не являющегося сервером, пользователь, который выполняет командлет, должен быть членом роли Ксперсистентчатадминистраторс для управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="32f9c-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="32f9c-242">При запуске с самого сервера пользователь, который выполняет командлет, должен быть членом группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="32f9c-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="32f9c-243">Искусственная транзакция однорангового вызова PSTN</span><span class="sxs-lookup"><span data-stu-id="32f9c-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="32f9c-244">Искусственная транзакция Test-CsPstnPeerToPeerCall проверяет возможность размещения и получения вызовов через коммутируемую телефонную сеть общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="32f9c-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="32f9c-245">Чтобы выполнить эту искусственную транзакцию, необходимо настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="32f9c-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="32f9c-246">Два тестовых пользователя с включенной поддержкой UC (вызывающий абонент и получатель).</span><span class="sxs-lookup"><span data-stu-id="32f9c-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="32f9c-247">Прямые входные номера для каждой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="32f9c-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="32f9c-248">Политики VoIP и маршруты голосовой связи, которые позволяют звонить на номер приемника для подключения к шлюзу PSTN.</span><span class="sxs-lookup"><span data-stu-id="32f9c-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="32f9c-249">Шлюз PSTN, который принимает вызовы и носители, которые будут перенаправлять вызовы обратно в пул домашнего пула получателя в соответствии с набираемым номером.</span><span class="sxs-lookup"><span data-stu-id="32f9c-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="32f9c-250">Искусственная транзакция в едином хранилище контактов</span><span class="sxs-lookup"><span data-stu-id="32f9c-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="32f9c-251">Искусственная транзакция в едином хранилище контактов проверяет способность Skype для бизнеса Server получать контакты от имени пользователя из Exchange.</span><span class="sxs-lookup"><span data-stu-id="32f9c-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="32f9c-252">Чтобы использовать эту искусственную транзакцию, следует выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="32f9c-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="32f9c-253">Lyss — необходимо настроить проверку подлинности Exchange Server на сервере.</span><span class="sxs-lookup"><span data-stu-id="32f9c-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="32f9c-254">Тестовые пользователи должны иметь действительный почтовый ящик Exchange.</span><span class="sxs-lookup"><span data-stu-id="32f9c-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="32f9c-255">После выполнения этих условий можно выполнить следующий командлет Windows PowerShell для переноса списков контактов тестовых пользователей в Exchange:</span><span class="sxs-lookup"><span data-stu-id="32f9c-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="32f9c-256">Для переноса списков контактов пользователей в Exchange может потребоваться некоторое время.</span><span class="sxs-lookup"><span data-stu-id="32f9c-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="32f9c-257">Чтобы отслеживать ход миграции, можно выполнить ту же командную строку без флага – Setup:</span><span class="sxs-lookup"><span data-stu-id="32f9c-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="32f9c-258">После завершения миграции эта командная строка будет выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="32f9c-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="32f9c-259">Искусственная транзакция XMPP</span><span class="sxs-lookup"><span data-stu-id="32f9c-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="32f9c-260">Для искусственной транзакции обмена мгновенными сообщениями по протоколу XMPP необходимо настроить функцию XMPP с одним или несколькими федеративными доменами.</span><span class="sxs-lookup"><span data-stu-id="32f9c-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="32f9c-261">Чтобы включить искусственную транзакцию XMPP, необходимо указать параметр Ксмпптестрецеивермаиладдресс с учетной записью пользователя в поднаправляемом домене XMPP.</span><span class="sxs-lookup"><span data-stu-id="32f9c-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="32f9c-262">Пример:</span><span class="sxs-lookup"><span data-stu-id="32f9c-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="32f9c-263">В этом примере должно существовать правило Skype для бизнеса Server для маршрутизации сообщений litwareinc.com на шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="32f9c-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="32f9c-264">Шлюзы и прокси-серверы XMPP были доступны в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="32f9c-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="32f9c-265">Дополнительные сведения приведены в статье [Миграция Федерации XMPP](../migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="32f9c-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="32f9c-266">Искусственная транзакция сервера видеовзаимодействия (VIS)</span><span class="sxs-lookup"><span data-stu-id="32f9c-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="32f9c-267">Для искусственной транзакции сервера видеовзаимодействия (VIS) необходимо скачать и установить файлы поддержки искусственной транзакции ([VISSTSupportPackage. msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span><span class="sxs-lookup"><span data-stu-id="32f9c-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="32f9c-268">Чтобы установить VISSTSupportPackage. msi, убедитесь, что зависимости (в разделе Требования к системе) для MSI уже установлены.</span><span class="sxs-lookup"><span data-stu-id="32f9c-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="32f9c-269">Запустите VISSTSupportPackage. msi, чтобы выполнить простую установку.</span><span class="sxs-lookup"><span data-stu-id="32f9c-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="32f9c-270">MSI устанавливает все файлы по следующему пути: "пакет поддержки искусственной транзакции%Програмфилес%\вис".</span><span class="sxs-lookup"><span data-stu-id="32f9c-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="32f9c-271">Для получения дополнительных сведений о запуске искусственной транзакции VIS обратитесь к документации по командлету [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) .</span><span class="sxs-lookup"><span data-stu-id="32f9c-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="32f9c-272">Изменение частоты запуска для искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="32f9c-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="32f9c-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="32f9c-273"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="32f9c-274">По умолчанию искусственные транзакции будут выполняться с настроенными пользователями каждые 15 минут.</span><span class="sxs-lookup"><span data-stu-id="32f9c-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="32f9c-275">Искусственные транзакции выполняются последовательно в наборе пользователей, чтобы избежать конфликтов между двумя искусственными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="32f9c-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="32f9c-276">Более длительный интервал необходим для предоставления времени для завершения всех искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="32f9c-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="32f9c-277">Если требуется более часто запускать искусственные транзакции, необходимо уменьшить количество искусственных транзакций, выполняемых с определенным набором пользователей, чтобы тесты могли завершиться в требуемом диапазоне времени с некоторым буфером для задержки в сети.</span><span class="sxs-lookup"><span data-stu-id="32f9c-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="32f9c-278">Если требуется выполнение дополнительных искусственных транзакций, создайте дополнительные наборы пользователей для запуска дополнительных искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="32f9c-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="32f9c-279">Чтобы изменить частоту выполнения искусственных транзакций, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="32f9c-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="32f9c-280">Откройте System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="32f9c-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="32f9c-281">Щелкните раздел Разработка.</span><span class="sxs-lookup"><span data-stu-id="32f9c-281">Click Authoring section.</span></span> <span data-ttu-id="32f9c-282">Раздел "правила" (в разделе Разработка)</span><span class="sxs-lookup"><span data-stu-id="32f9c-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="32f9c-283">В разделе rules (правила) Найдите правило с именем "главное правило сбора производительности для запуска искусственной транзакции".</span><span class="sxs-lookup"><span data-stu-id="32f9c-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="32f9c-284">Щелкните правило правой кнопкой мыши и выберите пункт переопределения, выберите переопределение правила, а затем выберите "для всех объектов класса:" наблюдатель пула "</span><span class="sxs-lookup"><span data-stu-id="32f9c-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="32f9c-285">В окне Переопределение свойств выберите имя параметра "частота" и задайте для свойства override нужное значение.</span><span class="sxs-lookup"><span data-stu-id="32f9c-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="32f9c-286">В том же окне выберите пакет управления, к которому необходимо применить это переопределение</span><span class="sxs-lookup"><span data-stu-id="32f9c-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="32f9c-287">Использование подробного журнала для искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="32f9c-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="32f9c-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="32f9c-288"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="32f9c-289">Искусственные транзакции очень удобно использовать для выявления проблем с системой.</span><span class="sxs-lookup"><span data-stu-id="32f9c-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="32f9c-290">Например, командлет Test-CsRegistration может предупредить администраторов о том, что пользователи столкнулись с проблемами при регистрации в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="32f9c-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="32f9c-291">Тем не менее, для определения фактической причины сбоя могут потребоваться дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="32f9c-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="32f9c-292">По этой причине искусственные транзакции предоставляют широкие возможности ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="32f9c-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="32f9c-293">С помощью расширенного ведения журнала для каждого действия, которое потребует искусственной транзакции, записываются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="32f9c-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="32f9c-294">Время начала действия.</span><span class="sxs-lookup"><span data-stu-id="32f9c-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="32f9c-295">Время завершения действия.</span><span class="sxs-lookup"><span data-stu-id="32f9c-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="32f9c-296">Выполняемое действие (например, создание, присоединение или выход из конференции; вход в Skype для бизнеса Server; Отправка мгновенного сообщения).</span><span class="sxs-lookup"><span data-stu-id="32f9c-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="32f9c-297">Информационные, подробные сообщения, предупреждения или сообщения об ошибках, которые были созданы при выполнении операции</span><span class="sxs-lookup"><span data-stu-id="32f9c-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="32f9c-298">Сообщения о регистрации SIP.</span><span class="sxs-lookup"><span data-stu-id="32f9c-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="32f9c-299">Записи об исключениях или диагностические коды, созданные при выполнении действия.</span><span class="sxs-lookup"><span data-stu-id="32f9c-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="32f9c-300">Общий результат выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="32f9c-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="32f9c-301">Эти сведения автоматически создаются при каждом запуске искусственной транзакции, но не отображаются и не записываются в файл журнала автоматически.</span><span class="sxs-lookup"><span data-stu-id="32f9c-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="32f9c-302">Если вы вручную выполняете искусственную транзакцию, можно использовать параметр OutLoggerVariable, чтобы указать переменную Windows PowerShell, в которой будут храниться данные.</span><span class="sxs-lookup"><span data-stu-id="32f9c-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="32f9c-303">Вы можете использовать один из двух методов для сохранения сообщений об ошибках в формате XML или HTML или просмотра сообщений об ошибках в расширенном журнале.</span><span class="sxs-lookup"><span data-stu-id="32f9c-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="32f9c-304">Чтобы получить сведения об устранении неполадок, укажите параметр OutLoggerVariable, а затем имя переменной, которую вы выбираете:</span><span class="sxs-lookup"><span data-stu-id="32f9c-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="32f9c-305">: Не предваряйте имя переменной символом $.</span><span class="sxs-lookup"><span data-stu-id="32f9c-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="32f9c-306">Используйте имя переменной, например RegistrationTest (не $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="32f9c-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="32f9c-307">При выполнении этой команды отобразятся выходные данные, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="32f9c-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="32f9c-308">Целевое полное доменное имя: atl-cs-001.litwareinc.com result: задержка сбоя: 00:00:00 сообщение об ошибке: на этом компьютере нет назначенных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="32f9c-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="32f9c-309">Диагностика: вы можете получить доступ к гораздо более подробным сведениям об этой ошибке, чем просто сообщение об ошибке, показанное здесь.</span><span class="sxs-lookup"><span data-stu-id="32f9c-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="32f9c-310">Чтобы получить доступ к этой информации в формате HTML, используйте команду, аналогичную приведенной ниже, чтобы сохранить данные, хранящиеся в переменной RegistrationTest, в HTML-файл:</span><span class="sxs-lookup"><span data-stu-id="32f9c-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="32f9c-311">Можно также использовать метод ToXML() для сохранения данных в файл XML:</span><span class="sxs-lookup"><span data-stu-id="32f9c-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="32f9c-312">Эти файлы можно просмотреть с помощью Windows Internet Explorer, Microsoft Visual Studio или любого другого приложения, поддерживающего файлы HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="32f9c-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="32f9c-313">Искусственные транзакции, выполняемые из System Center Operations Manager, будут автоматически создавать эти файлы журналов для сбоев.</span><span class="sxs-lookup"><span data-stu-id="32f9c-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="32f9c-314">Эти журналы не будут создаваться в случае сбоя выполнения до того, как Skype для бизнеса Server PowerShell сможет загрузить и запустить искусственную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="32f9c-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="32f9c-315">По умолчанию Skype для бизнеса Server сохраняет файлы журнала в папку, к которой не предоставлен общий доступ.</span><span class="sxs-lookup"><span data-stu-id="32f9c-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="32f9c-316">Чтобы сделать эти журналы общедоступными, необходимо поделиться этой папкой.</span><span class="sxs-lookup"><span data-stu-id="32f9c-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="32f9c-317">Пример: \\ATL-наблюдатель-001. litwareinc. ком\ватчерноде.</span><span class="sxs-lookup"><span data-stu-id="32f9c-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
