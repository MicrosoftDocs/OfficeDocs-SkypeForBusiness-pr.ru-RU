---
title: 'Lync Server 2013: развертывание Lync Server 2013 Standard Edition в существующем сервере Lync Server 2013 Enterprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd3d666eefe04a6650a5c1a10253f490e391ff22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501516"
---
# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="ef82c-102">Развертывание Lync Server 2013 Standard Edition в существующем сервере Lync Server 2013 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ef82c-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef82c-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ef82c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ef82c-104">Развертывание сервера Standard Edition в существующем развертывании Enterprise Edition аналогично развертыванию дополнительных ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="ef82c-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="ef82c-105">Сервер Standard Edition может быть развернут на другом сайте, что позволяет пользователям на этом сайте размещаться на сервере Standard Edition, а не на пуле переднего плана в глобальной сети (WAN).</span><span class="sxs-lookup"><span data-stu-id="ef82c-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="ef82c-106">Процедуры установки нового сайта и серверов на этом сайте уже определены в других разделах документации по [развертыванию Lync Server 2013](lync-server-2013-deploying-lync-server.md) .</span><span class="sxs-lookup"><span data-stu-id="ef82c-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="ef82c-107">**Определение нового сайта**</span><span class="sxs-lookup"><span data-stu-id="ef82c-107">**To define a new site**</span></span>

1.  <span data-ttu-id="ef82c-108">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ef82c-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ef82c-109">В дереве консоли щелкните правой кнопкой мыши **Lync Server 2013**и выберите **создать центральный сайт**.</span><span class="sxs-lookup"><span data-stu-id="ef82c-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="ef82c-110">На странице **указания сайта** задайте имя для этого сайта и при желании введите описание.</span><span class="sxs-lookup"><span data-stu-id="ef82c-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="ef82c-111">Выполните процедуры по определению остальной топологии сайта.</span><span class="sxs-lookup"><span data-stu-id="ef82c-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="ef82c-112">Дополнительные сведения см [в статье определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="ef82c-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="ef82c-113">Опубликуйте обновленную топологию.</span><span class="sxs-lookup"><span data-stu-id="ef82c-113">Publish the updated topology.</span></span> <span data-ttu-id="ef82c-114">Дополнительные сведения см [в статье Publishing Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="ef82c-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="ef82c-115">Установка и установка сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ef82c-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="ef82c-116">Если вы развернули среду с сервером Standard Edition, процесс установки был начат в мастере развертывания Lync Server с помощью ссылки <STRONG>Подготовка первого сервера Standard</STRONG> Edition для установки исходных файлов базы данных на новый сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ef82c-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="ef82c-117"><STRONG>Не</STRONG> поддерживайте этот процесс при установке сервера Standard Edition в существующем развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef82c-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

