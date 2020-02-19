---
title: 'Lync Server 2013: Просмотр сведений о параметрах push-уведомлений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73345feedda10a5cd7979b7683b5a700de578085
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a><span data-ttu-id="bd713-102">Просмотр сведений о параметрах push-уведомлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd713-102">Viewing information about push notification settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd713-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bd713-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bd713-104">Push-уведомления в форме индикаторов событий, значков или предупреждений могут отправляться на мобильное устройство, даже когда мобильное приложение неактивно.</span><span class="sxs-lookup"><span data-stu-id="bd713-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="bd713-105">Push-уведомления уведомляют пользователя о таких событиях, как новое или пропущенное приглашение к обмену мгновенными сообщениями и голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="bd713-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="bd713-106">Вы можете просматривать параметры push-уведомлений для мобильных устройств с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd713-106">You can view information push notifications settings for mobile devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a><span data-ttu-id="bd713-107">Просмотр сведений о push-уведомлениях из панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="bd713-107">To view push notification information from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="bd713-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bd713-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bd713-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd713-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bd713-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bd713-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bd713-111">В левой панели навигации щелкните **Клиенты**, а затем щелкните кнопку навигации **Настройка push-уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="bd713-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="bd713-112">На странице **Настройка push-уведомлений** выберите сайт, который нужно просмотреть, щелкните меню **Правка** и выберите команду **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="bd713-112">On the **Push Notification Configuration** page, click the site you want to view, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bd713-113">Просмотр сведений об push-уведомлениях с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd713-113">Viewing Push Notification Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bd713-114">Параметры конфигурации push-уведомлений можно просмотреть с помощью Windows PowerShell и командлета **Get-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="bd713-114">You can view push notification configuration settings by using Windows PowerShell and the **Get-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="bd713-115">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd713-115">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bd713-116">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="bd713-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-push-notification-configuration-information"></a><span data-ttu-id="bd713-117">Просмотр сведений о конфигурации push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="bd713-117">To view push notification configuration information</span></span>

  - <span data-ttu-id="bd713-118">Чтобы просмотреть сведения о всех параметрах конфигурации push-уведомлений, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="bd713-118">To view information about all your push notification configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPushNotificationConfiguration
    
    <span data-ttu-id="bd713-119">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="bd713-119">That will return information similar to this:</span></span>
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

<span data-ttu-id="bd713-120">Дополнительные сведения см. в разделе справки для командлета [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="bd713-120">For more information, see the help topic for the [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd713-121">См. также</span><span class="sxs-lookup"><span data-stu-id="bd713-121">See Also</span></span>


[<span data-ttu-id="bd713-122">Настройка для push-уведомлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd713-122">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

