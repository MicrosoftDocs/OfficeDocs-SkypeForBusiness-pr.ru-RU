---
title: 'Lync Server 2013: поддержка Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd35b9444f0ede4abc9b66ab6b5513d049df57ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a>Поддержка Active Directory в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-12-04_

Локальные топологии доменных служб Active Directory, поддерживаемые Lync Server 2013, описаны ниже.

  - Один лес с одним доменом

  - Один лес с одним деревом и несколькими доменами

  - Один лес с несколькими деревьями и несвязанными пространствами имен

  - Несколько лесов в топологии с центральным лесом

  - Несколько лесов в топологии с лесом ресурсов

<div>


> [!NOTE]  
> Lync Server 2013 не поддерживает домены с одной меткой. Например, лес с корневым доменом с именем <STRONG>contoso. local</STRONG> поддерживается, но не поддерживается корневой домен с именем <STRONG>Local</STRONG> в одной метке. Подробные сведения о том, как настроить Windows для доменов с DNS-именами, сопоставленными с одной меткой, можно найти в статье <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>300684 в Microsoft Knowledge Base.



</div>

<div>


> [!NOTE]  
> Lync Server 2013 не поддерживает переименование доменов. Если необходимо переименовать домен, на котором развернут сервер Lync Server, сначала необходимо удалить Lync Server, затем переименовать домен, а затем повторно установить Lync Server.



</div>

Для получения подробных сведений о поддерживаемых топологиях и требованиях для локальных развертываний просмотрите [требования к доменным службам Active Directory, поддержку и топологии в Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) в документации по планированию.

</div>

<span> </span>

</div>

</div>

</div>

