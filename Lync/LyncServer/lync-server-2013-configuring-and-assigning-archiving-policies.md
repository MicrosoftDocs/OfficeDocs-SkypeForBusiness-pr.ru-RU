---
title: 'Lync Server 2013: Настройка и назначение политик архивации'
description: 'Lync Server 2013: Настройка и назначение политик архивации.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebe08715433e04e56758c7fb09b331065fbd6f44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570915"
---
# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="9a2c2-103">Настройка и назначение политик архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a2c2-103">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a2c2-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9a2c2-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9a2c2-105">В Lync Server 2013 вы используете политики для включения и отключения архивации для внутренних коммуникаций и внешних коммуникаций для пользователей, размещенных в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a2c2-105">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="9a2c2-106">Доступны следующие политики архивации:</span><span class="sxs-lookup"><span data-stu-id="9a2c2-106">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="9a2c2-107">Глобальная политика, которая создается по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a2c2-107">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="9a2c2-108">Политики на уровне сайта и пользователя (необязательные), которые можно создать и использовать для указания параметров архивации для определенных сайтов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="9a2c2-108">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="9a2c2-109">Первичная настройка политик архивации выполняется при развертывании архивации, однако изменение, добавление и удаление политик доступно только после развертывания.</span><span class="sxs-lookup"><span data-stu-id="9a2c2-109">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="9a2c2-110">В панели управления Lync Server 2013 вы можете использовать страницу **Политика архивации** в группе **Архивация и мониторинг** для управления политиками на глобальном уровне, уровне сайта и на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a2c2-110">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a2c2-111">Для управления реализацией архивации необходимо указать параметры в конфигурациях архивации, например, задающие архивацию обмена мгновенными сообщениями или конференц-связи, использование критического режима и параметры очистки.</span><span class="sxs-lookup"><span data-stu-id="9a2c2-111">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="9a2c2-112">По умолчанию в глобальной конфигурации архивации и во всех конфигурациях архивации на уровне сайта и на уровне пула не включен ни один параметр.</span><span class="sxs-lookup"><span data-stu-id="9a2c2-112">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="9a2c2-113">Перед включением архивации для внутренних или внешних коммуникаций в политиках архивации необходимо указать все соответствующие параметры в конфигурациях архивации.</span><span class="sxs-lookup"><span data-stu-id="9a2c2-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="9a2c2-114">Дополнительные сведения: <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="9a2c2-114">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="9a2c2-115">Если вы интегрируете хранилище Lync Server с хранилищем Exchange 2013, то политики пользователей Exchange имеют приоритет над политиками архивации Lync Server 2013, но только для тех пользователей, которые размещены в Exchange 2013, у которых их почтовые ящики почтовые ящики In-Place удержания.</span><span class="sxs-lookup"><span data-stu-id="9a2c2-115">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="9a2c2-116">Для получения дополнительных сведений о реализации политик, включая иерархию политик, ознакомьтесь с [разработкой архивов в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="9a2c2-116">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="9a2c2-117">Дополнительные сведения об управлении политиками после развертывания приведены в статье [Управление архивацией внутренних и внешних коммуникаций в Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="9a2c2-117">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9a2c2-118">Содержание</span><span class="sxs-lookup"><span data-stu-id="9a2c2-118">In This Section</span></span>

  - [<span data-ttu-id="9a2c2-119">Настройка глобальной политики для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a2c2-119">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="9a2c2-120">Настройка политик сайта для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a2c2-120">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="9a2c2-121">Настройка политик архивации для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a2c2-121">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

