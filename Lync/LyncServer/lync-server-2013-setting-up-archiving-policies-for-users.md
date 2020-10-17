---
title: 'Lync Server 2013: Настройка политик архивации для пользователей'
description: 'Lync Server 2013: Настройка политик архивации для пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c18a15c1a0611f49a6fd9a4983f3ce87104332e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559525"
---
# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="37801-103">Настройка политик архивации для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37801-103">Setting up Archiving policies for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37801-104">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="37801-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="37801-105">Вы можете включить или отключить архивацию для отдельных пользователей, создав и настроив для пользователей политику архивации, а затем применив ее к отдельным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="37801-105">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="37801-106">Политики пользователей переопределяют любую глобальную политику и политики сайтов.</span><span class="sxs-lookup"><span data-stu-id="37801-106">User policies override any global policy or site policies.</span></span> <span data-ttu-id="37801-107">Политики архивации применяются только в том случае, если вы не используете интеграцию с Microsoft Exchange или если вы используете интеграцию Microsoft Exchange, но у вас есть некоторые пользователи, которые не размещены в Exchange 2013 и почтовые ящики помещаются на In-Place удержание.</span><span class="sxs-lookup"><span data-stu-id="37801-107">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="37801-108">Сведения о том, как работают политики архивации, в том числе иерархия глобальных, сайтов и пользовательских политик, приведены в статье Планирование [работы архивации в среде Lync Server 2013](lync-server-2013-how-archiving-works.md) , документация по развертыванию или документация по операциям.</span><span class="sxs-lookup"><span data-stu-id="37801-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37801-109">Если для развертывания включена интеграция с Microsoft Exchange, политики хранения Exchange In-Place контролируют, включена ли архивация для пользователей, размещенных в Exchange 2013, и почтовые ящики помещаются на In-Place удержание.</span><span class="sxs-lookup"><span data-stu-id="37801-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="37801-110">Дополнительные сведения: <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="37801-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="37801-111">Чтобы включить архивацию внутренних и внешних коммуникаций в политиках архивации, вы должны указать все соответствующие параметры конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="37801-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="37801-112">Дополнительные сведения приведены в статье <A href="lync-server-2013-configuring-archiving-options.md">Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="37801-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="37801-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="37801-113">In This Section</span></span>

  - [<span data-ttu-id="37801-114">Настройка политик пользователей для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37801-114">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="37801-115">Настройка политик архивации в Lync Server 2013 при использовании интеграции с Exchange Server</span><span class="sxs-lookup"><span data-stu-id="37801-115">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

