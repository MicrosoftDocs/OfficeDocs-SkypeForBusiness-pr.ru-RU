---
title: 'Lync Server 2013: Настройка и назначение политик архивации'
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
ms.openlocfilehash: 0d8cfb5b446456d99750529d883172ed3cb56e3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="cb41f-102">Настройка и назначение политик архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb41f-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb41f-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="cb41f-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="cb41f-104">В Lync Server 2013 вы используете политики для включения и отключения архивирования для внутренних коммуникаций и внешней связи для пользователей, которые размещены на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb41f-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="cb41f-105">К ним относятся следующие политики архивации:</span><span class="sxs-lookup"><span data-stu-id="cb41f-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="cb41f-106">Глобальная политика, созданная по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb41f-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="cb41f-107">Необязательные политики уровня сайта и уровня пользователя, которые можно создавать и использовать для определения способа реализации архивации для конкретных сайтов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="cb41f-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="cb41f-108">Изначально политики архивации были настроены при развертывании архивации, но вы можете изменить, добавить и удалить политики после развертывания.</span><span class="sxs-lookup"><span data-stu-id="cb41f-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="cb41f-109">В панели управления Lync Server 2013 вы можете управлять политиками на глобальном уровне, уровне сайта и на уровне пользователей с помощью страницы **политики архивации** в группе **Архивация и мониторинг** .</span><span class="sxs-lookup"><span data-stu-id="cb41f-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cb41f-110">Чтобы управлять реализацией архивации, необходимо указать параметры в конфигурациях архивации, например, следует ли архивировать сообщения или конференции, использовать критический режим и параметры очистки.</span><span class="sxs-lookup"><span data-stu-id="cb41f-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="cb41f-111">По умолчанию параметры не включены в глобальной конфигурации архивации или конфигурации архивации сайта или пула.</span><span class="sxs-lookup"><span data-stu-id="cb41f-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="cb41f-112">Прежде чем включать архивирование для внутренних или внешних сообщений в политиках архивации, необходимо задать все соответствующие параметры в параметрах конфигурации архивации.</span><span class="sxs-lookup"><span data-stu-id="cb41f-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="cb41f-113">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайты и пулы</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="cb41f-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="cb41f-114">Если вы интегрирует хранилище данных Lync Server с хранилищем Exchange 2013, политики пользователей Exchange имеют приоритет над политиками архивации Lync Server 2013, но только для тех пользователей, которые подключены к серверу Exchange 2013, на котором были помещены почтовые ящики, на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="cb41f-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="cb41f-115">Сведения о том, как реализованы политики, в том числе об иерархии политик, описаны [в разделе Работа с архивацией в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="cb41f-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="cb41f-116">Подробнее об управлении политиками после развертывания можно узнать в разделе [Управление архивацией внутренней и внешней связи в Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="cb41f-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cb41f-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="cb41f-117">In This Section</span></span>

  - [<span data-ttu-id="cb41f-118">Настройка глобальной политики архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb41f-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="cb41f-119">Настройка политик сайта для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb41f-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="cb41f-120">Настройка политик архивации для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb41f-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

