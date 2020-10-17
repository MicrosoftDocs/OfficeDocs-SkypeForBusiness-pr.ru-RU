---
title: 'Lync Server 2013: отключение или повторное включение учетной записи пользователя для Lync Server'
description: 'Lync Server 2013: отключение или повторное включение учетной записи пользователя для Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b30d83d7a7f38b84f8e669ac06947eebf4a8545
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568175"
---
# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="1412a-103">Отключение или повторное включение учетной записи пользователя для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1412a-103">Disable or re-enable user account for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1412a-104">_**Последнее изменение темы:** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="1412a-104">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="1412a-105">Вы можете использовать следующую процедуру, чтобы отключить ранее включенную учетную запись пользователя в Lync Server 2013 без потери параметров Lync Server, настроенных для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="1412a-105">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="1412a-106">Так как параметры учетной записи пользователя Lync Server не теряются, вы можете повторно включить учетную запись пользователя, включенную ранее, без необходимости повторной настройки учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="1412a-106">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1412a-107">Простое отключение учетной записи пользователя в Active Directory <STRONG>не приведет</STRONG> к прекращению входа пользователя в систему или использования Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1412a-107">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="1412a-108">Это связано с тем, что Lync использует проверку подлинности с помощью сертификата, которая упрощает процесс проверки подлинности, и эти сертификаты клиентов действительны в течение 180 дней.</span><span class="sxs-lookup"><span data-stu-id="1412a-108">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="1412a-109">Если вы хотите остановить отключение отключенных учетных записей Active Directory, для которых в Lync был разрешен доступ к Lync Server, необходимо использовать командлет <STRONG>Disable – CsUser</STRONG> или использовать <STRONG>Панель управления Lync Server</STRONG> , как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="1412a-109">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="1412a-110">После отключения пользователя в Lync и репликации центрального хранилища управления в среде пользователи больше не смогут выполнять вход.</span><span class="sxs-lookup"><span data-stu-id="1412a-110">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="1412a-111">Кроме того, пользователи, которые вошли в систему, будут отключены.</span><span class="sxs-lookup"><span data-stu-id="1412a-111">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="1412a-112">Отключение или повторное включение учетной записи пользователя, включенной ранее для Lync Server</span><span class="sxs-lookup"><span data-stu-id="1412a-112">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="1412a-113">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1412a-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1412a-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1412a-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1412a-115">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1412a-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1412a-116">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="1412a-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="1412a-117">В поле **Search users** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, которую требуется отключить или активировать повторно, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="1412a-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="1412a-118">В таблице щелкните учетную запись пользователя, которую необходимо отключить или активировать повторно.</span><span class="sxs-lookup"><span data-stu-id="1412a-118">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="1412a-119">В меню **Действие** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1412a-119">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="1412a-120">Чтобы временно отключить учетную запись пользователя для Lync Server 2013, выберите **временно отключить для Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1412a-120">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="1412a-121">Чтобы включить учетную запись пользователя для Lync Server 2013, нажмите кнопку **повторно включить для Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1412a-121">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="1412a-122">Использование Windows PowerShell для отключения или повторного включения учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="1412a-122">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="1412a-123">Учетные записи пользователей можно временно отключить, а затем снова включить с помощью командлета **Set – CsUser** .</span><span class="sxs-lookup"><span data-stu-id="1412a-123">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="1412a-124">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1412a-124">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1412a-125">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="1412a-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="1412a-126">Отключение учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="1412a-126">To disable a user account</span></span>

  - <span data-ttu-id="1412a-127">Чтобы временно отключить учетную запись пользователя, установите значение свойства "Enabled" равным False ($False).</span><span class="sxs-lookup"><span data-stu-id="1412a-127">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="1412a-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="1412a-128">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="1412a-129">Повторное включение учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="1412a-129">To re-enable a user account</span></span>

  - <span data-ttu-id="1412a-130">Чтобы повторно включить отключенную учетную запись пользователя, установите значение свойства "Enabled" равным True ($True).</span><span class="sxs-lookup"><span data-stu-id="1412a-130">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="1412a-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="1412a-131">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="1412a-132">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="1412a-132">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1412a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="1412a-133">See Also</span></span>


[<span data-ttu-id="1412a-134">Добавление и включение учетной записи пользователя для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1412a-134">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="1412a-135">Включение и отключение пользователей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1412a-135">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

