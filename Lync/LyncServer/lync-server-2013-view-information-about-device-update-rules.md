---
title: 'Lync Server 2013: Просмотр сведений о правилах обновления устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fef5d58116da6b8cbc07ce2b16f3dd4f6b28ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506386"
---
# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Просмотр сведений о правилах обновления устройств в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Просмотр сведений о правилах обновления устройств, которые уже были импортированы, включая тип, модель и фирменную символику устройств, к которым применяется обновление; версия и тип обновления; и языковой стандарт и пул для обновления. Сведения доступны для всех импортированных правил обновления устройств, которые ожидают утверждения, развернуты (утверждены), отозваны (восстановлены) и которые вы решили не использовать (сбросить). Доступ к этой информации осуществляется либо с помощью панели управления Lync Server, либо с помощью Windows PowerShell.

<div>


> [!NOTE]  
> Дополнительные сведения об импорте, утверждении, сбросе, восстановлении и удалении правил приведены в разделах, перечисленных в <A href="lync-server-2013-device-update-rules.md">статье обновление устройств в Lync Server 2013</A>.



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>Просмотр правил обновления устройств с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **обновления устройства** . Импортированные правила перечислены на странице **обновление устройства** .

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Просмотр правил обновления устройств с помощью командлетов Windows PowerShell

Подробные сведения обо всех правилах обновления устройств также можно просмотреть с помощью Windows PowerShell и командлета **Get – CsDeviceUpdateRule** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>Просмотр всех правил обновления устройств

  - Следующая команда возвращает сведения обо всех правилах обновления устройств, настроенных для использования в Организации.
    
        Get-CsDeviceUpdateRule
    
    Команда возвращает сведения, аналогичные приведенным ниже, для каждого правила обновления устройств.
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>Просмотр всех правил обновления устройств на определенном веб-сервере

  - Чтобы просмотреть правила обновления устройств на определенном компьютере, используйте параметр Filter, а затем идентификатор сервера и подстановочный знак ( \* ). Например:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

Дополнительные сведения см. в разделе справки по командлету [Get – CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

