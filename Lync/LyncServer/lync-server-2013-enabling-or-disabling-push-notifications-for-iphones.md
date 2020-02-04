---
title: 'Lync Server 2013: Включение и отключение push-уведомлений для iPhone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a73d0f32da5063f98da662e85ec531de6801a428
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a><span data-ttu-id="30601-102">Включение и отключение push-уведомлений для iPhone в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30601-102">Enabling or disabling push notifications for iPhones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30601-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="30601-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="30601-104">Push-уведомления, в форме индикаторов, значков или оповещений, могут отправляться на iPhone, даже если мобильное приложение неактивно.</span><span class="sxs-lookup"><span data-stu-id="30601-104">Push notifications, in the form of badges, icons, or alerts, can be sent to an iPhone even when the mobile application is inactive.</span></span> <span data-ttu-id="30601-105">Push-уведомления извещать пользователей о таких событиях, как новое или пропущенное приглашение на обмен мгновенными сообщениями и голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="30601-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="30601-106">Вы можете включить или отключить push-уведомления для iPhone с помощью панели управления Lync Server 2013 или оболочки управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="30601-106">You can enable or disable push notifications for iPhone by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="30601-107">Включение push-уведомлений для iPhone с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="30601-107">To enable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="30601-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="30601-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="30601-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="30601-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="30601-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="30601-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="30601-111">На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Навигация по **конфигурации push-уведомлений** .</span><span class="sxs-lookup"><span data-stu-id="30601-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="30601-112">На странице **Конфигурация push-уведомлений** выберите сайт, который вы хотите изменить, а затем в меню **Правка** выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="30601-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="30601-113">Установите флажок **включить push-уведомления Apple** .</span><span class="sxs-lookup"><span data-stu-id="30601-113">Click the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="30601-114">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="30601-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="30601-115">Отключение push-уведомлений для iPhone с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="30601-115">To disable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="30601-116">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="30601-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="30601-117">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="30601-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="30601-118">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="30601-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="30601-119">На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Навигация по **конфигурации push-уведомлений** .</span><span class="sxs-lookup"><span data-stu-id="30601-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="30601-120">На странице **Конфигурация push-уведомлений** выберите сайт, который вы хотите изменить, а затем в меню **Правка** выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="30601-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="30601-121">Снимите флажок **включить push-уведомления Apple** .</span><span class="sxs-lookup"><span data-stu-id="30601-121">Clear the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="30601-122">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="30601-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="30601-123">Включение и отключение push-уведомлений на iPhone с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="30601-123">Enabling or Disabling Push Notifications to iPhone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="30601-124">С помощью командлета **Set-кспушнотификатионконфигуратион** можно включить или отключить извещающие уведомления для Apple iPhone.</span><span class="sxs-lookup"><span data-stu-id="30601-124">Push notifications to Apple iPhone can be enabled or disabled by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="30601-125">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30601-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="30601-126">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30601-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone"></a><span data-ttu-id="30601-127">Включение push-уведомлений для iPhone</span><span class="sxs-lookup"><span data-stu-id="30601-127">To enable push notifications for iPhone</span></span>

  - <span data-ttu-id="30601-128">Чтобы включить push-уведомления для iPhone, установите для свойства Енаблеапплепушнотификатионсервице значение true ($True).</span><span class="sxs-lookup"><span data-stu-id="30601-128">To enable push notifications for iPhone set the value of the EnableApplePushNotificationService property to True ($True).</span></span> <span data-ttu-id="30601-129">Например:</span><span class="sxs-lookup"><span data-stu-id="30601-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a><span data-ttu-id="30601-130">Отключение push-уведомлений для iPhone</span><span class="sxs-lookup"><span data-stu-id="30601-130">To disable push notifications for iPhone</span></span>

  - <span data-ttu-id="30601-131">Чтобы отключить push-уведомления для iPhone, установите для свойства Енаблеапплепушнотификатионсервице значение false ($False).</span><span class="sxs-lookup"><span data-stu-id="30601-131">To disable push notifications for iPhone set the value of the EnableApplePushNotificationService property to False ($False).</span></span> <span data-ttu-id="30601-132">Например:</span><span class="sxs-lookup"><span data-stu-id="30601-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

<span data-ttu-id="30601-133">Дополнительные сведения можно найти в разделе справки по командлету [Set-кспушнотификатионконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="30601-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="30601-134">См. также</span><span class="sxs-lookup"><span data-stu-id="30601-134">See Also</span></span>


[<span data-ttu-id="30601-135">Настройка для использования push-уведомлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30601-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

