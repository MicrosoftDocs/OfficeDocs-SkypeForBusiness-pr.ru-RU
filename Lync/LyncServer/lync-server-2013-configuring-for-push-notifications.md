---
title: 'Lync Server 2013: Настройка для push-уведомлений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad1967bea18e0a03ac3a34bf187c1248ec5a1ab2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="e6b28-102">Настройка для push-уведомлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6b28-102">Configuring for push notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6b28-103">_**Последнее изменение темы:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="e6b28-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="e6b28-104">Push-уведомления в форме индикаторов событий, значков или предупреждений могут отправляться на мобильное устройство, даже когда мобильное приложение неактивно.</span><span class="sxs-lookup"><span data-stu-id="e6b28-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="e6b28-105">Push-уведомления уведомляют пользователя о таких событиях, как новое или пропущенное приглашение к обмену мгновенными сообщениями и голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="e6b28-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="e6b28-106">Служба Mobility Lync Server 2013 отправляет уведомления в службу push-уведомлений Lync Server на основе облака, которая затем отправляет уведомления в службу push-уведомлений Apple (APNS) (для устройства Apple, работающего с мобильным клиентом Lync 2010) или Служба push-уведомлений Майкрософт (MPNS) (для устройства с Windows Phone, на котором работает Lync 2010 Mobile или мобильный клиент Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="e6b28-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e6b28-107">Если вы используете Windows Phone со Lync 2010 Mobile или Lync 2013 для мобильных устройств, то следует принять во внимание push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="e6b28-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="e6b28-108">Если вы используете Lync 2010 Mobile на устройствах Apple, следует принять во внимание push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="e6b28-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="e6b28-109">Если вы используете Lync 2013 Mobile на устройствах Apple, вам больше не нужно push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="e6b28-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="e6b28-110">Настройте топологию для поддержки push-уведомлений, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e6b28-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="e6b28-111">Если в вашей среде используется пограничный сервер Lync Server 2010 или Lync Server 2013, необходимо добавить нового поставщика услуг хостинга, Microsoft Lync Online, а затем настроить федерацию поставщика услуг хранения между вашей организацией и Lync Online.</span><span class="sxs-lookup"><span data-stu-id="e6b28-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="e6b28-112">Если в вашей среде есть пограничный сервер Office Communications Server 2007 R2, необходимо настроить прямую федерацию SIP с push.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e6b28-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e6b28-113">Push.lync.com — это домен Microsoft Office 365 для службы push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="e6b28-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="e6b28-114">Чтобы включить push-уведомления, необходимо выполнить командлет **Set-CsPushNotificationConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e6b28-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="e6b28-115">По умолчанию push-уведомления отключены.</span><span class="sxs-lookup"><span data-stu-id="e6b28-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="e6b28-116">Протестируйте конфигурацию федерации и push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="e6b28-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="e6b28-117">Настройка отправки push-уведомлений с помощью пограничного сервера Lync Server 2013 или Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e6b28-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="e6b28-118">Выполните вход на компьютер, где установлена командная консоль Lync Server и OCSCore, в качестве члена группы RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e6b28-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e6b28-119">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e6b28-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e6b28-120">Добавьте поставщик услуг хостинга Lync Server Online.</span><span class="sxs-lookup"><span data-stu-id="e6b28-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="e6b28-121">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e6b28-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="e6b28-122">Например:</span><span class="sxs-lookup"><span data-stu-id="e6b28-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e6b28-p104">Нельзя настраивать несколько отношений федерации с одним поставщиком услуг размещения. То есть, настроив поставщика услуг размещения, имеющего отношения федерации с sipfed.online.lync.com, не добавляйте для этого сайта другого поставщика услуг размещения, даже если удостоверение поставщика отличается от LyncOnline.</span><span class="sxs-lookup"><span data-stu-id="e6b28-p104">You cannot have more than one federation relationship with a single hosting provider. That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="e6b28-p105">Настройте федерацию с поставщиком услуг размещения между организацией и службой push-уведомлений в Lync Online. В командной строке введите команду:</span><span class="sxs-lookup"><span data-stu-id="e6b28-p105">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online. At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="e6b28-127">Настройка для push-уведомлений с пограничным сервером Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e6b28-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="e6b28-128">Войдите на пограничный сервер в качестве члена группы RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e6b28-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e6b28-129">В меню **Пуск** выберите пункт **Все программы**, затем **Средства администрирования** и **Управление компьютером**.</span><span class="sxs-lookup"><span data-stu-id="e6b28-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="e6b28-130">В дереве консоли разверните узел **Службы и приложения**, щелкните правой кнопкой мыши **Microsoft Office Communications Server 2007 R2** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e6b28-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="e6b28-131">На вкладке **Разрешить** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e6b28-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="e6b28-132">В диалоговом окне **Add Federated Partner** (Добавление федеративного партнера) выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e6b28-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="e6b28-133">В поле **Federated partner domain name** (Доменное имя федеративного партнера) введите **push.lync.com**.</span><span class="sxs-lookup"><span data-stu-id="e6b28-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="e6b28-134">В поле **Federated partner Access Edge Server** (Пограничный сервер доступа федеративного партнера) введите **sipfed.online.lync.com**.</span><span class="sxs-lookup"><span data-stu-id="e6b28-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="e6b28-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e6b28-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="e6b28-136">Включение push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="e6b28-136">To enable push notifications</span></span>

1.  <span data-ttu-id="e6b28-137">Выполните вход на компьютер, на котором установлена командная консоль Lync Server и OCSCore, в качестве участника роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e6b28-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="e6b28-138">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e6b28-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e6b28-p106">Включите push-уведомления. В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e6b28-p106">Enable push notifications. At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="e6b28-p107">Включите федерацию. В командной строке введите команду:</span><span class="sxs-lookup"><span data-stu-id="e6b28-p107">Enable federation. At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="e6b28-143">Тестирование федерации и push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="e6b28-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="e6b28-144">Выполните вход на компьютер, на котором установлена командная консоль Lync Server и OCSCore, в качестве участника роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e6b28-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="e6b28-145">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e6b28-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e6b28-p108">Проверьте конфигурацию федерации. В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="e6b28-p108">Test the federation configuration. At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="e6b28-148">Пример:</span><span class="sxs-lookup"><span data-stu-id="e6b28-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="e6b28-p109">Протестируйте push-уведомления. В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="e6b28-p109">Test push notifications. At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="e6b28-151">Пример:</span><span class="sxs-lookup"><span data-stu-id="e6b28-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e6b28-152">См. также</span><span class="sxs-lookup"><span data-stu-id="e6b28-152">See Also</span></span>


[<span data-ttu-id="e6b28-153">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="e6b28-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="e6b28-154">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="e6b28-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

