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
ms.openlocfilehash: 0747957a42c07c987f3123608d35fb86b5d4c036
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="622c9-102">Требования к инфраструктуре Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="622c9-102">Active Directory infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="622c9-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="622c9-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="622c9-104">Прежде чем приступать к подготовке доменных служб Active Directory для Lync Server 2013, убедитесь, что инфраструктура Active Directory соответствует следующим предварительным требованиям:</span><span class="sxs-lookup"><span data-stu-id="622c9-104">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="622c9-105">Все контроллеры домена (в том числе все серверы глобального каталога) в лесу, где развертывается Lync Server, работают под управлением одной из следующих операционных систем:</span><span class="sxs-lookup"><span data-stu-id="622c9-105">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="622c9-106">Операционная система Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="622c9-106">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="622c9-107">Операционная система Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="622c9-107">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="622c9-108">Операционная система Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="622c9-108">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="622c9-109">Операционная система Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="622c9-109">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="622c9-110">Windows Server 2008 Enterprise 32 — bit</span><span class="sxs-lookup"><span data-stu-id="622c9-110">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="622c9-111">32 — разрядная или 64 – разрядная версии операционной системы Windows Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="622c9-111">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="622c9-112">32 — разрядная или 64 — разрядная версия операционной системы Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="622c9-112">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="622c9-113">Все домены, в которых выполняется развертывание Lync Server, порождаются на функциональном уровне домена Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 или Windows Server 2003 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="622c9-113">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="622c9-114">Лес, в котором развертывается Lync Server, поступает на функциональный уровень леса Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 или хотя бы Windows Server 2003 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="622c9-114">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="622c9-115">Чтобы изменить режим работы домена или леса, ознакомьтесь со статьей "повышение функциональных уровней домена и леса" в библиотеке TechNet <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A>по адресу.</span><span class="sxs-lookup"><span data-stu-id="622c9-115">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="622c9-116">Глобальный каталог разворачивается в каждом домене, где развертываются компьютеры или пользователи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="622c9-116">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="622c9-117">Lync Server 2013 поддерживает универсальные группы в операционных системах Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 и Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="622c9-117">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="622c9-118">Участниками универсальных групп могут быть другие группы и учетные записи из любого домена в дереве доменов или лесу и могут получать разрешения в любом домене в дереве доменов или лесу.</span><span class="sxs-lookup"><span data-stu-id="622c9-118">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="622c9-119">Поддержка универсальных групп, в сочетании с делегированием прав администратора, упрощает управление развертыванием Lync Server.</span><span class="sxs-lookup"><span data-stu-id="622c9-119">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="622c9-120">Например, не нужно добавлять один домен к другому, чтобы разрешить администратору управлять обоими.</span><span class="sxs-lookup"><span data-stu-id="622c9-120">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

