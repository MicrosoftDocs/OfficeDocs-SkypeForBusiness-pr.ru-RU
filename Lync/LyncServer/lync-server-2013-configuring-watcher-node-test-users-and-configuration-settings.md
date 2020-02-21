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
ms.openlocfilehash: 78d52e6a7eb36ce0f000a9986480d62692d3a33d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="8190a-102">Настройка тестовых пользователей и параметров конфигурации узла-наблюдателя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8190a-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8190a-103">_**Последнее изменение темы:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="8190a-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="8190a-104">Настроив компьютер, который будет выступать в качестве узла-наблюдателя, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8190a-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="8190a-105">Создайте тестовые учетные записи, которые будут использоваться узлами-наблюдателями.</span><span class="sxs-lookup"><span data-stu-id="8190a-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="8190a-106">Если вы используете проверку подлинности согласованием, вам также необходимо выполнить командлет [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)), чтобы разрешить использование этих учетных записей узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="8190a-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="8190a-107">Обновите параметры конфигурации узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="8190a-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="8190a-108">Содержание раздела:</span><span class="sxs-lookup"><span data-stu-id="8190a-108">This section covers:</span></span>

  - <span data-ttu-id="8190a-109">Настройка тестовых учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="8190a-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="8190a-110">Настройка базового узла-наблюдателя, использующего искусственные транзакции по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8190a-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="8190a-111">Настройка расширенных тестов</span><span class="sxs-lookup"><span data-stu-id="8190a-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="8190a-112">Добавление и удаление искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="8190a-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="8190a-113">Просмотр и тестирование конфигурации узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="8190a-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="8190a-114">Настройка тестовых учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="8190a-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="8190a-115">Тестовые пользователи не должны представлять реальных людей, но они должны быть действительными учетными записями доменных служб Active Directory; Кроме того, эти учетные записи должны быть включены для Lync Server 2013, они должны иметь допустимые SIP-адреса, а также должны быть включены для корпоративной голосовой связи (для использования искусственной транзакции test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="8190a-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="8190a-116">При использовании метода проверки подлинности TrustedServer все, что нужно сделать, — убедиться, что эти учетные записи существуют и настроены указанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="8190a-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="8190a-117">Необходимо назначить по крайней мере трех тестовых пользователей для каждого пула, который необходимо протестировать.</span><span class="sxs-lookup"><span data-stu-id="8190a-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="8190a-118">При использовании метода проверки подлинности Negotiate также необходимо использовать командлет **Set-CsTestUserCredential** и командную консоль Lync Server, чтобы включить эти тестовые учетные записи для работы с искусственными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="8190a-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="8190a-119">Это можно сделать, выполнив команду, аналогичную приведенной ниже.</span><span class="sxs-lookup"><span data-stu-id="8190a-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="8190a-120">(В этих командах предполагается, что три учетные записи пользователей Active Directory уже созданы и что эти учетные записи были включены для Lync Server 2013.):</span><span class="sxs-lookup"><span data-stu-id="8190a-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="8190a-121">Обратите внимание, что необходимо указать не только адрес SIP, но и имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="8190a-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="8190a-122">Если вы не включите пароль Set — CsTestUserCredential предложит ввести эту информацию.</span><span class="sxs-lookup"><span data-stu-id="8190a-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="8190a-123">Имя пользователя можно указать с помощью формата имени домена\\пользователя, показанного выше, или с помощью формата name@domain имя пользователя; Например:</span><span class="sxs-lookup"><span data-stu-id="8190a-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="8190a-124">Чтобы убедиться, что учетные данные тестового пользователя были созданы, выполните следующие команды в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="8190a-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="8190a-125">Команды возвращают сведения о каждом пользователе, похожие на следующие.</span><span class="sxs-lookup"><span data-stu-id="8190a-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="8190a-126">Настройка базового узла-наблюдателя, использующего искусственные транзакции по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8190a-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="8190a-127">Создав тестовых пользователей, вы можете создать узел-наблюдатель с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="8190a-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="8190a-128">Эта команда создает узел-наблюдатель с параметрами по умолчанию, который выполняет набор искусственных транзакций по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8190a-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="8190a-129">Для нового узла-наблюдателя используются тестовые пользователи watcher1@litwareinc.com, watcher2@litwareinc.com и watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="8190a-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="8190a-130">Если узел-наблюдатель использует проверку подлинности TrustedServer, три тестовые учетные записи могут быть любыми допустимыми учетными записями пользователей, включенными для Active Directory и Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8190a-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="8190a-131">Если узел-наблюдатель использует проверку подлинности согласованием, вам нужно разрешить использование этих учетных записей узлом-наблюдателем с помощью командлета **Set-CsTestUserCredential**.</span><span class="sxs-lookup"><span data-stu-id="8190a-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="8190a-132">Настройка расширенных тестов</span><span class="sxs-lookup"><span data-stu-id="8190a-132">Configuring Extended Tests</span></span>

