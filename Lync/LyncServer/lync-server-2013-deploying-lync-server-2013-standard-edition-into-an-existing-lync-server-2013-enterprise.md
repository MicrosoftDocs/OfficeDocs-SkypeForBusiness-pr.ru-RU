---
title: 'Lync Server 2013: Развертывание Lync Server 2013 Standard Edition на базе существующего развертывания Lync Server 2013 Enterprise'
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
ms.openlocfilehash: 6467ae9eb3c4d5159181a2d022c060b0b9f1fec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="d4940-102">Развертывание Lync Server 2013 Standard Edition на базе существующего развертывания Lync Server 2013 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d4940-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4940-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d4940-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d4940-104">Развертывание стандартного выпуска сервера в существующем развертывании Enterprise Edition похоже на развертывание дополнительных ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="d4940-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="d4940-105">Сервер Standard Edition может быть развернут на другом сайте, что позволяет пользователям на нем работать на сервере Standard Edition, а не в пуле переднего плана в глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="d4940-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="d4940-106">Процедуры для установки нового сайта и серверов на этом сайте уже определены в других разделах документации по [развертыванию Lync Server 2013](lync-server-2013-deploying-lync-server.md) .</span><span class="sxs-lookup"><span data-stu-id="d4940-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="d4940-107">**Определение нового сайта**</span><span class="sxs-lookup"><span data-stu-id="d4940-107">**To define a new site**</span></span>

1.  <span data-ttu-id="d4940-108">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d4940-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d4940-109">В дереве консоли щелкните правой кнопкой мыши **Lync Server 2013**и выберите пункт **создать центральный сайт**.</span><span class="sxs-lookup"><span data-stu-id="d4940-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="d4940-110">На странице **Определение сайта** укажите имя сайта и, при необходимости, введите описание.</span><span class="sxs-lookup"><span data-stu-id="d4940-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="d4940-111">Следуйте инструкциям по определению оставшейся части топологии сайта.</span><span class="sxs-lookup"><span data-stu-id="d4940-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="d4940-112">Подробные сведения можно найти [в разделе Определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="d4940-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="d4940-113">Опубликуйте обновленную топологию.</span><span class="sxs-lookup"><span data-stu-id="d4940-113">Publish the updated topology.</span></span> <span data-ttu-id="d4940-114">Подробности можно найти [в разделе Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="d4940-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="d4940-115">Настройка и установка сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d4940-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="d4940-116">Если вы развернули среду только на стандартном сервере выпуска, вы могли бы приступили к установке из мастера развертывания Lync Server, используя ссылку <STRONG>Prepare First Standard Edition</STRONG> , чтобы установить начальные файлы базы данных на новый сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d4940-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="d4940-117"><STRONG>Не</STRONG> поддерживайте этот процесс при установке стандартного выпуска сервера в существующем развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4940-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

