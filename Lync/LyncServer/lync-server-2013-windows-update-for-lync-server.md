---
title: 'Lync Server 2013: обновление Windows для Lync Server'
description: 'Lync Server 2013: обновление Windows для Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows Update for Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518337(v=OCS.15)
ms:contentKeyID: 62625495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe4b6d201a35584fceae5628b91631b48b30faae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546065"
---
# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="f5484-103">Обновление Windows для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5484-103">Windows Update for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5484-104">_**Последнее изменение темы:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="f5484-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="f5484-105">Часто проверяйте и примените обновления и обновления для системы безопасности с помощью служб центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="f5484-105">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="f5484-106">Это помогает предотвратить возникновение уязвимостей в других компонентах системы, которые могут привести к тому, что злоумышленники смогут получить доступ к серверам, на которых работает Microsoft Lync Server 2013 с правами администратора, и таким образом ослабить Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5484-106">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="f5484-107">Обновления для Microsoft SQL Server 2008 Express (64-разрядный выпуск) выполняются на каждом сервере Lync 2013 Server версии Standard Edition (для серверной базы данных) и всех остальных ролей сервера Lync Server 2013 Server (для локального хранилища конфигурации), если эти базы данных не были обновлены до SQL Server 2008 R2 Express.</span><span class="sxs-lookup"><span data-stu-id="f5484-107">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="f5484-108">Эти базы данных следует рассматривать как часть повседневного обслуживания обновления системы безопасности, как в случае использования SQL Server в серверной базе данных интерфейсного пула, базы данных мониторинга и базы данных архивации.</span><span class="sxs-lookup"><span data-stu-id="f5484-108">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="f5484-109">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="f5484-109">Best Practice</span></span>

  - <span data-ttu-id="f5484-110">Сохранение текущих обновлений Windows.</span><span class="sxs-lookup"><span data-stu-id="f5484-110">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

