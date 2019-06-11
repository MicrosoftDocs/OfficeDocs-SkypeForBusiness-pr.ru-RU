---
title: 'Lync Server 2013: Настройка политик пользователей для архивации в Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3921956949f38390277328495398970203993377
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="7af02-102">Настройка политик пользователей для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7af02-102">Setting up user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7af02-103">_**Тема последнего изменения:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="7af02-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="7af02-104">Включение и отключение архивации для конкретных пользователей, размещенных на Lync Server 2013, требует создания и настройки одной или нескольких политик пользователей, а затем применения соответствующей политики к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="7af02-104">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="7af02-105">Политики пользователей переопределяют сайты и глобальные политики, но только для пользователей, размещенных на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7af02-105">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="7af02-106">Пользователи всегда будут размещены в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7af02-106">Users are always homed in Lync Server.</span></span> <span data-ttu-id="7af02-107">Если включена интеграция Microsoft Exchange, то для пользователей, чьи почтовые ящики находятся в Microsoft Exchange Server 2013, они не нуждаются в политиках архивации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7af02-107">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="7af02-108">Эти пользователи с архивацией будут управляться хранением на месте.</span><span class="sxs-lookup"><span data-stu-id="7af02-108">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="7af02-109">Сведения о том, как работают политики архивации, в том числе иерархия глобальных, сайтов и пользовательских политик, описаны в разделе [Использование архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="7af02-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7af02-110">Если вы включили интеграцию Microsoft Exchange для развертывания, политики хранения на месте Exchange определяют, включено ли архивирование для пользователей, использующих Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="7af02-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="7af02-111">Для архивации данных пользователей необходимо, чтобы их почтовые ящики были размещены на месте.</span><span class="sxs-lookup"><span data-stu-id="7af02-111">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="7af02-112">Подробности можно найти в разделе <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="7af02-112">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="7af02-113">Перед включением архивации необходимо указать все соответствующие параметры в разделе конфигурации архивации.</span><span class="sxs-lookup"><span data-stu-id="7af02-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="7af02-114">Подробности можно найти <A href="lync-server-2013-configuring-archiving-options.md">в разделе Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="7af02-114">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7af02-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="7af02-115">In This Section</span></span>

  - [<span data-ttu-id="7af02-116">Создание и Настройка политик пользователей для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7af02-116">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="7af02-117">Применение политики архивации в Lync Server к пользователю в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7af02-117">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

