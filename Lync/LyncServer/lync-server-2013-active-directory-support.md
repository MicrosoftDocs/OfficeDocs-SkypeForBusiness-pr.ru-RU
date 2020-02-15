---
title: Lync Server 2013 support Active Directory
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
ms.openlocfilehash: b3ded5de5500778559efe632c5272db50b0eadbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a>Поддержка Active Directory в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-12-04_

Локальные топологии доменных служб Active Directory, поддерживаемые в Lync Server 2013, приведены ниже.

  - один лес с одним доменом;

  - один лес с одним деревом и несколькими доменами;

  - один лес с несколькими деревьями и несвязанными пространствами имен;

  - несколько лесов в топологии с центральным лесом;

  - несколько лесов в топологии с лесом ресурсов.

<div>


> [!NOTE]  
> Lync Server 2013 не поддерживает однокомпонентные домены. Например, лес с корневым доменом <STRONG>contoso.local</STRONG> поддерживается, а с однокомпонентным корневым доменом <STRONG>local</STRONG> — нет. Дополнительные сведения см. в статье 300684 базы знаний Майкрософт "сведения о настройке Windows для доменов с DNS-именем, сопоставленными с <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>одной меткой" по адресу ".



</div>

<div>


> [!NOTE]  
> Lync Server 2013 не поддерживает переименование доменов. Если требуется переименовать домен, на котором развернут Lync Server, сначала необходимо удалить Lync Server, затем переименовать домен, а затем переустановить Lync Server.



</div>

Подробные сведения о поддерживаемых топологиях и требованиях для локальных развертываний приведены в разделе [требования к доменным службам Active Directory, поддержке и топологий в Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) в документации по планированию.

</div>

<span> </span>

</div>

</div>

</div>

