---
title: Управление архивацией внутренних и внешних коммуникаций
description: Управление архивацией внутренних и внешних коммуникаций.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 857e4772d93ead01c3914b2ee04b71bddb1feed4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564135"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="a9dd5-103">Управление архивацией внутренних и внешних коммуникаций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9dd5-103">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9dd5-104">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="a9dd5-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="a9dd5-105">В Lync Server 2013 политики архивирования используются для включения и отключения архивации для внутренних коммуникаций и внешних коммуникаций, если вы не используете интеграцию с Microsoft Exchange или у вас нет пользователей, которые не размещены в Exchange 2013 с их почтовыми ящиками на In-Place удержания.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-105">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a9dd5-106">Доступны следующие политики архивации:</span><span class="sxs-lookup"><span data-stu-id="a9dd5-106">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="a9dd5-107">Глобальная политика, которая создается по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-107">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="a9dd5-108">Политики на уровне сайта и пользователя (необязательные), которые можно создать и использовать для указания параметров архивации для определенных сайтов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-108">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="a9dd5-109">Первичная настройка политик архивации выполняется при развертывании архивации, однако изменение, добавление и удаление политик доступно только после развертывания.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-109">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="a9dd5-110">В панели управления Lync Server 2013 вы можете использовать страницу **Политика архивации** в группе **Архивация и мониторинг** для управления политиками на глобальном уровне, уровне сайта и на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-110">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="a9dd5-111">Если вы интегрируете хранилище Lync Server с хранилищем Exchange 2013, политики пользователей Exchange имеют приоритет над политиками архивации Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-111">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="a9dd5-112">Для получения дополнительных сведений о реализации политик, включая иерархию политик, ознакомьтесь с [разработкой архивов в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-112">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a9dd5-113">Для управления реализацией архивации необходимо указать параметры в конфигурациях архивации, например, задающие архивацию обмена мгновенными сообщениями или конференц-связи, использование критического режима и параметры очистки.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-113">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="a9dd5-114">По умолчанию в глобальной конфигурации архивации и во всех конфигурациях архивации на уровне сайта и на уровне пула не включен ни один параметр.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-114">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="a9dd5-115">Перед включением архивации для внутренних или внешних коммуникаций в политиках архивации необходимо указать все соответствующие параметры в конфигурациях архивации.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-115">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="a9dd5-116">Дополнительные сведения: <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-116">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="a9dd5-117">Если вы включаете интеграцию Microsoft Exchange для развертывания, политики Exchange контролируют, включена ли архивация для пользователей, размещенных в Exchange 2013, и почтовые ящики помещаются на In-Place удержание.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-117">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a9dd5-118">Дополнительные сведения: <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a9dd5-118">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a9dd5-119">Содержание</span><span class="sxs-lookup"><span data-stu-id="a9dd5-119">In This Section</span></span>

  - [<span data-ttu-id="a9dd5-120">Создание политики архивации в Lync Server 2013 для включения или отключения архивации внутренних или внешних коммуникаций для определенных сайтов или пользователей</span><span class="sxs-lookup"><span data-stu-id="a9dd5-120">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)

  - [<span data-ttu-id="a9dd5-121">Изменение политики архивации в Lync Server 2013 для включения или отключения архивации внутренних или внешних коммуникаций для Организации, сайтов или пользователей</span><span class="sxs-lookup"><span data-stu-id="a9dd5-121">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [<span data-ttu-id="a9dd5-122">Применение политики архивации к пользователям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9dd5-122">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="a9dd5-123">Настройка политик архивации в Lync Server 2013 при использовании интеграции с Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a9dd5-123">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="a9dd5-124">Удаление политики архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9dd5-124">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

