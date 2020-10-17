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
ms.openlocfilehash: e4bcf8ccda422468416ae4c0b486e2e224b17f9f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515476"
---
# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a>Включение и отключение push-уведомлений для телефонов с Windows в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Push-уведомления в форме эмблем, значков или оповещений можно отправлять на телефон Windows, даже если мобильное приложение неактивно. Push-уведомления сообщают пользователю о событиях, таких как новые или пропущенные приглашения в сеанс обмена мгновенными сообщениями, а также новые сообщения голосовой почты. Вы можете включать и отключать push-уведомления для устройств с Windows Phone с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Включение push-уведомлений для Windows Phone с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Клиенты**, а затем щелкните кнопку навигации **Настройка push-уведомлений**.

4.  На странице **Настройка push-уведомлений** выберите сайт, который нужно изменить, щелкните меню **Правка** и выберите команду **Показать сведения**.

5.  Установите флажок **Разрешить push-уведомления от Майкрософт**.

6.  Нажмите кнопку **Зафиксировать**.

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Отключение push-уведомлений для Windows Phone с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Клиенты**, а затем щелкните кнопку навигации **Настройка push-уведомлений**.

4.  На странице **Настройка push-уведомлений** выберите сайт, который нужно изменить, щелкните меню **Правка** и выберите команду **Показать сведения**.

5.  Снимите флажок **Разрешить push-уведомления от Майкрософт**.

6.  Нажмите кнопку **Зафиксировать**.

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a>Включение и отключение push-уведомлений для Windows Phone с помощью командлетов Windows PowerShell

Вы можете включать и отключать push-уведомления для Windows Phone с помощью командлета **Set-CsPushNotificationConfiguration** . Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a>Включение push-уведомлений для Windows Phone

  - Чтобы включить push-уведомления для Windows Phone, установите для свойства Енаблемикрософтпушнотификатионсервице значение true ($True). Например:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a>Отключение push-уведомлений для Windows Phone

  - Чтобы отключить push-уведомления для Windows Phone, установите для свойства Енаблемикрософтпушнотификатионсервице значение false ($False). Например:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

Дополнительные сведения см. в разделе справки о командлете [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка для push-уведомлений в Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

