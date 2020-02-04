---
title: 'Lync Server 2013: включение удаленного управления звонками для пользователей Lync'
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
ms.openlocfilehash: 260cfc2d3a0b185d58e90f4944162ea23135a0b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="26ea7-102">Включение удаленного управления звонками для пользователей Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26ea7-102">Enable Lync users for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26ea7-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="26ea7-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="26ea7-104">Вы можете настроить пользователей Lync для удаленного управления звонками, используя политики подготовки по стандарту, которые являются серверными.</span><span class="sxs-lookup"><span data-stu-id="26ea7-104">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="26ea7-105">Вы можете управлять параметрами подготовки по каналу с помощью панели управления Lync Server или интерфейса командной строки оболочки Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="26ea7-105">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="26ea7-106">Эти средства заменяют оснастку WMI (инструментарий управления Windows), которая использовалась для управления параметрами групповой политики в более ранних выпусках.</span><span class="sxs-lookup"><span data-stu-id="26ea7-106">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="26ea7-107">Если вы хотите, чтобы пользователи могли настраивать собственные параметры удаленного управления звонками в Lync, вы можете настроить параметры удаленного управления звонками для пользователей на сервере без указания **URI** и значений **URI** для строк сервера.</span><span class="sxs-lookup"><span data-stu-id="26ea7-107">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="26ea7-108">Убедитесь в том, что вы сообщаете соответствующим пользователям **строковый URI** и значения **универсальных кодов (URI** ), а также предоставьте пользователям инструкции по настройке этих параметров.</span><span class="sxs-lookup"><span data-stu-id="26ea7-108">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="26ea7-109">Процедура настройки удаленного управления звонками вручную в Lync Server приведена в разделе "Настройка параметров и номеров телефонов" <http://go.microsoft.com/fwlink/p/?linkid=210132> в документации клиента Lync на веб-сайте Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="26ea7-109">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <http://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="26ea7-110">Если у вас есть существующая связь между сервером Communications Server 2007 R2 или Communications Server 2007, Пользователи Communicator 2007 R2 и Communicator 2007 будут продолжать использовать групповую политику при переходе на другую сторону.</span><span class="sxs-lookup"><span data-stu-id="26ea7-110">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="26ea7-111">Тем не менее, если вы хотите, чтобы параметры политики настроились на работу с клиентами Lync, необходимо настроить соответствующие параметры подготовки в стандарте Lync Server.</span><span class="sxs-lookup"><span data-stu-id="26ea7-111">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26ea7-112">Чтобы разрешить пользователю удаленное управление звонками, необходимо предоставить пользователю как универсальный код ресурса (URI), так и URI сервера строки.</span><span class="sxs-lookup"><span data-stu-id="26ea7-112">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="26ea7-113">Как описано в разделе <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">задачи развертывания для удаленного управления звонками в Lync Server 2013</A>, необходимо обязательно использовать синтаксис, необходимый шлюзом для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="26ea7-113">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="26ea7-114">Убедитесь, что домен в URI сервера линии совпадает с конечным доменом, указанным в параметре Матчури, при настройке статического маршрута к шлюзу.</span><span class="sxs-lookup"><span data-stu-id="26ea7-114">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="26ea7-115">Универсальный код ресурса (URI) для строки — номер телефона, назначенный пользователю в формате E. 164, с префиксом "TEL:" (например, Tel: + 14255550150).</span><span class="sxs-lookup"><span data-stu-id="26ea7-115">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150).</span></span> <span data-ttu-id="26ea7-116">Если вы хотите настроить добавочный номер, выберите формат Tel: + 14255550150; ext = 111.</span><span class="sxs-lookup"><span data-stu-id="26ea7-116">If you want to configure an extension number, then the format is tel:+14255550150;ext=111.</span></span> <span data-ttu-id="26ea7-117">Если ранее вы настроили универсальный код ресурса (URI) для строки пользователя и значение не изменилось, вам не нужно указывать универсальный код ресурса (URI) для строки, когда вы включите удаленное управление звонком.</span><span class="sxs-lookup"><span data-stu-id="26ea7-117">If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="26ea7-118">Включение удаленного управления звонком для пользователей с поддержкой Lync с помощью командной консоли</span><span class="sxs-lookup"><span data-stu-id="26ea7-118">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="26ea7-119">Войдите в систему на компьютере, на котором установлена консоль управления Lync Server, в качестве участника группы Рткуниверсалсерверадминс или роли управления доступом на основе ролей, которой назначен командлет **Set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="26ea7-119">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="26ea7-120">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="26ea7-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="26ea7-121">Чтобы использовать командлет **Set-CsUser** для настройки удаленного управления звонками для существующего пользователя с поддержкой Lync, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="26ea7-121">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="26ea7-122">Например:</span><span class="sxs-lookup"><span data-stu-id="26ea7-122">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="26ea7-123">Настройка пользователей для удаленного управления звонками с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="26ea7-123">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="26ea7-124">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="26ea7-124">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="26ea7-125">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="26ea7-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="26ea7-126">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="26ea7-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="26ea7-127">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="26ea7-127">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="26ea7-128">В поле **Поиск пользователей** введите все (или первую часть) отображаемого имени, имя, фамилию, имя учетной записи диспетчера учетных записей безопасности (SAM), адрес SIP или универсальный код ресурса (URI) для учетной записи пользователя, а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="26ea7-128">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="26ea7-129">В таблице выберите учетную запись пользователя, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="26ea7-129">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="26ea7-130">В меню **Правка** выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="26ea7-130">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="26ea7-131">В разделе **телефония**выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="26ea7-131">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="26ea7-132">Чтобы включить удаленное управление звонками, чтобы разрешить пользователю управлять телефонным подключением к личной ветвью из Lync 2013, чтобы звонить между компьютерами и телефонными звонками с компьютера на компьютер, нажмите **Удаленное управление звонками**.</span><span class="sxs-lookup"><span data-stu-id="26ea7-132">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="26ea7-133">В **URI строки**укажите номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="26ea7-133">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="26ea7-134">В **URI сервера графики**укажите URI SIP шлюза SIP/кста.</span><span class="sxs-lookup"><span data-stu-id="26ea7-134">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="26ea7-135">Чтобы включить удаленное управление звонками, но отключить голосовые звонки между компьютерами и разрешить только пользователю управлять телефоном УАТС из Lync 2013 для звонков с компьютера на телефон, выберите **только удаленный Звонок**.</span><span class="sxs-lookup"><span data-stu-id="26ea7-135">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="26ea7-136">В **URI строки**укажите номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="26ea7-136">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="26ea7-137">В **URI сервера графики**укажите URI SIP шлюза SIP/кста.</span><span class="sxs-lookup"><span data-stu-id="26ea7-137">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="26ea7-138">Когда все будет готово, нажмите кнопку **зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="26ea7-138">When you are finished, click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

