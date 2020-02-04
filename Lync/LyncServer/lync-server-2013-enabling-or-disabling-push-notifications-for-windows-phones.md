---
title: 'Lync Server 2013: Включение и отключение push-уведомлений для телефонов с Windows'
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
ms.openlocfilehash: d1b4c8f1f86fa1456230ad4695de0f5b8c56d406
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a><span data-ttu-id="c2b51-102">Включение и отключение push-уведомлений для телефонов с Windows в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2b51-102">Enabling or disabling push notifications for Windows Phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2b51-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c2b51-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c2b51-104">Push-уведомления, в форме индикаторов, значков или оповещений, могут отправляться на устройство Windows Phone, даже если оно неактивно.</span><span class="sxs-lookup"><span data-stu-id="c2b51-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a Windows Phone even when the mobile application is inactive.</span></span> <span data-ttu-id="c2b51-105">Push-уведомления извещать пользователей о таких событиях, как новое или пропущенное приглашение на обмен мгновенными сообщениями и голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="c2b51-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="c2b51-106">Вы можете включать и отключать push-уведомления для устройств с Windows Phone с помощью панели управления Lync Server 2013 или оболочки управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2b51-106">You can enable or disable push notifications for Windows Phone devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="c2b51-107">Включение push-уведомлений для Windows Phone с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="c2b51-107">To enable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c2b51-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c2b51-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c2b51-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2b51-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c2b51-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c2b51-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c2b51-111">На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Навигация по **конфигурации push-уведомлений** .</span><span class="sxs-lookup"><span data-stu-id="c2b51-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="c2b51-112">На странице **Конфигурация push-уведомлений** выберите сайт, который вы хотите изменить, а затем в меню **Правка** выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="c2b51-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c2b51-113">Установите флажок **включить push-уведомления Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="c2b51-113">Click the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="c2b51-114">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="c2b51-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="c2b51-115">Отключение push-уведомлений для Windows Phone с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="c2b51-115">To disable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c2b51-116">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c2b51-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c2b51-117">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2b51-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c2b51-118">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c2b51-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c2b51-119">На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Навигация по **конфигурации push-уведомлений** .</span><span class="sxs-lookup"><span data-stu-id="c2b51-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="c2b51-120">На странице **Конфигурация push-уведомлений** выберите сайт, который вы хотите изменить, а затем в меню **Правка** выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="c2b51-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c2b51-121">Снимите флажок **включить push-уведомления Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="c2b51-121">Clear the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="c2b51-122">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="c2b51-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c2b51-123">Включение и отключение push-уведомлений для Windows Phone с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2b51-123">Enabling or Disabling Push Notifications for Windows Phone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c2b51-124">Вы можете включать и отключать push-уведомления для Windows Phone с помощью командлета **Set – кспушнотификатионконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="c2b51-124">You can enable or disable push notifications for Windows Phone by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="c2b51-125">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2b51-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c2b51-126">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2b51-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a><span data-ttu-id="c2b51-127">Включение push-уведомлений для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="c2b51-127">To enable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="c2b51-128">Чтобы включить push-уведомления для Windows Phone, установите для свойства Енаблемикрософтпушнотификатионсервице значение true ($True).</span><span class="sxs-lookup"><span data-stu-id="c2b51-128">To enable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to True ($True).</span></span> <span data-ttu-id="c2b51-129">Например:</span><span class="sxs-lookup"><span data-stu-id="c2b51-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a><span data-ttu-id="c2b51-130">Отключение push-уведомлений для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="c2b51-130">To disable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="c2b51-131">Чтобы отключить push-уведомления для Windows Phone, установите для свойства Енаблемикрософтпушнотификатионсервице значение false ($False).</span><span class="sxs-lookup"><span data-stu-id="c2b51-131">To disable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to False ($False).</span></span> <span data-ttu-id="c2b51-132">Например:</span><span class="sxs-lookup"><span data-stu-id="c2b51-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

<span data-ttu-id="c2b51-133">Дополнительные сведения можно найти в разделе справки по командлету [Set-кспушнотификатионконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="c2b51-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2b51-134">См. также</span><span class="sxs-lookup"><span data-stu-id="c2b51-134">See Also</span></span>


[<span data-ttu-id="c2b51-135">Настройка для использования push-уведомлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2b51-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

