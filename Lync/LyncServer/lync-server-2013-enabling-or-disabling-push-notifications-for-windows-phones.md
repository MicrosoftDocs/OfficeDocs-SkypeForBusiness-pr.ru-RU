---
title: 'Lync Server 2013: Включение и отключение push-уведомлений для телефонов с Windows'
description: 'Lync Server 2013: Включение и отключение push-уведомлений для телефонов с Windows.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba3748c56291b8c6eb236edaac7e23a9e00e5e98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543475"
---
# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a><span data-ttu-id="9ff87-103">Включение и отключение push-уведомлений для телефонов с Windows в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ff87-103">Enabling or disabling push notifications for Windows Phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ff87-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9ff87-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9ff87-105">Push-уведомления в форме эмблем, значков или оповещений можно отправлять на телефон Windows, даже если мобильное приложение неактивно.</span><span class="sxs-lookup"><span data-stu-id="9ff87-105">Push notifications, in the form of badges, icons, or alerts, can be sent to a Windows Phone even when the mobile application is inactive.</span></span> <span data-ttu-id="9ff87-106">Push-уведомления сообщают пользователю о событиях, таких как новые или пропущенные приглашения в сеанс обмена мгновенными сообщениями, а также новые сообщения голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="9ff87-106">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="9ff87-107">Вы можете включать и отключать push-уведомления для устройств с Windows Phone с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ff87-107">You can enable or disable push notifications for Windows Phone devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="9ff87-108">Включение push-уведомлений для Windows Phone с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="9ff87-108">To enable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9ff87-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9ff87-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9ff87-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ff87-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9ff87-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9ff87-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9ff87-112">В левой панели навигации щелкните **Клиенты**, а затем щелкните кнопку навигации **Настройка push-уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="9ff87-112">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="9ff87-113">На странице **Настройка push-уведомлений** выберите сайт, который нужно изменить, щелкните меню **Правка** и выберите команду **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="9ff87-113">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9ff87-114">Установите флажок **Разрешить push-уведомления от Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="9ff87-114">Click the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="9ff87-115">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="9ff87-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="9ff87-116">Отключение push-уведомлений для Windows Phone с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="9ff87-116">To disable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9ff87-117">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9ff87-117">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9ff87-118">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ff87-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9ff87-119">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9ff87-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9ff87-120">В левой панели навигации щелкните **Клиенты**, а затем щелкните кнопку навигации **Настройка push-уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="9ff87-120">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="9ff87-121">На странице **Настройка push-уведомлений** выберите сайт, который нужно изменить, щелкните меню **Правка** и выберите команду **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="9ff87-121">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9ff87-122">Снимите флажок **Разрешить push-уведомления от Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="9ff87-122">Clear the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="9ff87-123">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="9ff87-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9ff87-124">Включение и отключение push-уведомлений для Windows Phone с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ff87-124">Enabling or Disabling Push Notifications for Windows Phone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9ff87-125">Вы можете включать и отключать push-уведомления для Windows Phone с помощью командлета **Set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9ff87-125">You can enable or disable push notifications for Windows Phone by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="9ff87-126">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ff87-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9ff87-127">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="9ff87-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a><span data-ttu-id="9ff87-128">Включение push-уведомлений для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="9ff87-128">To enable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="9ff87-129">Чтобы включить push-уведомления для Windows Phone, установите для свойства Енаблемикрософтпушнотификатионсервице значение true ($True).</span><span class="sxs-lookup"><span data-stu-id="9ff87-129">To enable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to True ($True).</span></span> <span data-ttu-id="9ff87-130">Например:</span><span class="sxs-lookup"><span data-stu-id="9ff87-130">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a><span data-ttu-id="9ff87-131">Отключение push-уведомлений для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="9ff87-131">To disable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="9ff87-132">Чтобы отключить push-уведомления для Windows Phone, установите для свойства Енаблемикрософтпушнотификатионсервице значение false ($False).</span><span class="sxs-lookup"><span data-stu-id="9ff87-132">To disable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to False ($False).</span></span> <span data-ttu-id="9ff87-133">Например:</span><span class="sxs-lookup"><span data-stu-id="9ff87-133">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

<span data-ttu-id="9ff87-134">Дополнительные сведения см. в разделе справки о командлете [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="9ff87-134">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9ff87-135">См. также</span><span class="sxs-lookup"><span data-stu-id="9ff87-135">See Also</span></span>


[<span data-ttu-id="9ff87-136">Настройка для push-уведомлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ff87-136">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

