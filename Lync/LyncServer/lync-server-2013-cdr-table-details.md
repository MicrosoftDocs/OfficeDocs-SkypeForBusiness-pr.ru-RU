---
title: 'Lync Server 2013: сведения о таблице регистрации вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f87e681cc25f9ed64509ff3bdb31abc5fd77101d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a>Сведения о таблице регистрации вызовов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-18_

В следующих разделах описаны столбцы в каждой из таблиц схемы базы данных "сведения о звонке" (CDR).

<div>

## <a name="in-this-section"></a>Содержание

  - [Таблица Application в Lync Server 2013](lync-server-2013-application-table.md)

  - [Таблица SessionCorrelation в Lync Server 2013](lync-server-2013-callpriorities-table.md)

  - [Таблица CallType в Lync Server 2013](lync-server-2013-calltype-table.md)

  - [Таблица ClientVersions в Lync Server 2013](lync-server-2013-clientversions-table.md)

  - [Таблица Конференцежоинтимесрешолдс в Lync Server 2013](lync-server-2013-conferencejointimethresholds-table.md)

  - [Таблица ConferenceMessageCount в Lync Server 2013](lync-server-2013-conferencemessagecount-table.md)

  - [Таблица Conferences в Lync Server 2013](lync-server-2013-conferences-table.md)

  - [Таблица ConferenceSessionDetails в Lync Server 2013](lync-server-2013-conferencesessiondetails-table.md)

  - [Таблица ConferenceUris в Lync Server 2013](lync-server-2013-conferenceuris-table.md)

  - [Таблица ContentTypes в Lync Server 2013](lync-server-2013-contenttypes-table.md)

  - [Таблица DeRegisterType в Lync Server 2013](lync-server-2013-deregistertype-table.md)

  - [Таблица Devices в Lync Server 2013](lync-server-2013-devices-table.md)

  - [Таблица Dialogs в Lync Server 2013](lync-server-2013-dialogs-table.md)

  - [Таблица EdgeServers в Lync Server 2013](lync-server-2013-edgeservers-table.md)

  - [Таблица Ерроркатегори в Lync Server 2013](lync-server-2013-errorcategory-table.md)

  - [Таблица ErrorDef в Lync Server 2013](lync-server-2013-errordef-table.md)

  - [Таблица ErrorReport в Lync Server 2013](lync-server-2013-errorreport-table.md)

  - [Таблица FileTransfers в Lync Server 2013](lync-server-2013-filetransfers-table.md)

  - [Таблица FocusJoinsAndLeaves в Lync Server 2013](lync-server-2013-focusjoinsandleaves-table.md)

  - [Интерфейсная таблица в Lync Server 2013](lync-server-2013-frontend-table.md)

  - [Таблица Gateways в Lync Server 2013](lync-server-2013-gateways-table.md)

  - [Таблица HardwareVersions в Lync Server 2013](lync-server-2013-hardwareversions-table.md)

  - [Таблица Имрепортсуммари в Lync Server 2013](lync-server-2013-imreportsummary-table.md)

  - [Таблица Locations в Lync Server 2013](lync-server-2013-locations-table.md)

  - [Таблица Manufacturers в Lync Server 2013](lync-server-2013-manufacturers-table.md)

  - [Таблица McuJoinsAndLeaves в Lync Server 2013](lync-server-2013-mcujoinsandleaves-table.md)

  - [Таблица Mcus в Lync Server 2013](lync-server-2013-mcus-table.md)

  - [Таблица Media в Lync Server 2013](lync-server-2013-media-table.md)

  - [Таблица MediaList в Lync Server 2013](lync-server-2013-medialist-table.md)

  - [Таблица MediationServers в Lync Server 2013](lync-server-2013-mediationservers-table.md)

  - [Таблица Мсмкпроцессинг в Lync Server 2013](lync-server-2013-msmqprocessing-table.md)

  - [Таблица Phones в Lync Server 2013](lync-server-2013-phones-table.md)

  - [Таблица Pools в Lync Server 2013](lync-server-2013-pools-table.md)

  - [Таблица ProgressReport в Lync Server 2013](lync-server-2013-progressreport-table.md)

  - [Таблица Пуржесеттингс в Lync Server 2013](lync-server-2013-purgesettings-table.md)

  - [Таблица Registration в Lync Server 2013](lync-server-2013-registration-table.md)

  - [Таблица Roles в Lync Server 2013](lync-server-2013-roles-table.md)

  - [Таблица Servers в Lync Server 2013](lync-server-2013-servers-table.md)

  - [Таблица SessionDetails в Lync Server 2013](lync-server-2013-sessiondetails-table.md)

  - [Таблица Сипреспонсеметадата в Lync Server 2013](lync-server-2013-sipresponsemetadata-table.md)

  - [Таблица "синдикации" в Lync Server 2013](lync-server-2013-syndicators-table.md)

  - [Таблица Синдикаторстенантмап в Lync Server 2013](lync-server-2013-syndicatorstenantmap-table.md)

  - [Таблица задач в Lync Server 2013](lync-server-2013-task-table.md)

  - [Таблица Tenants в Lync Server 2013](lync-server-2013-tenants-table.md)

  - [Таблица UriTypes в Lync Server 2013](lync-server-2013-uritypes-table.md)

  - [Таблица Users в Lync Server 2013](lync-server-2013-users-table.md)

  - [Таблица Усеражентдеф в Lync Server 2013](lync-server-2013-useragentdef-table.md)

  - [Таблица Усерстатистикс в Lync Server 2013](lync-server-2013-userstatistics-table.md)

  - [Таблица VoipDetails в Lync Server 2013](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

