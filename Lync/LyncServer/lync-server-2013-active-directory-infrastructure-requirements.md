---
title: 'Lync Server 2013: требования к инфраструктуре Active Directory'
description: 'Lync Server 2013: требования к инфраструктуре Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62218605c9b3fac20743d0b6bb475515c9498f9a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552365"
---
# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Требования к инфраструктуре Active Directory для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-11-07_

Прежде чем приступать к подготовке доменных служб Active Directory для Lync Server 2013, убедитесь, что инфраструктура Active Directory соответствует следующим предварительным требованиям:

  - Все контроллеры домена (в том числе все серверы глобального каталога) в лесу, где развертывается Lync Server, работают под управлением одной из следующих операционных систем:
    
      - Операционная система Windows Server 2012 R2
    
      - Операционная система Windows Server 2012
    
      - Операционная система Windows Server 2008 R2
    
      - Операционная система Windows Server 2008
    
      - Windows Server 2008 Enterprise 32 — bit
    
      - 32 — разрядная или 64 – разрядная версии операционной системы Windows Server 2003 R2
    
      - 32 — разрядная или 64 — разрядная версия операционной системы Windows Server 2003

  - Все домены, в которых выполняется развертывание Lync Server, порождаются на функциональном уровне домена Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 или Windows Server 2003 или более поздней версии.

  - Лес, в котором развертывается Lync Server, поступает на функциональный уровень леса Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 или хотя бы Windows Server 2003 или более поздней версии.
    
    <div>
    

    > [!NOTE]  
    > Чтобы изменить режим работы домена или леса, ознакомьтесь со статьей "повышение функциональных уровней домена и леса" в библиотеке TechNet по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A> .

    
    </div>

  - Глобальный каталог разворачивается в каждом домене, где развертываются компьютеры или пользователи Lync Server.

Lync Server 2013 поддерживает универсальные группы в операционных системах Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 и Windows Server 2003. Участниками универсальных групп могут быть другие группы и учетные записи из любого домена в дереве доменов или лесу и могут получать разрешения в любом домене в дереве доменов или лесу. Поддержка универсальных групп, в сочетании с делегированием прав администратора, упрощает управление развертыванием Lync Server. Например, не нужно добавлять один домен к другому, чтобы разрешить администратору управлять обоими.

</div>

<span> </span>

</div>

</div>

</div>

