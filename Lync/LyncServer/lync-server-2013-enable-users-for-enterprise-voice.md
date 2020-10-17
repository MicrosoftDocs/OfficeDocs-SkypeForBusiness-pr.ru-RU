---
title: 'Lync Server 2013: включение пользователей для корпоративной голосовой связи'
description: 'Lync Server 2013: включение пользователей для корпоративной голосовой связи.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa8dbbeb507ced5217e517c1608c3a2a9259668
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557655"
---
# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="cfd85-103">Разрешить пользователям использовать корпоративную голосовую связь в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfd85-103">Enable users for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfd85-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cfd85-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cfd85-105">После установки файлов для одного или нескольких серверов-посредников Настройте маршрутизацию исходящих вызовов и при необходимости разверните одну или несколько расширенных функций корпоративной голосовой связи, чтобы разрешить пользователю совершать звонки с помощью корпоративной голосовой связи, можно использовать следующие процедуры:</span><span class="sxs-lookup"><span data-stu-id="cfd85-105">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cfd85-106">Из следующих процедур можно выполнить только первый из них с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cfd85-106">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="cfd85-107">В остальных процедурах можно использовать только командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cfd85-107">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="cfd85-108">Включение учетной записи пользователя для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cfd85-108">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="cfd85-109">(Необязательно) Назначьте учетной записи пользователя определенную политику голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cfd85-109">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="cfd85-110">(Необязательно) Назначьте учетной записи пользователя определенную абонентскую группу.</span><span class="sxs-lookup"><span data-stu-id="cfd85-110">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="cfd85-111">Включение учетной записи пользователя для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="cfd85-111">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="cfd85-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cfd85-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cfd85-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cfd85-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cfd85-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cfd85-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cfd85-115">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="cfd85-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="cfd85-116">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="cfd85-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="cfd85-117">В таблице щелкните учетную запись пользователя, для которой необходимо включить поддержку корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cfd85-117">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="cfd85-118">В меню **Правка** выберите команду **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="cfd85-118">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="cfd85-119">На странице **Изменение пользователя Lync Server** в разделе **Телефония** щелкните **Корпоративная голосовая связь**.</span><span class="sxs-lookup"><span data-stu-id="cfd85-119">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="cfd85-120">Щелкните **Строковый URI** и введите уникальный нормализованный номер телефона (например, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="cfd85-120">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="cfd85-121">Щелкните **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="cfd85-121">Click **Commit**.</span></span>

<span data-ttu-id="cfd85-122">Чтобы завершить включение пользователя для корпоративной голосовой связи, убедитесь, что пользователю назначена политика голосовой связи и абонентская группы, будь это глобальная (назначенная по умолчанию) или пользовательская.</span><span class="sxs-lookup"><span data-stu-id="cfd85-122">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="cfd85-123">По умолчанию всем пользователям назначается глобальная голосовая политика и абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="cfd85-123">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="cfd85-124">Если голосовая политика или абонентская группа существуют на уровне сайта для того сайта, на котором размещена учетная запись пользователя, эта политика будет автоматически применена к пользователю.</span><span class="sxs-lookup"><span data-stu-id="cfd85-124">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="cfd85-125">Чтобы применить голосовую политику или абонентскую группу на уровне пользователя к определенному пользователю, необходимо выполнить командлеты **Grant-CsVoicePolicy** и **Grant-CsDialPlan**.</span><span class="sxs-lookup"><span data-stu-id="cfd85-125">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="cfd85-126">Дополнительные сведения см. в документации по [командной консоли Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="cfd85-126">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="cfd85-127">Назначение политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="cfd85-127">Voice Policy Assignment</span></span>

<span data-ttu-id="cfd85-128">Глобальные и на уровне сайта политики голосовой связи автоматически назначаются всем учетным записям пользователей, для которых включена поддержка корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cfd85-128">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="cfd85-129">Вы также можете создать политики, которые применяются к определенным пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="cfd85-129">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="cfd85-130">Их необходимо назначить явно.</span><span class="sxs-lookup"><span data-stu-id="cfd85-130">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="cfd85-131">Если вы хотите использовать глобальную политику голосовой связи для всех пользователей с включенной поддержкой корпоративной голосовой связи, вы можете пропустить этот раздел и перейти к разделу назначение абонентской группы позже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cfd85-131">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="cfd85-132">Назначение политики голосовой связи для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="cfd85-132">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="cfd85-133">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cfd85-133">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cfd85-134">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cfd85-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cfd85-135">Чтобы назначить существующую политику голосовой связи пользователю, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="cfd85-135">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="cfd85-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="cfd85-136">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="cfd85-137">В этом примере пользователю с отображаемым именем Bob Kelly назначается политика голосовой связи с именем **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="cfd85-137">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="cfd85-138">Дополнительные сведения о назначении политики голосовой связи для конкретных пользователей или о запуске командлета **Grant – CsVoicePolicy** можно найти в документации по [среде управления Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="cfd85-138">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="cfd85-139">Назначение абонентской группы</span><span class="sxs-lookup"><span data-stu-id="cfd85-139">Dial Plan Assignment</span></span>

<span data-ttu-id="cfd85-140">Чтобы выполнить настройку учетной записи пользователя как для пользователей корпоративной голосовой связи, так и для пользователей конференц-связи с телефонным подключением, этот пользователь должен быть назначен соответствующей абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="cfd85-140">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="cfd85-141">Учетные записи пользователей будут автоматически применять глобальную абонентскую группу или, если такая имеется, абонентскую группу на уровне сайта, если вы явно не назначите абонентскую группу для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="cfd85-141">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="cfd85-142">Если вы хотите использовать глобальную или глобальную абонентскую схему для всех пользователей с включенной поддержкой корпоративной голосовой связи, вы можете пропустить этот раздел.</span><span class="sxs-lookup"><span data-stu-id="cfd85-142">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="cfd85-143">Назначение абонентской группы</span><span class="sxs-lookup"><span data-stu-id="cfd85-143">To assign a dial plan</span></span>

1.  <span data-ttu-id="cfd85-144">Из учетной записи пользователя, назначенной роли  CsUserAdministrator или CsAdministrator, выполните вход на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="cfd85-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cfd85-145">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cfd85-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cfd85-146">Чтобы назначить абонентскую группу для отдельных пользователей, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="cfd85-146">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="cfd85-147">Пример:</span><span class="sxs-lookup"><span data-stu-id="cfd85-147">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="cfd85-148">В этом примере пользователю с отображаемым именем Bob Kelly назначается абонентская абонентская схема с именем **voicepolicyjapan**.</span><span class="sxs-lookup"><span data-stu-id="cfd85-148">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="cfd85-149">Для получения дополнительных сведений о назначении абонентской группы или о запуске командлета **Grant – CsDialPlan** , ознакомьтесь с документацией по [среде управления Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="cfd85-149">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cfd85-150">См. также</span><span class="sxs-lookup"><span data-stu-id="cfd85-150">See Also</span></span>


[<span data-ttu-id="cfd85-151">Отключение пользователя для корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfd85-151">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

