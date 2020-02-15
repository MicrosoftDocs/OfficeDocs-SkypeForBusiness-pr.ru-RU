---
title: 'Lync Server 2013: Настройка существующего центрального сервера управления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50835858c9c78851ec5fc7359f988790bb0d1c2f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a>Настройка существующего центрального сервера управления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Если вы повторно восиспользуете центральный сервер управления из существующего развертывания Lync Server 2013, необходимо выполнить процедуру, описанную ниже, чтобы убедиться, что панель управления Lync Server и функция Windows PowerShell правильно работают.

<div>

## <a name="to-configure-an-existing-central-management-server"></a>Настройка существующего центрального сервера управления

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Используйте командлет **Update-CsAdminRole** , чтобы обновить роли управления доступом на основе РОЛЕЙ (RBAC), которые хранятся на центральном сервере управления.
    
    <div>
    

    > [!NOTE]  
    > При отсутствии ошибок вывод результатов не ожидается.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

