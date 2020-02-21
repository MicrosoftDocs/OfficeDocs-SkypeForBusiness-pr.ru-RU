---
title: 'Lync Server 2013: развертывание архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Archiving
ms:assetid: a89edd16-12d5-4602-ad2f-194b47d1188e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205147(v=OCS.15)
ms:contentKeyID: 48185031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d31a4bdf75b649dec1d18a834335b0d47a69a3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="efabe-102">Развертывание архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efabe-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efabe-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="efabe-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="efabe-104">Lync Server 2013 предоставляет решение для архивации содержимого обмена мгновенными сообщениями и обмена мгновенными сообщениями в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efabe-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="efabe-105">Поддержку архивации можно реализовать путем интеграции хранилища архивации с хранилищем Exchange 2013, с помощью баз данных SQL Server для хранения данных архивации Lync Server 2013 или с помощью хранилища Lync Server 2013 и Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="efabe-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="efabe-106">Для управления архивацией данных используются политики и конфигурации архивации.</span><span class="sxs-lookup"><span data-stu-id="efabe-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="efabe-107">Дополнительные сведения приведены в статье [Планирование архивации в Lync server 2013](lync-server-2013-planning-for-archiving.md) в документации по планированию, а [также о том, как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="efabe-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="efabe-108">Для первичной настройки архивации можно использовать инструкции данного раздела.</span><span class="sxs-lookup"><span data-stu-id="efabe-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="efabe-109">После развертывания можно изменить параметры архивации.</span><span class="sxs-lookup"><span data-stu-id="efabe-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="efabe-110">Сведения о том, как реализовать поддержку архивации для повседневного управления или для удовлетворения новых требований в Организации, можно найти в статье [Управление процессом архивации Lync Server 2013](lync-server-2013-managing-archiving.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="efabe-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="efabe-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="efabe-111">In This Section</span></span>

  - [<span data-ttu-id="efabe-112">Принцип работы архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efabe-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="efabe-113">Контрольный список развертывания для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efabe-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="efabe-114">Настройка систем и инфраструктуры для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efabe-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="efabe-115">Добавление баз данных архивации к существующему развертыванию Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efabe-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="efabe-116">Настройка поддержки архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efabe-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

