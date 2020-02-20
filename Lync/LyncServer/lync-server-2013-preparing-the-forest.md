---
title: 'Lync Server 2013: подготовка леса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6f8ff7bbbdd7e1f941b941e2c9446e5890b97dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="b1806-102">Подготовка леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1806-102">Preparing the forest for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1806-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b1806-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b1806-104">При подготовке леса создаются глобальные параметры и объекты Active Directory, а также универсальные группы Active Directory для использования в Lync Server 2013, а также предоставляются соответствующие разрешения на доступ к объектам Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b1806-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="b1806-105">Описание универсальных групп и глобальных параметров и объектов, созданных при подготовке леса, приведены [в статье изменения, внесенные при подготовке леса в Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span><span class="sxs-lookup"><span data-stu-id="b1806-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="b1806-106">При подготовке леса также создаются объекты, содержащие наборы свойств и описатели отображения, используемые Lync Server 2013, и хранятся в контейнере конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b1806-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b1806-107">Убедитесь, что изменения, внесенные при подготовке схемы, реплицированы на все контроллеры домена перед выполнением процедуры подготовки леса.</span><span class="sxs-lookup"><span data-stu-id="b1806-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="b1806-108">Если репликация не выполнена, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="b1806-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="b1806-109">При выполнении нового развертывания Lync Server необходимо хранить глобальные параметры в контейнере конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b1806-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="b1806-110">Если вы выполняете обновление предыдущей версии и все еще храните глобальные параметры в контейнере System, вы можете продолжить использовать этот контейнер.</span><span class="sxs-lookup"><span data-stu-id="b1806-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="b1806-111">Чтобы выполнить данную процедуру, вы должны быть членом группы «Администраторы предприятия» или «Администраторы домена» для корневого домена леса.</span><span class="sxs-lookup"><span data-stu-id="b1806-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b1806-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="b1806-112">In This Section</span></span>

  - [<span data-ttu-id="b1806-113">Выполнение подготовки леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1806-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="b1806-114">Использование командлетов для отмены подготовки леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1806-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

