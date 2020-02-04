---
title: 'Lync Server 2013: настройка для использования push-уведомлений'
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
ms.openlocfilehash: c34b49d6c968effa46005a01df286d14fcff394c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="d87b2-102">Настройка для использования push-уведомлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d87b2-102">Configuring for push notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d87b2-103">_**Тема последнего изменения:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="d87b2-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="d87b2-104">Push-уведомления, в форме индикаторов, значков или оповещений, могут отправляться на мобильное устройство, даже если мобильное приложение неактивно.</span><span class="sxs-lookup"><span data-stu-id="d87b2-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="d87b2-105">Push-уведомления извещать пользователей о таких событиях, как новое или пропущенное приглашение на обмен мгновенными сообщениями и голосовая почта.</span><span class="sxs-lookup"><span data-stu-id="d87b2-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="d87b2-106">Служба Lync Server 2013 Mobility Service отправляет уведомления на облачную службу push-уведомлений Lync Server, которая затем отправляет уведомления в службу извещающих уведомлений Apple (APNS) (для устройства Apple, работающего на мобильном клиенте Lync 2010) или Служба push-уведомлений Майкрософт (MPNS) (для устройства с Windows Phone, работающего на мобильном телефоне Lync 2010 или мобильном клиенте Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="d87b2-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d87b2-107">Если вы используете Windows Phone с мобильным клиентом Lync 2010 Mobile или Lync 2013 для мобильных устройств, следует учитывать push-уведомление.</span><span class="sxs-lookup"><span data-stu-id="d87b2-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="d87b2-108">Если вы используете Lync 2010 Mobile на устройствах Apple, следует учитывать push-уведомление.</span><span class="sxs-lookup"><span data-stu-id="d87b2-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="d87b2-109">Если вы используете Lync 2013 Mobile на устройствах Apple, вам больше не нужно push-уведомление.</span><span class="sxs-lookup"><span data-stu-id="d87b2-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="d87b2-110">Настройте топологию для поддержки push-уведомлений, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d87b2-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="d87b2-111">Если в вашей среде есть сервер Lync Server 2010 или Lync Server 2013 EDGE, вам нужно добавить нового поставщика услуг размещения, Microsoft Lync Online, а затем настроить федерацию поставщика услуг размещения между вашей организацией и Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d87b2-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="d87b2-112">Если в вашей среде есть сервер Office Communications Server 2007 R2, вам нужно настроить прямую федерацию SIP с помощью push.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d87b2-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d87b2-113">Push.lync.com — домен Microsoft Office 365 для службы push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="d87b2-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="d87b2-114">Чтобы включить push-уведомления, необходимо выполнить командлет **Set – кспушнотификатионконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="d87b2-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="d87b2-115">По умолчанию push-уведомления отключены.</span><span class="sxs-lookup"><span data-stu-id="d87b2-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="d87b2-116">Проверка конфигурации Федерации и push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="d87b2-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="d87b2-117">Настройка push-уведомлений с помощью Lync Server 2013 или Lync Server 2010 Edge Server</span><span class="sxs-lookup"><span data-stu-id="d87b2-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="d87b2-118">Войдите в систему на компьютере, на котором оболочка Lync Server Management Shell и Окскоре устанавливается как участник группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="d87b2-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d87b2-119">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d87b2-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d87b2-120">Добавьте поставщика услуг размещения Lync Server Online.</span><span class="sxs-lookup"><span data-stu-id="d87b2-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="d87b2-121">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d87b2-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="d87b2-122">Например:</span><span class="sxs-lookup"><span data-stu-id="d87b2-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d87b2-123">У вас не может быть более одной связи Федерации с одним поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="d87b2-123">You cannot have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="d87b2-124">Таким образом, если вы уже настроили поставщика услуг размещения с отношением Федерации с sipfed.online.lync.com, не добавляйте для него другого поставщика услуг размещения, даже если удостоверение поставщика услуг размещения не является Линконлине.</span><span class="sxs-lookup"><span data-stu-id="d87b2-124">That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="d87b2-125">Настройте федерацию поставщика услуг хостинга между вашей организацией и службой push-уведомлений в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d87b2-125">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online.</span></span> <span data-ttu-id="d87b2-126">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d87b2-126">At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="d87b2-127">Настройка push-уведомлений с помощью пограничного сервера Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d87b2-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="d87b2-128">Войдите на пограничный сервер в качестве участника группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="d87b2-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d87b2-129">Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Администрирование**, а затем — **Управление компьютером**.</span><span class="sxs-lookup"><span data-stu-id="d87b2-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="d87b2-130">В дереве консоли разверните узел **службы и приложения**, щелкните правой кнопкой мыши **Microsoft Office Communications Server 2007 R2**и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d87b2-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="d87b2-131">На вкладке **Разрешить** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d87b2-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="d87b2-132">В диалоговом окне **Добавление федеративного партнера** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d87b2-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="d87b2-133">В **доменном имени федеративного партнера**введите **Push.Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="d87b2-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="d87b2-134">В **пограничный сервер для федеративного партнера Access**введите **sipfed.Online.Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="d87b2-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="d87b2-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d87b2-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="d87b2-136">Включение push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="d87b2-136">To enable push notifications</span></span>

1.  <span data-ttu-id="d87b2-137">Войдите в систему на компьютере, на котором оболочка Lync Server Management Shell и Окскоре установлен в качестве участника роли Ксадминистратор.</span><span class="sxs-lookup"><span data-stu-id="d87b2-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="d87b2-138">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d87b2-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d87b2-139">Включение push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="d87b2-139">Enable push notifications.</span></span> <span data-ttu-id="d87b2-140">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d87b2-140">At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="d87b2-141">Включите Федерацию.</span><span class="sxs-lookup"><span data-stu-id="d87b2-141">Enable federation.</span></span> <span data-ttu-id="d87b2-142">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d87b2-142">At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="d87b2-143">Тестирование Федерации и push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="d87b2-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="d87b2-144">Войдите в систему на компьютере, на котором оболочка Lync Server Management Shell и Окскоре установлен в качестве участника роли Ксадминистратор.</span><span class="sxs-lookup"><span data-stu-id="d87b2-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="d87b2-145">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d87b2-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d87b2-146">Проверьте конфигурацию Федерации.</span><span class="sxs-lookup"><span data-stu-id="d87b2-146">Test the federation configuration.</span></span> <span data-ttu-id="d87b2-147">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d87b2-147">At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="d87b2-148">Например:</span><span class="sxs-lookup"><span data-stu-id="d87b2-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="d87b2-149">Тест push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="d87b2-149">Test push notifications.</span></span> <span data-ttu-id="d87b2-150">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d87b2-150">At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="d87b2-151">Например:</span><span class="sxs-lookup"><span data-stu-id="d87b2-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d87b2-152">См. также</span><span class="sxs-lookup"><span data-stu-id="d87b2-152">See Also</span></span>


[<span data-ttu-id="d87b2-153">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="d87b2-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="d87b2-154">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="d87b2-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

