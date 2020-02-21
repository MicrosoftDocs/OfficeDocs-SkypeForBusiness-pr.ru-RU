---
title: 'Lync Server 2013: публикация топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a741fe97faebe40841c4b0173820c2fc90d5b87
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a><span data-ttu-id="54061-102">Публикация топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54061-102">Publish your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54061-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="54061-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="54061-104">Каждый раз, когда вы используете построитель топологий для построения топологии, необходимо опубликовать топологию в базе данных в центральном хранилище управления, чтобы эти данные можно было использовать для развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54061-104">Each time you use Topology Builder to build your topology, you must publish the topology to a database in the Central Management store so that the data can be used to deploy Lync Server 2013.</span></span> <span data-ttu-id="54061-105">Для публикации топологии используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="54061-105">Use the following procedure to publish your topology.</span></span>

<div>

## <a name="to-publish-the-topology"></a><span data-ttu-id="54061-106">Публикация топологии</span><span class="sxs-lookup"><span data-stu-id="54061-106">To publish the topology</span></span>

1.  <span data-ttu-id="54061-107">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="54061-107">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="54061-108">В построителе топологий в дереве консоли щелкните правой кнопкой мыши **Lync 2013**и выберите команду **опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="54061-108">In Topology Builder, in the console tree, right-click **Lync 2013**, and then click **Publish Topology**.</span></span>

3.  <span data-ttu-id="54061-109">На странице **Приветствия** мастера нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="54061-109">On the **Welcome** page of the wizard, click **Next**.</span></span>

4.  <span data-ttu-id="54061-110">На странице **Построитель топологии обнаружил хранилище CMS** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="54061-110">On the **Topology Builder found a CMS store** page, click **Next**.</span></span>

5.  <span data-ttu-id="54061-111">На странице **Создание других баз данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="54061-111">On the **Create other databases** page, click **Next**.</span></span>

6.  <span data-ttu-id="54061-112">Когда состояние указывает, что процесс создания базы данных успешно завершен, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="54061-112">When the status indicates that database creation succeeded, do the following:</span></span>
    
      - <span data-ttu-id="54061-113">Чтобы просмотреть журнал, нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="54061-113">To view the log, click **View log**.</span></span>
    
      - <span data-ttu-id="54061-114">Чтобы закрыть мастер, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="54061-114">To close the wizard, click **Finish**.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="54061-115">Если это новая установка пограничного сервера или пограничного пула, необходимо экспортировать конфигурацию пограничного сервера с существующего сервера переднего плана, интерфейсного пула или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="54061-115">If this is a new installation of an Edge Server or Edge pool, you must export the Edge Server configuration from an existing Front End Server, Front End pool, or Standard Edition server.</span></span> <span data-ttu-id="54061-116">Чтобы экспортировать конфигурацию, ознакомьтесь со статьей <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Экспорт вашей топологии Lync Server 2013 и ее копирование на внешние носители для установки пограничной системы</A>.</span><span class="sxs-lookup"><span data-stu-id="54061-116">To export the configuration, see <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A>.</span></span> <span data-ttu-id="54061-117">Вы будете импортировать файл конфигурации с внешнего носителя или из сетевой папки на этапе установки и развертывания пограничных серверов с помощью мастера развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54061-117">You will import the configuration file from the external media or network share during the setup and deployment phase of the Edge Servers through the Lync Server Deployment Wizard.</span></span><BR><span data-ttu-id="54061-118">После того как пограничные серверы будут работоспособны, а локальная база данных хранилища управления конфигураций будет реплицирована с использованием внутреннего развертывания, последующие обновления конфигурации Lync Server 2013 будут опубликованы и реплицированы на пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="54061-118">Once the Edge Servers are operational and the local configuration management store database is replicating with the internal deployment, subsequent updates to the Lync Server 2013 configuration will be published and replicated to the Edge Servers.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