<span data-ttu-id="8190a-133">Если вы хотите включить тест ТСОП, проверяющий подключение к телефонной сети общего пользования, вам потребуется произвести дополнительную настройку узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="8190a-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="8190a-134">Во-первых, вам нужно связать тестовых пользователей с типом теста ТСОП.</span><span class="sxs-lookup"><span data-stu-id="8190a-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="8190a-135">Для этого выполните следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="8190a-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="8190a-136">Обратите внимание на то, что результаты выполнения этой команды необходимо сохранить в переменной.</span><span class="sxs-lookup"><span data-stu-id="8190a-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="8190a-137">В этом примере используется переменная $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="8190a-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="8190a-138">На этом шаге можно использовать командлет **New-CsWatcherNodeConfiguration** , чтобы связать тип теста (хранящийся в переменной $pstnTest) с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8190a-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="8190a-139">Например, следующая команда создает конфигурацию узла-наблюдателя для пула atl-cs-001.litwareinc.com, добавляет трех тестовых пользователей, созданных ранее, а также тест ТСОП.</span><span class="sxs-lookup"><span data-stu-id="8190a-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="8190a-140">Обратите внимание на то, что предыдущая команда завершится с ошибками, если на компьютере узла-наблюдателя не установлены основные файлы Lync Server и база данных RTCLocal.</span><span class="sxs-lookup"><span data-stu-id="8190a-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="8190a-141">Чтобы протестировать несколько политик голосовой связи, вам нужно создать расширенный тест для каждой политики с помощью командлета **New-CsExtendedTest**.</span><span class="sxs-lookup"><span data-stu-id="8190a-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="8190a-142">Для пользователей, назначенных этому тесту, следует настроить требуемые политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8190a-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="8190a-143">После этого передайте расширенные тесты в командлет **New-CsWatcherNodeConfiguration** с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="8190a-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="8190a-p110">Так как командлет New-CsWatcherNodeConfiguration был вызван без параметра Tests, то для нового узла-наблюдателя будут включены только искусственные транзакции по умолчанию и указанные расширенные искусственные транзакции. Это означает, что узел-наблюдатель будет тестировать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="8190a-p110">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node. This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="8190a-146">Зарегистрировал</span><span class="sxs-lookup"><span data-stu-id="8190a-146">Registration</span></span>

  - <span data-ttu-id="8190a-147">"IM" (Обмен мгновенными сообщениями);</span><span class="sxs-lookup"><span data-stu-id="8190a-147">IM</span></span>

  - <span data-ttu-id="8190a-148">граупим</span><span class="sxs-lookup"><span data-stu-id="8190a-148">GroupIM</span></span>

  - <span data-ttu-id="8190a-149">P2PAV (одноранговые аудио- и видеосеансы)</span><span class="sxs-lookup"><span data-stu-id="8190a-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="8190a-150">AvConference (аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="8190a-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="8190a-151">Присутствие</span><span class="sxs-lookup"><span data-stu-id="8190a-151">Presence</span></span>

  - <span data-ttu-id="8190a-152">ABS (служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="8190a-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="8190a-153">ABWQ (веб-служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="8190a-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="8190a-p111">ТСОП (звонки через шлюз ТСОП, определенные как расширенный тест; по умолчанию тест ТСОП отключен, но в этом случае он включен с помощью параметра ExtendedTests, используемого в команде)</span><span class="sxs-lookup"><span data-stu-id="8190a-p111">PSTN (PSTN gateway calls, specified as an extended test. By default, PSTN is disabled. The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="8190a-157">Это также означает, что следующие компоненты не будут тестироваться по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="8190a-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="8190a-158">аведжеконнективити</span><span class="sxs-lookup"><span data-stu-id="8190a-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="8190a-159">MCXP2PIM (обмен мгновенными сообщениями с помощью мобильных устройств)</span><span class="sxs-lookup"><span data-stu-id="8190a-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="8190a-160">ExumConnectivity (единая система обмена сообщениями Exchange)</span><span class="sxs-lookup"><span data-stu-id="8190a-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="8190a-161">жоинлаунчер</span><span class="sxs-lookup"><span data-stu-id="8190a-161">JoinLauncher</span></span>

  - <span data-ttu-id="8190a-162">персистентчатмессаже</span><span class="sxs-lookup"><span data-stu-id="8190a-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="8190a-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="8190a-163">DataConference</span></span>

  - <span data-ttu-id="8190a-164">ксмппим</span><span class="sxs-lookup"><span data-stu-id="8190a-164">XmppIM</span></span>

  - <span data-ttu-id="8190a-165">унифиедконтактсторе</span><span class="sxs-lookup"><span data-stu-id="8190a-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="8190a-166">Добавление и удаление искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="8190a-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="8190a-167">После настройки узла-наблюдателя вы можете добавлять искусственные транзакции на узел-наблюдатель или удалять их с узла-наблюдателя с помощью командлета **Set-CsWatcherNodeConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="8190a-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="8190a-168">Например, чтобы добавить тест PersistentChatMessage на узел-наблюдатель, используйте следующую команду с методом Add.</span><span class="sxs-lookup"><span data-stu-id="8190a-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="8190a-p113">При указании нескольких тестов используйте запятые. Пример:</span><span class="sxs-lookup"><span data-stu-id="8190a-p113">Multiple tests can be added by separating the test names by using commas. For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="8190a-p114">Имейте в виду, что если один или несколько этих тестов (например, DataConference) уже были включены на узле-наблюдателе, произойдет ошибка. В этом случае вы получите следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="8190a-p114">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node. In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="8190a-173">Если произошла эта ошибка, изменения не применяются.</span><span class="sxs-lookup"><span data-stu-id="8190a-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="8190a-174">Команду следует выполнить повторно, удалив повторяющийся тест.</span><span class="sxs-lookup"><span data-stu-id="8190a-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="8190a-p116">Чтобы удалить искусственную транзакцию с узла-наблюдателя, вместо метода Add используйте метод Remove. Например, следующая команда удаляет тест ABWQ с узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="8190a-p116">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method. For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="8190a-p117">С помощью метода Replace вы можете также заменить все тесты, включенные в настоящий момент, на один или несколько новых тестов. Например, если вы хотите, чтобы узел-наблюдатель выполнял только тест IM, вы можете использовать следующую команду.</span><span class="sxs-lookup"><span data-stu-id="8190a-p117">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests. For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="8190a-179">При выполнении предыдущей команды на указанном узле-наблюдателе отключаются все искусственные транзакции, кроме IM.</span><span class="sxs-lookup"><span data-stu-id="8190a-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="8190a-180">Просмотр и тестирование конфигурации узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="8190a-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="8190a-181">Чтобы просмотреть тесты, назначенные узлу-наблюдателю, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="8190a-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="8190a-182">Предыдущая команда возвращает сведения, схожие со следующими (с учетом искусственных транзакций, назначенных узлу).</span><span class="sxs-lookup"><span data-stu-id="8190a-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

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
> <span data-ttu-id="8190a-183">Чтобы просмотреть искусственные транзакции в алфавитном порядке, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="8190a-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="8190a-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span><span class="sxs-lookup"><span data-stu-id="8190a-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="8190a-185">Чтобы проверить, был ли создан узел-наблюдатель, введите в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8190a-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="8190a-186">Команда возвращает сведения, похожие на следующие.</span><span class="sxs-lookup"><span data-stu-id="8190a-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="8190a-187">Чтобы убедиться в правильности настройки узла-наблюдателя, введите следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="8190a-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="8190a-188">Предыдущая команда проверяет каждый узел-наблюдатель в развертывании и сообщает следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="8190a-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="8190a-189">установлена ли требуемая роль Регистратора;</span><span class="sxs-lookup"><span data-stu-id="8190a-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="8190a-190">созданы ли требуемые разделы реестра при запуске команды Set-CsWatcherNodeConfiguration;</span><span class="sxs-lookup"><span data-stu-id="8190a-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="8190a-191">На ваших серверах работает правильная версия Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8190a-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="8190a-192">правильно ли настроены порты;</span><span class="sxs-lookup"><span data-stu-id="8190a-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="8190a-193">имеются ли у назначенных тестовых пользователей требуемые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="8190a-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

