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

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="fe76e-102">Настройка пользователей и параметров конфигурации для проверки узла-наблюдателя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe76e-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe76e-103">_**Тема последнего изменения:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="fe76e-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="fe76e-104">Настроив компьютер, который будет выступать в качестве узла-наблюдателя, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fe76e-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="fe76e-105">Создание тестовых учетных записей, которые будут использоваться этими узлами контрольного следа.</span><span class="sxs-lookup"><span data-stu-id="fe76e-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="fe76e-106">Если вы используете проверку подлинности согласованием, вам также необходимо выполнить командлет [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)), чтобы разрешить использование этих учетных записей узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="fe76e-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="fe76e-107">Обновите параметры конфигурации узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="fe76e-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="fe76e-108">В этом разделе рассматриваются следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="fe76e-108">This section covers:</span></span>

  - <span data-ttu-id="fe76e-109">Настройка тестовых учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="fe76e-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="fe76e-110">Настройка основного узла наблюдения с синтетическими транзакциями по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fe76e-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="fe76e-111">Настройка расширенных тестов</span><span class="sxs-lookup"><span data-stu-id="fe76e-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="fe76e-112">Добавление и удаление искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="fe76e-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="fe76e-113">Просмотр и тестирование конфигурации узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="fe76e-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="fe76e-114">Настройка тестовых учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="fe76e-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="fe76e-115">Тестовые пользователи не должны представлять реальных пользователей, но они должны быть действительными учетными записями доменных служб Active Directory; Кроме того, эти учетные записи должны быть включены для Lync Server 2013, они должны иметь действительные адреса SIP, и они должны быть включены для использования в корпоративных голосовых целях (чтобы использовать синтетическую транзакцию Test-Кспстнпиртопиркалл).</span><span class="sxs-lookup"><span data-stu-id="fe76e-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="fe76e-116">При использовании метода проверки подлинности Трустедсервер все, что вам нужно сделать, — это убедиться, что эти учетные записи существуют и настроены указанным образом.</span><span class="sxs-lookup"><span data-stu-id="fe76e-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="fe76e-117">You should assign at least three test users for each pool that you want to test.</span><span class="sxs-lookup"><span data-stu-id="fe76e-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="fe76e-118">Если вы используете метод проверки подлинности Negotiate, необходимо также использовать командлет **Set-кстестусеркредентиал** и командную консоль Lync Server, чтобы включить эти тестовые учетные записи для работы с искусственными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="fe76e-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="fe76e-119">Это можно сделать, выполнив команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="fe76e-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="fe76e-120">(В этом разделе предполагается, что три учетные записи пользователей Active Directory уже созданы и что эти учетные записи включены для Lync Server 2013.):</span><span class="sxs-lookup"><span data-stu-id="fe76e-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="fe76e-121">Обратите внимание, что необходимо указать не только адрес SIP, но и имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="fe76e-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="fe76e-122">Если пароль не указан, Кстестусеркредентиал предложит ввести эти данные.</span><span class="sxs-lookup"><span data-stu-id="fe76e-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="fe76e-123">Имя пользователя можно указать с помощью формата доменных\\имен, показанного выше, или с помощью команды формат имени пользователя @ доменного имени; Например:</span><span class="sxs-lookup"><span data-stu-id="fe76e-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="fe76e-124">Чтобы убедиться, что учетные данные тестового пользователя были созданы, выполните эти команды в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fe76e-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="fe76e-125">Данные, подобные этим, должны быть возвращены каждому пользователю:</span><span class="sxs-lookup"><span data-stu-id="fe76e-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="fe76e-126">Настройка основного узла наблюдения с синтетическими транзакциями по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fe76e-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="fe76e-127">После создания тестовых пользователей вы можете создать узел наблюдателя с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="fe76e-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="fe76e-128">Эта команда создает узел-наблюдатель с параметрами по умолчанию, который выполняет набор искусственных транзакций по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe76e-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="fe76e-129">Для нового узла-наблюдателя используются тестовые пользователи watcher1@litwareinc.com, watcher2@litwareinc.com и watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="fe76e-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="fe76e-130">Если узел наблюдателя использует проверку подлинности Трустедсервер, то три тестовых учетных записей могут быть любыми действительными учетными записями пользователей, включенными для службы каталогов Active Directory и Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe76e-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="fe76e-131">Если узел наблюдателя использует метод проверки подлинности Negotiate, необходимо также включить эти учетные записи пользователей для узла наблюдателя с помощью командлета **Set-кстестусеркредентиал** .</span><span class="sxs-lookup"><span data-stu-id="fe76e-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="fe76e-132">Настройка расширенных тестов</span><span class="sxs-lookup"><span data-stu-id="fe76e-132">Configuring Extended Tests</span></span>

