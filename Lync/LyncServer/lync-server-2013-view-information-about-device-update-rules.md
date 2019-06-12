---
title: 'Lync Server 2013: Просмотр сведений о правилах обновления устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d873cbd80e599313b60a57cfc28eb9752d85ef66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Просмотр сведений о правилах обновления устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Просмотр сведений о правилах обновления устройств, которые уже были импортированы, в том числе тип, модель и фирменные символики устройств, к которым применяется обновление. версия и тип обновления; и Национальная настройка и пул для обновления. Информация доступна для всех импортированных правил обновления устройства — тех, которые ожидают утверждения, развернуты (утверждены), отозваны (восстановлены) и которые вы решили не использовать (сбросить). Получить доступ к этим сведениям можно на панели управления Lync Server или Windows PowerShell.

<div>


> [!NOTE]  
> Подробнее об импорте, утверждении, сбросе, восстановлении и удалении правил можно найти в разделах, перечисленных в разделе <A href="lync-server-2013-device-update-rules.md">правила обновления устройств в Lync Server 2013</A>.



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>Просмотр правил обновления устройства с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Навигация по **обновлению устройства** . Импортированные правила перечислены на странице **обновления устройства** .

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Просмотр правил обновления устройства с помощью командлетов Windows PowerShell

Подробные сведения о всех правилах обновления устройств также можно просмотреть с помощью Windows PowerShell и командлета **Get-ксдевицеупдатеруле** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>Просмотр всех правил обновления устройства

  - Следующая команда возвращает сведения о всех правилах обновления устройства, настроенных для использования в вашей организации:
    
        Get-CsDeviceUpdateRule
    
    Команда возвращает данные, аналогичные приведенным ниже, для каждого правила обновления устройства.
    
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

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>Просмотр всех правил обновления устройства на определенном веб-сервере

  - Чтобы просмотреть правила обновления устройства на определенном компьютере, используйте параметр фильтра, а затем идентификатор сервера и подстановочный знак (\*). Например:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Get-ксдевицеупдатеруле](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

