---
title: Настройка политик архивации при использовании интеграции с Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 948d57d753c774737d0a1c6b98bd24560d47606b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="f8bba-102">Настройка политик архивации в Lync Server 2013 при использовании интеграции с Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f8bba-102">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8bba-103">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="f8bba-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="f8bba-104">Если почтовые ящики пользователей, размещенных в Exchange 2013, имеют почтовые ящики на месте хранения на месте, политики хранения на месте Exchange управляют архивированием для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8bba-104">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="f8bba-105">Если вы используете интеграцию Microsoft Exchange для своего развертывания, политики Exchange 2013 переопределяют политики архивации Lync Server для пользователей, размещенных в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f8bba-105">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="f8bba-106">Сведения о настройке политик архивации Exchange можно найти в документации по Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f8bba-106">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="f8bba-107">Сведения о настройке политик пользователей для пользователей, размещенных на Lync Server 2013, приведены в статье [Настройка политик пользователей для архивации в Lync server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f8bba-107">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="f8bba-108">Чтобы узнать, как работают политики, посмотрите, [как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="f8bba-108">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f8bba-109">При развертывании Exchange 2013 и Lync Server 2013 в одном лесу политики хранения на месте Exchange 2013 для управления архивацией.</span><span class="sxs-lookup"><span data-stu-id="f8bba-109">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="f8bba-110">Если вы развертываете Exchange 2013 и Lync Server 2013 в отдельных лесах, ознакомьтесь со статьей "развертывание Lync Server и Microsoft Exchange в разных лесах" в <A href="lync-server-2013-deployment-checklist-for-archiving.md">контрольном списке развертывания для архивации в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f8bba-110">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

