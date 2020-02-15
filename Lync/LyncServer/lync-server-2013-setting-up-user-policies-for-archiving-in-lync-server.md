---
title: 'Lync Server 2013: Настройка политик пользователей для архивации в Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e6a04f976022ea4f3026c7be5caa3ce186efa77
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="7ca80-102">Настройка политик пользователей для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ca80-102">Setting up user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ca80-103">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="7ca80-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="7ca80-104">Для включения или отключения архивации для отдельных пользователей, размещенных в Lync Server 2013, необходимо создать и настроить одну или несколько политик пользователей, а затем применить соответствующую политику к определенным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="7ca80-104">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="7ca80-105">Политики пользователей переопределяют сайт и глобальные политики, но только для пользователей, размещенных в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ca80-105">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="7ca80-106">Пользователи всегда размещены в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ca80-106">Users are always homed in Lync Server.</span></span> <span data-ttu-id="7ca80-107">Если включена интеграция Microsoft Exchange, то для пользователей, чьи почтовые ящики находятся в Microsoft Exchange Server 2013, не нуждаются в политиках архивации в Lync Server Managed.</span><span class="sxs-lookup"><span data-stu-id="7ca80-107">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="7ca80-108">Этим пользователям с архивацией будет управлять удержание на месте Exchange.</span><span class="sxs-lookup"><span data-stu-id="7ca80-108">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="7ca80-109">Сведения о том, как работают политики архивации, в том числе иерархия для глобальных политик, политик сайтов и пользователей, приведены в статье Планирование, документация по развертыванию и документация по работе [при архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) .</span><span class="sxs-lookup"><span data-stu-id="7ca80-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ca80-110">Если вы включили интеграцию Microsoft Exchange для развертывания, политики хранения на месте Exchange управляют включением архивации для пользователей, размещенных в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="7ca80-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="7ca80-111">Для архивации требуется, чтобы почтовые ящики пользователей были помещены на судебное удержание.</span><span class="sxs-lookup"><span data-stu-id="7ca80-111">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="7ca80-112">Дополнительные сведения: <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="7ca80-112">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="7ca80-113">Перед включением архивации необходимо задать все требуемые параметры с помощью конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="7ca80-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="7ca80-114">Дополнительные сведения приведены в статье <A href="lync-server-2013-configuring-archiving-options.md">Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="7ca80-114">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7ca80-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="7ca80-115">In This Section</span></span>

  - [<span data-ttu-id="7ca80-116">Создание и Настройка политик пользователей для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ca80-116">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="7ca80-117">Применение политики архивации Lync Server к пользователю в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ca80-117">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

