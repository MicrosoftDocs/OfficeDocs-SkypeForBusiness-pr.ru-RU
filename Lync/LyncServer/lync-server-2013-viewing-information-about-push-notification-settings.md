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
ms.openlocfilehash: c74bbc90b0b7ef27da6b38b626fc91bc04383685
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>Просмотр сведений о параметрах push-уведомлений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Push-уведомления в форме индикаторов событий, значков или предупреждений могут отправляться на мобильное устройство, даже когда мобильное приложение неактивно. Push-уведомления уведомляют пользователя о таких событиях, как новое или пропущенное приглашение к обмену мгновенными сообщениями и голосовая почта. Вы можете просматривать параметры push-уведомлений для мобильных устройств с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>Просмотр сведений о push-уведомлениях из панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Клиенты**, а затем щелкните кнопку навигации **Настройка push-уведомлений**.

4.  На странице **Настройка push-уведомлений** выберите сайт, который нужно просмотреть, щелкните меню **Правка** и выберите команду **Показать сведения**.

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений об push-уведомлениях с помощью командлетов Windows PowerShell

Параметры конфигурации push-уведомлений можно просмотреть с помощью Windows PowerShell и командлета **Get-CsPushNotificationConfiguration** . Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-view-push-notification-configuration-information"></a>Просмотр сведений о конфигурации push-уведомлений

  - Чтобы просмотреть сведения о всех параметрах конфигурации push-уведомлений, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:
    
        Get-CsPushNotificationConfiguration
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

Дополнительные сведения см. в разделе справки для командлета [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration).

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

