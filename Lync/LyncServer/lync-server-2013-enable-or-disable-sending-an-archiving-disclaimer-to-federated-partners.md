---
title: Включение и отключение отправки отказа от архивирования федеративным партнерам
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
ms.openlocfilehash: 1f53e03ebfdc24ff969ff44a9b39149456ab3f16
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a>Включение и отключение отправки отказа от архивирования федеративным партнерам в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

На момент развертывания пограничных серверов и включения Федерации для Организации необходимо указать, следует ли автоматически отправлять заявление об отказе от архивации федеративным партнерам. При архивации внешних данных необходимо включить отправку сообщений об отказе в архивацию. Чтобы изменить конфигурацию, воспользуйтесь процедурой, описанной в этом разделе.

<div>


> [!NOTE]
> В описанной ниже процедуре предполагается, что вы уже включили Федерацию для своей организации. Дополнительные сведения о включении Федерации можно найти <A href="lync-server-2013-enable-or-disable-remote-user-access.md">в разделе Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по эксплуатации.



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Включение и отключение отправки запроса на архивацию федеративных партнеров

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите **внешний пользовательский доступ**, а затем — **Конфигурация Edge Access**.

4.  На вкладке **Конфигурация пограничного доступа** последовательно выберите пункты **Глобальная**, **Изменить** и **Показать подробности**.

5.  В диалоговом окне **изменение конфигурации Edge для доступа**в разделе **включить связь с федеративными пользователями**установите или снимите флажок **отправлять заявление об отказе от работы федеративным партнерам** , чтобы включить или отключить автоматическую отправку сообщений об отказе в архивацию.

6.  Нажмите **Исполнить**.

Чтобы пользователи федеративных пользователей могли работать с пользователями в Lync Server 2013, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки федеративного доступа пользователей. Подробные сведения можно найти [в разделе Управление федеративными партнерами КСМПП в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) в документации по развертыванию или документации по эксплуатации. Подробнее об управлении доступом для определенных федеративных доменов можно узнать в разделе [Настройка поддержки разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) в документации по развертыванию или документации по операциям.

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Включение и отключение отказа от архивации с помощью командлетов Windows PowerShell

Для управления использованием отказа в архивации можно использовать Windows PowerShell и командлет Set-Ксакцесседжеконфигуратион. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-enable-the-archiving-disclaimer"></a>Включение отказа в архивации

  - Чтобы включить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение True ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a>Отключение отказа от архивации

  - Чтобы отключить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение False ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

