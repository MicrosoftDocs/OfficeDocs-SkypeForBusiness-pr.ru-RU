---
title: 'Lync Server 2013: обзор архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f718ac939fc665c0464d4986f51279d3afdee8a3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="9dab3-102">Обзор архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dab3-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dab3-103">_**Тема последнего изменения:** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="9dab3-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="9dab3-104">Архивация в Lync Server 2013 предоставляет способ архивации сообщений, отправленных с помощью Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9dab3-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="9dab3-105">Вы можете внедрить архивацию как часть первоначального развертывания Lync Server 2013 или добавить ее в существующее развертывание.</span><span class="sxs-lookup"><span data-stu-id="9dab3-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="9dab3-106">Чтобы использовать базу данных архивации Lync Server 2013 (базы данных SQL Server) для хранения данных архивации, используйте Topology Builder, чтобы добавить базы данных в топологию, а затем опубликуйте топологию еще раз.</span><span class="sxs-lookup"><span data-stu-id="9dab3-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="9dab3-107">Если все ваши пользователи находятся в Exchange 2013 и почтовые ящики помещаются на хранение на месте, вам не нужно обновлять топологию, но для того чтобы хранить архивные данные в Exchange 2013, нужно только включить интеграцию Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="9dab3-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="9dab3-108">При внедрении архива вы настраиваете его, чтобы указать, что заархивировано.</span><span class="sxs-lookup"><span data-stu-id="9dab3-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="9dab3-109">По умолчанию ничего не архивируется.</span><span class="sxs-lookup"><span data-stu-id="9dab3-109">By default, nothing is archived.</span></span> <span data-ttu-id="9dab3-110">Настраивать архивирование и управлять ими можно с помощью панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9dab3-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="9dab3-111">Вы можете реализовать архивацию для внутренней связи, внешней связи или и того, и для других.</span><span class="sxs-lookup"><span data-stu-id="9dab3-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="9dab3-112">Вы можете настроить параметры архивирования всей Организации и, при необходимости, для определенных сайтов, определенных пулов и определенных пользователей и групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="9dab3-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="9dab3-113">Подробнее о том, как определить соответствующие параметры для Организации, можно найти [в разделе Определение требований для архивации в Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="9dab3-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="9dab3-114">Сведения о том, как выполняются политики архивирования и конфигурации, а также сведения о том, как [работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) , можно найти в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="9dab3-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

