---
title: 'Lync Server 2013: Управление конфигурацией пограничного сервера для Организации'
description: 'Lync Server 2013: Управление конфигурацией пограничного сервера для Организации.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2161385f9c03f025bcf6f5e599b7e0276f6d592c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550645"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Управление конфигурацией пограничного сервера доступа для Организации в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Это Предварительная документация, которая может быть изменена. Пустые разделы включены в качестве заполнителей.

После развертывания одного или нескольких пограничных серверов необходимо включить типы доступа к внешним доменам или поставщикам, удаленный доступ пользователей и анонимный доступ пользователей к конференциям через пограничные серверы, которые будут поддерживаться в вашей организации.

Ниже перечислены типы доступа, которые можно настроить на странице **Настройка пограничного доступа**:

  - **Включение Федерации и общедоступной службы**     обмена мгновенными сообщениями Включите этот параметр, если требуется поддержка доступа пользователей к доменам федеративных партнеров. Это значение применяется и к федерациям SIP, и к федерациям XMPP, настроенным на глобальном уровне, уровне площадки или пользовательском уровне на странице**Политика внешнего доступа**. Для применения параметров федераций необходимо настроить поддержку федераций на обеих страницах.
    
    Следующие два необязательных параметра позволят определить способ обнаружения федеративных партнеров и то, будут ли отправляться контактам уведомления об архивации (уведомление федеративных контактов о том, что во время взаимодействия с вашей стороны включена архивация и ход взаимодействия будет архивироваться).
    
      - **Включение обнаружения**     доменных партнеров При выборе этого параметра включается автоматическое обнаружение доменов, с которыми вы можете создать федерацию. Lync Server 2013 использует записи службы доменных имен (DNS) для обнаружения доменов, не указанных в списке разрешенных доменов, автоматически оценивая входящий трафик от обнаруженных федеративных партнеров и ограничивая или блокирующая трафик на основе уровня доверия, объема трафика и параметров администратора. Если этот параметр не выбран, доступ будет разрешен только для федеративных пользователей из доменов, включенных в список разрешенных доменов. Независимо от выбора этого параметра можно указать отдельные домены, которые будут заблокированы или разрешены, включая ограничение доступа к конкретным серверам пограничной службы доступа в федеративном домене. Подробнее: [Настройка поддержки для разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Отправка заявления об отказе от архивации федеративным партнерам**     При выборе этого параметра включается Отправка сообщения об отказе от архивации федеративным партнерам, которые сообщают им о том, что сведения о связи записываются. При архивировании внешних взаимодействий с доменами федеративных партнеров следует включить уведомление об архивации, чтобы предупредить партнеров о том, что их сообщения и сведения о взаимодействии с ними будут архивироваться в вашей среде. Подробные сведения о архивации можно найти [в статье Определение требований к архивации в Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Включение удаленного доступа пользователей**     Включите этот параметр, если вы хотите, чтобы пользователи из вашей организации, находящиеся за преправителями, например для пользователей, которые находятся в дороге, могли подключиться к Lync Server. Дополнительные сведения см. [в статье Включение или отключение удаленного доступа пользователей в Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Разрешение доступа анонимных пользователей к конференциям**     Включите этот параметр, если вы хотите, чтобы внутренние пользователи пригласили внешних анонимных пользователей на Конференции, которые они упорядочивают. Включение этого параметра только разрешает анонимным пользователям участвовать в конференциях. Чтобы настроить интерфейс и параметры конференц-связи, которые определяют, как и как пользователи могут выполнять конференции, а также для включения анонимных пользователей, ознакомьтесь со статьей сведения о [создании или изменении интерфейса Конференц-](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) связи для сайтов, пользователей и [параметров политики конференц-связи для Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>


> [!NOTE]  
> Кроме поддержки разрешения доступа внешних пользователей, прежде чем внешним пользователям станет доступен любой тип доступа, также нужно настроить политики управления. Сведения о создании, настройке и применении политик для доступа внешних пользователей приведены <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">в статье Manage External Access Policy in Lync Server 2013</A>.



</div>

**Просмотр сведений о конфигурации пограничного доступа с помощью командлетов Windows PowerShell**

  - Сведения о конфигурации пограничного сервера доступа можно просмотреть с помощью Windows PowerShell и командлета **Get – CsAccessEdgeConfiguration** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    Чтобы просмотреть сведения обо всех параметрах конфигурации пограничного сервера доступа, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:
    
        Get-CsAccessEdgeConfiguration
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a>Содержание

  - [Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Включение и отключение обнаружения партнеров Федерации в Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Включение или отключение отправки заявления об отказе от архивации федеративным партнерам в Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Включение или отключение доступа удаленных пользователей в Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Включение или отключение анонимного доступа пользователей в Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Назначение политик конференц-связи для поддержки анонимных пользователей в Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

