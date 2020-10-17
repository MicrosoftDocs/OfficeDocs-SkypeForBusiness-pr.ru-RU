---
title: 'Lync Server 2013: Включение удаленного управления звонками для пользователей Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d5aa0b9f13f17dee91ff48048908cde3dbc2cf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528736"
---
# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="73b5b-102">Включение удаленного управления звонками для пользователей Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b5b-102">Enable Lync users for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73b5b-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="73b5b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="73b5b-104">Пользователи Lync можно настроить для управления удаленными звонками с помощью политик подготовки в стандартном канале, которые основаны на сервере.</span><span class="sxs-lookup"><span data-stu-id="73b5b-104">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="73b5b-105">Вы можете управлять параметрами подготовки в стандартном режиме с помощью панели управления Lync Server или интерфейса командной строки командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73b5b-105">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="73b5b-106">Эти средства заменяют оснастку инструментария управления Windows (WMI), используемую для управления параметрами групповой политики в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="73b5b-106">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="73b5b-107">Если вы хотите позволить пользователям настроить собственные параметры управления удаленными звонками в Lync, вы можете настроить параметры для пользователей на сервере, не указывая значения параметров **Линейный URI сервера** и **Линейный URI**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-107">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="73b5b-108">Передайте соответствующие значения параметров **Линейный URI сервера** и **Линейный URI** пользователям и предоставьте им инструкции по настройке этих параметров.</span><span class="sxs-lookup"><span data-stu-id="73b5b-108">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="73b5b-109">Процедура настройки удаленного управления звонками в Lync Server вручную приведена в разделе "Установка параметров и номеров телефонов" в <https://go.microsoft.com/fwlink/p/?linkid=210132> документации клиента Lync на веб-сайте Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="73b5b-109">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <https://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="73b5b-110">Если у вас есть существующее развертывание сервера Communications Server 2007 R2 или Communications Server 2007, Communicator 2007 R2 и Communicator 2007 клиенты продолжат использовать групповую политику в ходе параллельной миграции.</span><span class="sxs-lookup"><span data-stu-id="73b5b-110">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="73b5b-111">Тем не менее, если вы хотите, чтобы параметры политики выполнялись для клиентов Lync, необходимо настроить соответствующие параметры подготовки в стандартном сервере Lync.</span><span class="sxs-lookup"><span data-stu-id="73b5b-111">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73b5b-112">Чтобы включить для пользователя управление удаленными звонками, у пользователя должен быть линейный URI и линейный URI сервера.</span><span class="sxs-lookup"><span data-stu-id="73b5b-112">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="73b5b-113">Как описано в разделе <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">задачи развертывания для удаленного управления звонками в Lync Server 2013</A>, необходимо обязательно использовать синтаксис, необходимый шлюзу для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="73b5b-113">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="73b5b-114">Убедитесь, что домен в линейном URI сервера совпадает с конечным доменом, указанном в параметре MatchUri, при настройке статического маршрута до шлюза.</span><span class="sxs-lookup"><span data-stu-id="73b5b-114">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="73b5b-p105">Линейный URI определяет номер телефона, назначенный пользователю, в формате E.164 с префиксом "TEL:" (например, tel:+14255550150). Если вы хотите настроить добавочный номер, то используется формат tel:+14255550150;ext=111. Если вы ранее настроили линейный URI пользователя и это значение не изменилось, вам не нужно указывать линейный URI при включении управления удаленными звонками для пользователя.</span><span class="sxs-lookup"><span data-stu-id="73b5b-p105">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150). If you want to configure an extension number, then the format is tel:+14255550150;ext=111. If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="73b5b-118">Включение управления удаленными звонками для пользователей с поддержкой Lync с помощью командной консоли</span><span class="sxs-lookup"><span data-stu-id="73b5b-118">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="73b5b-119">Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или роли управления доступом на основе ролей, которой назначен командлет **Set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="73b5b-119">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="73b5b-120">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="73b5b-121">Чтобы использовать командлет **Set-CsUser** для настройки управления удаленными звонками для существующего пользователя с поддержкой Lync, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="73b5b-121">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="73b5b-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="73b5b-122">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="73b5b-123">Настройка пользователей для управления удаленными звонками с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="73b5b-123">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="73b5b-124">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="73b5b-124">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="73b5b-125">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73b5b-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="73b5b-126">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="73b5b-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="73b5b-127">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-127">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="73b5b-128">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM, SIP-адрес или линейный идентификатор URI учетной записи пользователя, которая требуется, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-128">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="73b5b-129">В таблице щелкните учетную запись пользователя, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="73b5b-129">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="73b5b-130">В меню **Правка** щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-130">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="73b5b-131">В разделе **Телефония** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="73b5b-131">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="73b5b-132">Чтобы разрешить удаленному управлению звонкам разрешить пользователю управлять телефонной УАТС из Lync 2013, чтобы совершать голосовые звонки между компьютерами и телефонами, нажмите кнопку **Удаленное управление звонками**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-132">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="73b5b-133">В поле **Линейный URI** укажите номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="73b5b-133">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="73b5b-134">В поле **Линейный URI сервера** укажите SIP URI шлюза SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="73b5b-134">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="73b5b-135">Чтобы включить удаленное управление звонками, но отключить голосовые вызовы между ПК и ПК, а также разрешить пользователю управлять телефон УАТС из Lync 2013 для совершения звонков с ПК на телефон, выберите **только удаленное управление звонками**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-135">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="73b5b-136">В поле **Линейный URI** укажите номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="73b5b-136">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="73b5b-137">В поле **Линейный URI сервера** укажите SIP URI шлюза SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="73b5b-137">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="73b5b-138">По завершении щелкните **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-138">When you are finished, click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

