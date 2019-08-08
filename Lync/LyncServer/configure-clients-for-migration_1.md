---
title: Настройка клиентов для миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710a5cf6cb23b91431b340c44ebe6ff2738b0822
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a><span data-ttu-id="ce7dc-102">Настройка клиентов для миграции</span><span class="sxs-lookup"><span data-stu-id="ce7dc-102">Configure clients for migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce7dc-103">_**Тема последнего изменения:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="ce7dc-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="ce7dc-104">В этой статье описаны рекомендованные этапы развертывания клиента перед переходом на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce7dc-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="ce7dc-105">Эти изменения конфигурации следует вносить в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ce7dc-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="ce7dc-106">Прежде чем выполнять миграцию, очень важно выполнить эти действия.</span><span class="sxs-lookup"><span data-stu-id="ce7dc-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="ce7dc-107">Подробные сведения можно найти [в разделе Планирование клиентов и устройств в Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="ce7dc-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="ce7dc-108">Настройка клиентов перед миграцией</span><span class="sxs-lookup"><span data-stu-id="ce7dc-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="ce7dc-109">Развертывание самых последних обновлений сервера Office Communications Server 2007 R2, клиентов и устройств (исправлений):</span><span class="sxs-lookup"><span data-stu-id="ce7dc-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="ce7dc-110">Установка обновлений Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="ce7dc-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="ce7dc-111">Описание накопительного пакета обновления для Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="ce7dc-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="ce7dc-112">Получение обновлений программного обеспечения для устройств</span><span class="sxs-lookup"><span data-stu-id="ce7dc-112">Obtaining Software Updates for Devices</span></span>](http://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="ce7dc-113">В Office Communications Server 2007 R2 используйте фильтрацию по версии клиента, чтобы разрешить только клиентам Office Communications Server 2007 R2, у которых установлены последние обновления, чтобы войти в систему.</span><span class="sxs-lookup"><span data-stu-id="ce7dc-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="ce7dc-114">В Office Communications Server 2007 R2 используйте фильтрацию версий клиента, чтобы заблокировать вход в приложение Lync Server 2013 для клиентов.</span><span class="sxs-lookup"><span data-stu-id="ce7dc-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="ce7dc-115">Выполните действия, описанные в статье **Настройка фильтрации клиентских версий** [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) , чтобы добавить фильтры версий, указанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="ce7dc-115">Follow the steps described in **Configuring Client Version Filtering** at [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="ce7dc-116">Для каждого фильтра версий назначьте **блок**действий.</span><span class="sxs-lookup"><span data-stu-id="ce7dc-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ce7dc-117">Клиент</span><span class="sxs-lookup"><span data-stu-id="ce7dc-117">Client</span></span></th>
    <th><span data-ttu-id="ce7dc-118">Заголовок агента пользователя</span><span class="sxs-lookup"><span data-stu-id="ce7dc-118">User agent header</span></span></th>
    <th><span data-ttu-id="ce7dc-119">Версия</span><span class="sxs-lookup"><span data-stu-id="ce7dc-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ce7dc-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ce7dc-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="ce7dc-121">OC</span><span class="sxs-lookup"><span data-stu-id="ce7dc-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="ce7dc-122">15.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="ce7dc-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ce7dc-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="ce7dc-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="ce7dc-124">CWA</span><span class="sxs-lookup"><span data-stu-id="ce7dc-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="ce7dc-125">5.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="ce7dc-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ce7dc-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ce7dc-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="ce7dc-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="ce7dc-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="ce7dc-128">4.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="ce7dc-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

