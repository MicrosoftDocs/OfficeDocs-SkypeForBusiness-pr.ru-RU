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
ms.openlocfilehash: 22d79d16980c29907aa4e254d4be7eaee2fcfaae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>Просмотр сведений о параметрах push-уведомлений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Push-уведомления, в форме индикаторов, значков или оповещений, могут отправляться на мобильное устройство, даже если мобильное приложение неактивно. Push-уведомления извещать пользователей о таких событиях, как новое или пропущенное приглашение на обмен мгновенными сообщениями и голосовая почта. Вы можете просматривать параметры push-уведомлений для мобильных устройств с помощью панели управления Lync Server 2013 или оболочки управления Lync Server 2013.

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>Просмотр сведений о push-уведомлениях из панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Навигация по **конфигурации push-уведомлений** .

4.  На странице **Конфигурация push-уведомлений** выберите сайт, который вы хотите просмотреть, а затем в меню **Правка** выберите пункт **Показать подробности**.

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений push-уведомлений с помощью командлетов Windows PowerShell

Параметры конфигурации push-уведомлений можно просмотреть с помощью Windows PowerShell и командлета **Get – кспушнотификатионконфигуратион** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-view-push-notification-configuration-information"></a>Просмотр сведений о конфигурации push-уведомлений

  - Чтобы просмотреть сведения о всех параметрах конфигурации push-уведомлений, введите в командной консоли Lync Server указанную ниже команду и нажмите клавишу ВВОД.
    
        Get-CsPushNotificationConfiguration
    
    Команда возвращает примерно следующую информацию:
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Get-кспушнотификатионконфигуратион](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) .

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка для использования push-уведомлений в Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

