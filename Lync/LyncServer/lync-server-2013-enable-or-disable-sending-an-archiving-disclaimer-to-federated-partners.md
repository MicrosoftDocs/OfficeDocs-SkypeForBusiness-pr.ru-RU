---
title: Включение или отключение отправки заявления об отказе от архивации федеративным партнерам
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac499b9cdadbda44cf6afd87382a1259cb4e467
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a>Включение или отключение отправки заявления об отказе от архивации федеративным партнерам в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

При развертывании пограничных серверов и включении Федерации для Организации необходимо указать, следует ли автоматически отправлять заявление об отказе от архивации федеративным партнерам. При архивации внешних коммуникаций необходимо включить отправку заявления об отказе от архивации. Используйте процедуру, описанную в данном разделе, для изменения этой конфигурации.

<div>


> [!NOTE]
> В следующей процедуре предполагается, что федерация уже включена для организации. Подробнее о включении Федерации можно узнать в статье <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по операциям.



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Включение или отключение отправки заявления об отказе от архивации федеративным партнерам

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.

4.  На вкладке **Настройка пограничного доступа** нажмите кнопку **Глобальная**, выберите команду **изменить**, а затем щелкните **Показать подробности**.

5.  В разделе **изменение конфигурации пограничного сервера доступа**в разделе **Разрешить взаимодействие с федеративными пользователями**установите или снимите флажок **отправлять заявление об отказе от прав для федеративных партнеров** , чтобы включить или отключить автоматическую отправку заявления об отказе от архивации.

6.  Щелкните **Исполнить**.

Чтобы разрешить федеративным пользователям совместно работать с пользователями в развертывании Lync Server 2013, вам также необходимо настроить по крайней мере одну политику внешнего доступа для поддержки федеративного доступа пользователей. Дополнительные сведения: [Manage XMPP Федеративные партнеры в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) в документации по развертыванию или документации по операциям. Подробные сведения об управлении доступом для определенных федеративных доменов приведены в статье [Настройка поддержки для разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) в документации по развертыванию или документации по операциям.

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Включение или отключение заявления об отказе от архивации с помощью командлетов Windows PowerShell

Для управления использованием заявления об отказе в архивации можно использовать Windows PowerShell и командлет Set – CsAccessEdgeConfiguration. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-enable-the-archiving-disclaimer"></a>Включение заявления об отказе от архивации

  - Чтобы включить заявление об отказе в архивации, присвойте свойству **EnableArchivingDisclaimer** значение True ($true):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a>Отключение заявления об отказе от архивации

  - Чтобы отключить заявление об отказе в архивации, присвойте свойству **EnableArchivingDisclaimer** значение False ($false):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

