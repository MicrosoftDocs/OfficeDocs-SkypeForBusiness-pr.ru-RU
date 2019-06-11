---
title: Управление архивацией внутренней и внешней связи
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a9e3c0a0708075eecc28282021f98724325ff6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="f59fc-102">Управление архивированием внутренней и внешней связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f59fc-102">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f59fc-103">_**Тема последнего изменения:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="f59fc-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="f59fc-104">В Lync Server 2013 вы используете политики архивации для включения и отключения архивации для внутренней связи и внешней связи, если вы не используете интеграцию с Microsoft Exchange или если у вас нет пользователей, которые не подключены к Exchange 2013 с почтовыми ящиками, на которые они помещаются. Хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="f59fc-104">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="f59fc-105">К ним относятся следующие политики архивации:</span><span class="sxs-lookup"><span data-stu-id="f59fc-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="f59fc-106">Глобальная политика, созданная по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f59fc-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="f59fc-107">Необязательные политики уровня сайта и уровня пользователя, которые можно создавать и использовать для определения способа реализации архивации для конкретных сайтов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="f59fc-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="f59fc-108">Изначально политики архивации были настроены при развертывании архивации, но вы можете изменить, добавить и удалить политики после развертывания.</span><span class="sxs-lookup"><span data-stu-id="f59fc-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="f59fc-109">В панели управления Lync Server 2013 вы можете управлять политиками на глобальном уровне, уровне сайта и на уровне пользователей с помощью страницы **политики архивации** в группе **Архивация и мониторинг** .</span><span class="sxs-lookup"><span data-stu-id="f59fc-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="f59fc-110">Если вы интегрирует хранилище Lync Server с хранилищем Exchange 2013, политики пользователей Exchange имеют приоритет над политиками архивации Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f59fc-110">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="f59fc-111">Сведения о том, как реализованы политики, в том числе об иерархии политик, описаны [в разделе Работа с архивацией в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="f59fc-111">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f59fc-112">Чтобы управлять реализацией архивации, необходимо указать параметры в конфигурациях архивации, например, следует ли архивировать сообщения или конференции, использовать критический режим и параметры очистки.</span><span class="sxs-lookup"><span data-stu-id="f59fc-112">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="f59fc-113">По умолчанию параметры не включены в глобальной конфигурации архивации или конфигурации архивации сайта или пула.</span><span class="sxs-lookup"><span data-stu-id="f59fc-113">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="f59fc-114">Прежде чем включать архивирование для внутренних или внешних сообщений в политиках архивации, необходимо задать все соответствующие параметры в параметрах конфигурации архивации.</span><span class="sxs-lookup"><span data-stu-id="f59fc-114">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="f59fc-115">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайты и пулы</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="f59fc-115">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="f59fc-116">При включении интеграции Microsoft Exchange для развертывания политики Exchange определяют, разрешено ли архивирование для пользователей, использующих Exchange 2013, и почтовые ящики, которые помещаются на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="f59fc-116">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="f59fc-117">Подробности можно найти в разделе <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f59fc-117">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f59fc-118">Содержание</span><span class="sxs-lookup"><span data-stu-id="f59fc-118">In This Section</span></span>

  - [<span data-ttu-id="f59fc-119">Создание политики архивации в Lync Server 2013 для включения и отключения архивации внутренних или внешних сообщений определенных сайтов и пользователей</span><span class="sxs-lookup"><span data-stu-id="f59fc-119">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users</span></span>](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)

  - [<span data-ttu-id="f59fc-120">Изменение политики архивации в Lync Server 2013 для включения и отключения архивирования внутренней или внешней связи для Организации, сайтов и пользователей</span><span class="sxs-lookup"><span data-stu-id="f59fc-120">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-changing-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-your-organization-sites-or-us.md)

  - [<span data-ttu-id="f59fc-121">Применение политики архивации к пользователям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f59fc-121">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="f59fc-122">Настройка политик для архивации в Lync Server 2013 при использовании интеграции с Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f59fc-122">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="f59fc-123">Удаление политики архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f59fc-123">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

