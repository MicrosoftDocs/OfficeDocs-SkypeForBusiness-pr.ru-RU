---
title: 'Lync Server 2013: отключение и повторное включение учетной записи пользователя Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7944af89ffae7545ba3a2593c7617fc944a7916e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="cd52b-102">Отключение и повторное включение учетной записи пользователя для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd52b-102">Disable or re-enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd52b-103">_**Тема последнего изменения:** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="cd52b-103">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="cd52b-104">Вы можете использовать описанную ниже процедуру, чтобы отключить ранее включенную учетную запись пользователя в Lync Server 2013 без потери параметров сервера Lync Server, настроенных для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd52b-104">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="cd52b-105">Так как вы не потеряли параметры учетной записи пользователя Lync Server, вы можете снова включить ее еще раз, не требуя повторной настройки учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd52b-105">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="cd52b-106">Отключение учетной записи пользователя в службе каталогов Active Directory <STRONG>не</STRONG> означает, что пользователь сможет войти в Lync Server или использовать его.</span><span class="sxs-lookup"><span data-stu-id="cd52b-106">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="cd52b-107">Это связано с тем, что Lync использует проверку подлинности сертификата, которая упрощает процесс проверки подлинности, и эти клиентские сертификаты действительны в течение 180 дней.</span><span class="sxs-lookup"><span data-stu-id="cd52b-107">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="cd52b-108">Если вы хотите отключить отключенные учетные записи Active Directory, для которых в Lync разрешен доступ к серверу Lync Server, необходимо использовать командлет <STRONG>Disable-CsUser</STRONG> или воспользоваться <STRONG>панелью управления Lync Server</STRONG> в соответствии с инструкциями, изложенными в этой статье.</span><span class="sxs-lookup"><span data-stu-id="cd52b-108">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="cd52b-109">После того как пользователь отключен в Lync и хранилище Центрального управления будет реплицировано в среде, пользователи больше не смогут входить.</span><span class="sxs-lookup"><span data-stu-id="cd52b-109">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="cd52b-110">Кроме того, пользователи, которые вошли в систему, будут отключены.</span><span class="sxs-lookup"><span data-stu-id="cd52b-110">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="cd52b-111">Отключение и повторное включение учетной записи пользователя, включенного в Lync Server</span><span class="sxs-lookup"><span data-stu-id="cd52b-111">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="cd52b-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cd52b-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cd52b-113">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cd52b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cd52b-114">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cd52b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cd52b-115">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="cd52b-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="cd52b-116">В поле **Поиск пользователей** введите все или первую часть отображаемого имени, имя, фамилию, диспетчер учетных записей безопасности (SAM), имя учетной записи, адрес SIP или универсальный код ресурса (URI) для учетной записи пользователя, которую вы хотите отключить или включить заново. и нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="cd52b-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="cd52b-117">В таблице выберите учетную запись пользователя, которую вы хотите отключить или включить заново.</span><span class="sxs-lookup"><span data-stu-id="cd52b-117">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="cd52b-118">В меню **действия** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="cd52b-118">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="cd52b-119">Чтобы временно отключить учетную запись пользователя для Lync Server 2013, выберите **временно отключить для Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cd52b-119">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="cd52b-120">Чтобы включить учетную запись пользователя для Lync Server 2013, нажмите кнопку **повторно включить для Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cd52b-120">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="cd52b-121">Использование Windows PowerShell для отключения и повторного включения учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="cd52b-121">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="cd52b-122">Учетные записи пользователей можно временно отключить, а затем снова включить с помощью командлета **Set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="cd52b-122">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="cd52b-123">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd52b-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cd52b-124">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd52b-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="cd52b-125">Отключение учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="cd52b-125">To disable a user account</span></span>

  - <span data-ttu-id="cd52b-126">Чтобы временно отключить учетную запись пользователя, установите для свойства Enabled значение false ($False).</span><span class="sxs-lookup"><span data-stu-id="cd52b-126">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="cd52b-127">Например:</span><span class="sxs-lookup"><span data-stu-id="cd52b-127">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="cd52b-128">Повторное включение учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="cd52b-128">To re-enable a user account</span></span>

  - <span data-ttu-id="cd52b-129">Чтобы повторно включить отключенную учетную запись пользователя, установите для свойства Enabled значение true ($True).</span><span class="sxs-lookup"><span data-stu-id="cd52b-129">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="cd52b-130">Например:</span><span class="sxs-lookup"><span data-stu-id="cd52b-130">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="cd52b-131">Дополнительные сведения можно найти в разделе справки по командлету [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="cd52b-131">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cd52b-132">См. также</span><span class="sxs-lookup"><span data-stu-id="cd52b-132">See Also</span></span>


[<span data-ttu-id="cd52b-133">Добавление и включение учетной записи пользователя для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd52b-133">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="cd52b-134">Включение и отключение пользователей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd52b-134">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

