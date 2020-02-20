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
ms.openlocfilehash: 50b2cc9facfc93868abeb85ca02e8cb17a6803a9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Настройка для push-уведомлений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-12_

Push-уведомления в форме индикаторов событий, значков или предупреждений могут отправляться на мобильное устройство, даже когда мобильное приложение неактивно. Push-уведомления уведомляют пользователя о таких событиях, как новое или пропущенное приглашение к обмену мгновенными сообщениями и голосовая почта. Служба Mobility Lync Server 2013 отправляет уведомления в службу push-уведомлений Lync Server на основе облака, которая затем отправляет уведомления в службу push-уведомлений Apple (APNS) (для устройства Apple, работающего с мобильным клиентом Lync 2010) или Служба push-уведомлений Майкрософт (MPNS) (для устройства с Windows Phone, на котором работает Lync 2010 Mobile или мобильный клиент Lync 2013).

<div>


> [!IMPORTANT]  
> Если вы используете Windows Phone со Lync 2010 Mobile или Lync 2013 для мобильных устройств, то следует принять во внимание push-уведомления.<BR>Если вы используете Lync 2010 Mobile на устройствах Apple, следует принять во внимание push-уведомления.<BR>Если вы используете Lync 2013 Mobile на устройствах Apple, вам больше не нужно push-уведомления.



</div>

Настройте топологию для поддержки push-уведомлений, выполнив следующие действия.

  - Если в вашей среде используется пограничный сервер Lync Server 2010 или Lync Server 2013, необходимо добавить нового поставщика услуг хостинга, Microsoft Lync Online, а затем настроить федерацию поставщика услуг хранения между вашей организацией и Lync Online.

  - Если в вашей среде есть пограничный сервер Office Communications Server 2007 R2, необходимо настроить прямую федерацию SIP с push.lync.com.
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com — это домен Microsoft Office 365 для службы push-уведомлений.

    
    </div>

  - Чтобы включить push-уведомления, необходимо выполнить командлет **Set-CsPushNotificationConfiguration**. По умолчанию push-уведомления отключены.

  - Протестируйте конфигурацию федерации и push-уведомлений.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>Настройка отправки push-уведомлений с помощью пограничного сервера Lync Server 2013 или Lync Server 2010

1.  Выполните вход на компьютер, где установлена командная консоль Lync Server и OCSCore, в качестве члена группы RtcUniversalServerAdmins.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Добавьте поставщик услуг хостинга Lync Server Online. В командной строке введите следующую команду.
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Например:
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > Нельзя настраивать несколько отношений федерации с одним поставщиком услуг размещения. То есть, настроив поставщика услуг размещения, имеющего отношения федерации с sipfed.online.lync.com, не добавляйте для этого сайта другого поставщика услуг размещения, даже если удостоверение поставщика отличается от LyncOnline.

    
    </div>

4.  Настройте федерацию с поставщиком услуг размещения между организацией и службой push-уведомлений в Lync Online. В командной строке введите команду:
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>Настройка для push-уведомлений с пограничным сервером Office Communications Server 2007 R2

1.  Войдите на пограничный сервер в качестве члена группы RtcUniversalServerAdmins.

2.  В меню **Пуск** выберите пункт **Все программы**, затем **Средства администрирования** и **Управление компьютером**.

3.  В дереве консоли разверните узел **Службы и приложения**, щелкните правой кнопкой мыши **Microsoft Office Communications Server 2007 R2** и выберите пункт **Свойства**.

4.  На вкладке **Разрешить** нажмите кнопку **Добавить**.

5.  В диалоговом окне **Add Federated Partner** (Добавление федеративного партнера) выполните следующие действия.
    
      - В поле **Federated partner domain name** (Доменное имя федеративного партнера) введите **push.lync.com**.
    
      - В поле **Federated partner Access Edge Server** (Пограничный сервер доступа федеративного партнера) введите **sipfed.online.lync.com**.
    
      - Нажмите кнопку **ОК**.

</div>

<div>

## <a name="to-enable-push-notifications"></a>Включение push-уведомлений

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server и OCSCore, в качестве участника роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Включите push-уведомления. В командной строке введите следующую команду:
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Включите федерацию. В командной строке введите команду:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>Тестирование федерации и push-уведомлений

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server и OCSCore, в качестве участника роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Проверьте конфигурацию федерации. В командной строке введите:
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Пример:
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Протестируйте push-уведомления. В командной строке введите:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Пример:
    
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

