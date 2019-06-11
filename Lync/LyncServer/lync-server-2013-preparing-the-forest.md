---
title: 'Lync Server 2013: подготовка леса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c374252f94c3a872eacbb99a4f6b891204bb56cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="55bc5-102">Подготовка леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55bc5-102">Preparing the forest for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55bc5-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="55bc5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="55bc5-104">При подготовке леса создаются глобальные параметры и объекты Active Directory, а также универсальные группы Active Directory для использования в Lync Server 2013, а также предоставляются соответствующие разрешения на доступ к объектам Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55bc5-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="55bc5-105">Описание универсальных групп, а также глобальных параметров и объектов, созданных с помощью подготовки леса, приведены [в разделе изменения, внесенные в процессе подготовки леса в Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span><span class="sxs-lookup"><span data-stu-id="55bc5-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="55bc5-106">Подготовка леса также создает объекты, которые содержат наборы свойств и спецификаторы отображения, используемые в Lync Server 2013, и сохраняет их в контейнере конфигурации.</span><span class="sxs-lookup"><span data-stu-id="55bc5-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="55bc5-107">Перед выполнением процедуры подготовки леса убедитесь, что изменения подготовки схемы реплицированы на все контроллеры домена.</span><span class="sxs-lookup"><span data-stu-id="55bc5-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="55bc5-108">Если репликация не завершена, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="55bc5-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="55bc5-109">Если вы выполняете развертывание Lync Server, вы должны сохранить глобальные параметры в контейнере конфигурации.</span><span class="sxs-lookup"><span data-stu-id="55bc5-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="55bc5-110">Если вы обновляете более раннюю версию, но глобальные параметры по-прежнему хранятся в системном контейнере, вы можете продолжать использовать системный контейнер.</span><span class="sxs-lookup"><span data-stu-id="55bc5-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="55bc5-111">Для выполнения этой процедуры необходимо быть членом группы администраторов предприятия или администраторов домена для корневого домена леса.</span><span class="sxs-lookup"><span data-stu-id="55bc5-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="55bc5-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="55bc5-112">In This Section</span></span>

  - [<span data-ttu-id="55bc5-113">Проведение подготовки леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55bc5-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="55bc5-114">Использование командлетов для отмены подготовки леса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55bc5-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

