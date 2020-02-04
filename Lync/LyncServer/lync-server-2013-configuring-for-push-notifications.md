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

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Настройка для использования push-уведомлений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-12_

Push-уведомления, в форме индикаторов, значков или оповещений, могут отправляться на мобильное устройство, даже если мобильное приложение неактивно. Push-уведомления извещать пользователей о таких событиях, как новое или пропущенное приглашение на обмен мгновенными сообщениями и голосовая почта. Служба Lync Server 2013 Mobility Service отправляет уведомления на облачную службу push-уведомлений Lync Server, которая затем отправляет уведомления в службу извещающих уведомлений Apple (APNS) (для устройства Apple, работающего на мобильном клиенте Lync 2010) или Служба push-уведомлений Майкрософт (MPNS) (для устройства с Windows Phone, работающего на мобильном телефоне Lync 2010 или мобильном клиенте Lync 2013).

<div>


> [!IMPORTANT]  
> Если вы используете Windows Phone с мобильным клиентом Lync 2010 Mobile или Lync 2013 для мобильных устройств, следует учитывать push-уведомление.<BR>Если вы используете Lync 2010 Mobile на устройствах Apple, следует учитывать push-уведомление.<BR>Если вы используете Lync 2013 Mobile на устройствах Apple, вам больше не нужно push-уведомление.



</div>

Настройте топологию для поддержки push-уведомлений, выполнив указанные ниже действия.

  - Если в вашей среде есть сервер Lync Server 2010 или Lync Server 2013 EDGE, вам нужно добавить нового поставщика услуг размещения, Microsoft Lync Online, а затем настроить федерацию поставщика услуг размещения между вашей организацией и Lync Online.

  - Если в вашей среде есть сервер Office Communications Server 2007 R2, вам нужно настроить прямую федерацию SIP с помощью push.lync.com.
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com — домен Microsoft Office 365 для службы push-уведомлений.

    
    </div>

  - Чтобы включить push-уведомления, необходимо выполнить командлет **Set – кспушнотификатионконфигуратион** . По умолчанию push-уведомления отключены.

  - Проверка конфигурации Федерации и push-уведомлений.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>Настройка push-уведомлений с помощью Lync Server 2013 или Lync Server 2010 Edge Server

1.  Войдите в систему на компьютере, на котором оболочка Lync Server Management Shell и Окскоре устанавливается как участник группы Рткуниверсалсерверадминс.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Добавьте поставщика услуг размещения Lync Server Online. В командной строке введите следующую команду:
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Например:
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > У вас не может быть более одной связи Федерации с одним поставщиком услуг размещения. Таким образом, если вы уже настроили поставщика услуг размещения с отношением Федерации с sipfed.online.lync.com, не добавляйте для него другого поставщика услуг размещения, даже если удостоверение поставщика услуг размещения не является Линконлине.

    
    </div>

4.  Настройте федерацию поставщика услуг хостинга между вашей организацией и службой push-уведомлений в Lync Online. В командной строке выполните следующую команду:
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>Настройка push-уведомлений с помощью пограничного сервера Office Communications Server 2007 R2

1.  Войдите на пограничный сервер в качестве участника группы Рткуниверсалсерверадминс.

2.  Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Администрирование**, а затем — **Управление компьютером**.

3.  В дереве консоли разверните узел **службы и приложения**, щелкните правой кнопкой мыши **Microsoft Office Communications Server 2007 R2**и выберите пункт **Свойства**.

4.  На вкладке **Разрешить** нажмите кнопку **Добавить**.

5.  В диалоговом окне **Добавление федеративного партнера** выполните указанные ниже действия.
    
      - В **доменном имени федеративного партнера**введите **Push.Lync.com**.
    
      - В **пограничный сервер для федеративного партнера Access**введите **sipfed.Online.Lync.com**.
    
      - Нажмите кнопку **ОК**.

</div>

<div>

## <a name="to-enable-push-notifications"></a>Включение push-уведомлений

1.  Войдите в систему на компьютере, на котором оболочка Lync Server Management Shell и Окскоре установлен в качестве участника роли Ксадминистратор.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Включение push-уведомлений. В командной строке выполните следующую команду:
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Включите Федерацию. В командной строке выполните следующую команду:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>Тестирование Федерации и push-уведомлений

1.  Войдите в систему на компьютере, на котором оболочка Lync Server Management Shell и Окскоре установлен в качестве участника роли Ксадминистратор.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Проверьте конфигурацию Федерации. В командной строке введите следующую команду:
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Например:
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Тест push-уведомлений. В командной строке введите следующую команду:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Например:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>См. также


[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