<span data-ttu-id="fe76e-133">Если вы хотите включить коммутируемую телефонную сеть с открытым коммутируемым подключением (для проверки PSTN), которая проверяет связь с телефонной сетью с открытым подключением, вам потребуется дополнительная настройка при настройке узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="fe76e-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="fe76e-134">Сначала необходимо связать тестовых пользователей с типом проверки КТСОП.</span><span class="sxs-lookup"><span data-stu-id="fe76e-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="fe76e-135">Для этого выполните следующую команду в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe76e-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="fe76e-136">Обратите внимание, что результаты этой команды должны храниться в переменной.</span><span class="sxs-lookup"><span data-stu-id="fe76e-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="fe76e-137">В этом примере это переменная с именем $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="fe76e-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="fe76e-138">На этом этапе можно с помощью командлета **New-ксватчернодеконфигуратион** связать тип теста (хранящийся в переменной $pstnTest) с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe76e-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="fe76e-139">Например, следующая команда создает новую конфигурацию узла-наблюдателя для пула atl-cs-001.litwareinc.com, добавляя трех тестовых пользователей, которые были созданы ранее, а также добавляя тип теста КТСОП.</span><span class="sxs-lookup"><span data-stu-id="fe76e-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="fe76e-140">Обратите внимание на то, что предыдущая команда завершится сбоем, если вы не установили файлы основных файлов Lync Server и базу данных Ртклокал на компьютере с узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="fe76e-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="fe76e-141">Чтобы протестировать несколько политик голосовой связи, необходимо создать расширенный тест для каждой политики с помощью командлета **New-ксекстендедтест** .</span><span class="sxs-lookup"><span data-stu-id="fe76e-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="fe76e-142">Пользователи, которым вы назначили этот тест, должны настроить нужные политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="fe76e-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="fe76e-143">После этого Расширенные тесты передаются в командлет **New-ксватчернодеконфигуратион** с помощью команды, подобной приведенной ниже:</span><span class="sxs-lookup"><span data-stu-id="fe76e-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="fe76e-144">Если метод New-Ксватчернодеконфигуратион вызывается без использования параметра "тесты", это означает, что для нового узла-наблюдателя будут включены только синтетические транзакции по умолчанию (и указанная расширенная виртуальная транзакция).</span><span class="sxs-lookup"><span data-stu-id="fe76e-144">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="fe76e-145">Это означает, что узел наблюдателя будет тестировать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="fe76e-145">This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="fe76e-146">Registration</span><span class="sxs-lookup"><span data-stu-id="fe76e-146">Registration</span></span>

  - <span data-ttu-id="fe76e-147">IM</span><span class="sxs-lookup"><span data-stu-id="fe76e-147">IM</span></span>

  - <span data-ttu-id="fe76e-148">GroupIM (групповые мгновенные сообщения)</span><span class="sxs-lookup"><span data-stu-id="fe76e-148">GroupIM</span></span>

  - <span data-ttu-id="fe76e-149">P2PAV (одноранговые аудио- и видеосеансы)</span><span class="sxs-lookup"><span data-stu-id="fe76e-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="fe76e-150">AvConference (аудио- и видеоконференции)</span><span class="sxs-lookup"><span data-stu-id="fe76e-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="fe76e-151">Presence</span><span class="sxs-lookup"><span data-stu-id="fe76e-151">Presence</span></span>

  - <span data-ttu-id="fe76e-152">ABS (служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="fe76e-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="fe76e-153">ABWQ (веб-служба адресной книги)</span><span class="sxs-lookup"><span data-stu-id="fe76e-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="fe76e-154">PSTN (коммутируемые звонки шлюза, заданные в виде расширенного теста.</span><span class="sxs-lookup"><span data-stu-id="fe76e-154">PSTN (PSTN gateway calls, specified as an extended test.</span></span> <span data-ttu-id="fe76e-155">По умолчанию PSTN отключена.</span><span class="sxs-lookup"><span data-stu-id="fe76e-155">By default, PSTN is disabled.</span></span> <span data-ttu-id="fe76e-156">В этом случае проверка будет включена только в том случае, если команда включила протокол КТСОП с помощью параметра Екстендедтестс.)</span><span class="sxs-lookup"><span data-stu-id="fe76e-156">The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="fe76e-157">Это также означает, что следующие компоненты не будут протестированы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe76e-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="fe76e-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="fe76e-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="fe76e-159">MCXP2PIM (обмен мгновенными сообщениями с помощью мобильных устройств)</span><span class="sxs-lookup"><span data-stu-id="fe76e-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="fe76e-160">ExumConnectivity (единая система обмена сообщениями Exchange)</span><span class="sxs-lookup"><span data-stu-id="fe76e-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="fe76e-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="fe76e-161">JoinLauncher</span></span>

  - <span data-ttu-id="fe76e-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="fe76e-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="fe76e-163">DataConference</span><span class="sxs-lookup"><span data-stu-id="fe76e-163">DataConference</span></span>

  - <span data-ttu-id="fe76e-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="fe76e-164">XmppIM</span></span>

  - <span data-ttu-id="fe76e-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="fe76e-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="fe76e-166">Добавление и удаление искусственных транзакций</span><span class="sxs-lookup"><span data-stu-id="fe76e-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="fe76e-167">После настройки узла наблюдения можно использовать командлет **Set-ксватчернодеконфигуратион** , чтобы добавить или удалить из узла искусственные транзакции.</span><span class="sxs-lookup"><span data-stu-id="fe76e-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="fe76e-168">Например, чтобы добавить тест PersistentChatMessage на узел-наблюдатель, используйте следующую команду с методом Add.</span><span class="sxs-lookup"><span data-stu-id="fe76e-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="fe76e-169">При указании нескольких тестов используйте запятые.</span><span class="sxs-lookup"><span data-stu-id="fe76e-169">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="fe76e-170">Пример:</span><span class="sxs-lookup"><span data-stu-id="fe76e-170">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="fe76e-171">Обратите внимание, что если один или несколько из этих тестов (например, "Конференция") уже включены на узле наблюдателя, произойдет ошибка.</span><span class="sxs-lookup"><span data-stu-id="fe76e-171">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="fe76e-172">В этом случае вы получите следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="fe76e-172">In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="fe76e-173">Если произошла эта ошибка, изменения не применяются.</span><span class="sxs-lookup"><span data-stu-id="fe76e-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="fe76e-174">Команду следует повторно запустить с удаленным тестовым повторением.</span><span class="sxs-lookup"><span data-stu-id="fe76e-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="fe76e-175">Для удаления искусственной транзакции из узла-наблюдателя используйте метод Remove вместо метода Add.</span><span class="sxs-lookup"><span data-stu-id="fe76e-175">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method.</span></span> <span data-ttu-id="fe76e-176">Например, следующая команда удаляет тест ABWQ с узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="fe76e-176">For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="fe76e-177">Вы также можете использовать метод Replace для замены всех текущих тестов на один или несколько новых тестов.</span><span class="sxs-lookup"><span data-stu-id="fe76e-177">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="fe76e-178">Например, если вы хотите, чтобы узел наблюдателя мог выполнять тест IM, вы можете настроить его с помощью этой команды:</span><span class="sxs-lookup"><span data-stu-id="fe76e-178">For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="fe76e-179">При выполнении предыдущей команды все синтетические транзакции на указанном узле наблюдения будут отключены, кроме сообщений.</span><span class="sxs-lookup"><span data-stu-id="fe76e-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="fe76e-180">Просмотр и тестирование конфигурации узла-наблюдателя</span><span class="sxs-lookup"><span data-stu-id="fe76e-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="fe76e-181">Чтобы просмотреть тесты, назначенные узлу-наблюдателю, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="fe76e-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="fe76e-182">Предыдущая команда возвращает такие сведения, в зависимости от искусственных транзакций, которые были назначены узлу.</span><span class="sxs-lookup"><span data-stu-id="fe76e-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

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
> <span data-ttu-id="fe76e-183">Чтобы просмотреть искусственные транзакции в алфавитном порядке, используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="fe76e-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="fe76e-184">Get-Ксватчернодеконфигуратион – Identity "atl-cs-001.litwareinc.com" | Select-Object – Експандпропертиные тесты | Sort (объект)</span><span class="sxs-lookup"><span data-stu-id="fe76e-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="fe76e-185">Чтобы убедиться в том, что узел-наблюдатель создан, введите следующую команду в командной консоли Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="fe76e-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="fe76e-186">Вы получите примерно такую информацию:</span><span class="sxs-lookup"><span data-stu-id="fe76e-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="fe76e-187">Чтобы убедиться в правильности настройки узла-наблюдателя, введите в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fe76e-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="fe76e-188">Предыдущая команда протестирует каждый узел контрольного просмотра в развертывании и сообщает сведения о том, что:</span><span class="sxs-lookup"><span data-stu-id="fe76e-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="fe76e-189">Была установлена обязательная роль регистратора.</span><span class="sxs-lookup"><span data-stu-id="fe76e-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="fe76e-190">Требуемый раздел реестра был создан при запуске Set-Ксватчернодеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="fe76e-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="fe76e-191">На ваших серверах работает нужная версия Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe76e-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="fe76e-192">Порты настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="fe76e-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="fe76e-193">У назначенных тестовых пользователей есть необходимые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="fe76e-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

