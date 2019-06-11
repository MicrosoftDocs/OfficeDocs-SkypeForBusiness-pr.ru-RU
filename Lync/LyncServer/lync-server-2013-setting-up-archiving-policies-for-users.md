---
title: 'Lync Server 2013: Настройка политик архивации для пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55a56ff5c44d10d112762bb06662e9266dbc270b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="e8d26-102">Настройка политик архивации для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8d26-102">Setting up Archiving policies for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8d26-103">_**Тема последнего изменения:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="e8d26-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="e8d26-104">Вы можете включить или отключить архивацию для определенных пользователей, создав и настроив политику архивации для пользователей, а затем применяя политику к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="e8d26-104">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="e8d26-105">Политики пользователей переопределяют любую глобальную политику и политики сайтов.</span><span class="sxs-lookup"><span data-stu-id="e8d26-105">User policies override any global policy or site policies.</span></span> <span data-ttu-id="e8d26-106">Правила архивации применяются только в том случае, если вы не используете интеграцию с Microsoft Exchange или если вы используете интеграцию Microsoft Exchange, но у вас есть некоторые пользователи, которые не подключены к Exchange 2013, и почтовые ящики помещаются на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="e8d26-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="e8d26-107">Сведения о том, как работают политики архивации, в том числе иерархия для глобальных политик, политики сайтов и пользователей, описаны [в разделе Архивация в среде Lync Server 2013](lync-server-2013-how-archiving-works.md) , документация по планированию и документация по операциям.</span><span class="sxs-lookup"><span data-stu-id="e8d26-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8d26-108">Если вы включили интеграцию Microsoft Exchange для развертывания, политики хранения на месте Exchange определяют, разрешено ли архивирование для пользователей, использующих Exchange 2013, и почтовые ящики, которые помещаются на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="e8d26-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e8d26-109">Подробности можно найти в разделе <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e8d26-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="e8d26-110">Перед активацией архивации внутренних или внешних взаимодействий в политиках архивации необходимо указать все надлежащие параметры в конфигурациях архивации.</span><span class="sxs-lookup"><span data-stu-id="e8d26-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="e8d26-111">Подробности можно найти <A href="lync-server-2013-configuring-archiving-options.md">в разделе Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e8d26-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e8d26-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="e8d26-112">In This Section</span></span>

  - [<span data-ttu-id="e8d26-113">Настройка политик пользователей для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8d26-113">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="e8d26-114">Настройка политик для архивации в Lync Server 2013 при использовании интеграции с Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e8d26-114">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

