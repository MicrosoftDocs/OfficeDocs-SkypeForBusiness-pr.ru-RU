---
title: 'Lync Server 2013: требования к инфраструктуре Active Directory'
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
ms.openlocfilehash: 75278700623ae7251fe7cebec36e959a38f325dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Требования к инфраструктуре Active Directory для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-11-07_

Прежде чем приступить к подготовке доменных служб Active Directory для Lync Server 2013, убедитесь, что инфраструктура Active Directory удовлетворяет следующим требованиям:

  - Все контроллеры домена (включая все серверы глобального каталога) в лесу, где развертывается сервер Lync Server, работают под управлением одной из следующих операционных систем.
    
      - Операционная система Windows Server 2012 R2
    
      - Операционная система Windows Server 2012
    
      - Операционная система Windows Server 2008 R2
    
      - Операционная система Windows Server 2008
    
      - Windows Server 2008 Enterprise 32-bit
    
      - 32-разрядная или 64-разрядная версии операционной системы Windows Server 2003 R2
    
      - 32-разрядная или 64-разрядная версии операционной системы Windows Server 2003

  - Все домены, в которых развертывается сервер Lync Server, порождаются на функциональном уровне домена Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 или не ниже Windows Server 2003.

  - Лес, в котором развертывается сервер Lync Server, передается на функциональный уровень леса Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 или хотя бы Windows Server 2003 или более поздней версии.
    
    <div>
    

    > [!NOTE]  
    > Чтобы изменить функциональный уровень домена или леса, ознакомьтесь со статьей "создание функциональных уровней домена и леса" в библиотеке <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>TechNet по адресу.

    
    </div>

  - Глобальный каталог разворачивается во всех доменах, где развертываются компьютеры или пользователи Lync Server.

Lync Server 2013 поддерживает универсальные группы в операционных системах Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 и Windows Server 2003. Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest. Поддержка универсальной группы в сочетании с делегированием администратора упрощает управление развертыванием Lync Server. For example, it is not necessary to add one domain to another to enable an administrator to manage both.

</div>

<span> </span>

</div>

</div>

</div>

