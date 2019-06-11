---
title: 'Lync Server 2013: публикация топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd542db6acedbec75e475045ae2ace6d63d5469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a><span data-ttu-id="0e61a-102">Публикация топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e61a-102">Publish your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e61a-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="0e61a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="0e61a-104">Каждый раз, когда вы используете Topology Builder для построения топологии, необходимо опубликовать топологию в базе данных в хранилище Центрального управления, чтобы эти данные можно было использовать для развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e61a-104">Each time you use Topology Builder to build your topology, you must publish the topology to a database in the Central Management store so that the data can be used to deploy Lync Server 2013.</span></span> <span data-ttu-id="0e61a-105">Чтобы опубликовать топологию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0e61a-105">Use the following procedure to publish your topology.</span></span>

<div>

## <a name="to-publish-the-topology"></a><span data-ttu-id="0e61a-106">Публикация топологии</span><span class="sxs-lookup"><span data-stu-id="0e61a-106">To publish the topology</span></span>

1.  <span data-ttu-id="0e61a-107">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0e61a-107">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="0e61a-108">В построителе топологии в дереве консоли щелкните правой кнопкой мыши **Lync 2013**и выберите команду **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="0e61a-108">In Topology Builder, in the console tree, right-click **Lync 2013**, and then click **Publish Topology**.</span></span>

3.  <span data-ttu-id="0e61a-109">На странице **приветствия** в мастере нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0e61a-109">On the **Welcome** page of the wizard, click **Next**.</span></span>

4.  <span data-ttu-id="0e61a-110">На странице **Topology Builder обнаружена страница хранилища CMS** , нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0e61a-110">On the **Topology Builder found a CMS store** page, click **Next**.</span></span>

5.  <span data-ttu-id="0e61a-111">На странице **создания других баз данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0e61a-111">On the **Create other databases** page, click **Next**.</span></span>

6.  <span data-ttu-id="0e61a-112">Когда состояние указывает на то, что создание базы данных прошло успешно, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0e61a-112">When the status indicates that database creation succeeded, do the following:</span></span>
    
      - <span data-ttu-id="0e61a-113">Для просмотра журнала нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="0e61a-113">To view the log, click **View log**.</span></span>
    
      - <span data-ttu-id="0e61a-114">Для завершения работы мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="0e61a-114">To close the wizard, click **Finish**.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="0e61a-115">Если это новая установка пограничного сервера или пула EDGE, необходимо экспортировать конфигурацию пограничного сервера на существующем сервере переднего плана, пуле переднего плана или стандартном сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0e61a-115">If this is a new installation of an Edge Server or Edge pool, you must export the Edge Server configuration from an existing Front End Server, Front End pool, or Standard Edition server.</span></span> <span data-ttu-id="0e61a-116">Для экспорта конфигурации ознакомьтесь со <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">сведениями о том, как экспортировать топологию Lync Server 2013 и скопировать ее на внешние носители для установки пограничного сервера</A>.</span><span class="sxs-lookup"><span data-stu-id="0e61a-116">To export the configuration, see <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A>.</span></span> <span data-ttu-id="0e61a-117">Вы будете импортировать файл конфигурации из внешнего носителя или сетевого общего доступа на этапе настройки и развертывания пограничных серверов с помощью мастера развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0e61a-117">You will import the configuration file from the external media or network share during the setup and deployment phase of the Edge Servers through the Lync Server Deployment Wizard.</span></span><BR><span data-ttu-id="0e61a-118">После того как пограничные серверы будут работоспособны, а локальная база данных хранится в локальной конфигурации, последующие обновления конфигурации Lync Server 2013 будут опубликованы и реплицированы на пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="0e61a-118">Once the Edge Servers are operational and the local configuration management store database is replicating with the internal deployment, subsequent updates to the Lync Server 2013 configuration will be published and replicated to the Edge Servers.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

