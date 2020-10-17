---
title: загрузка топологии из существующего развертывания;
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 903b115eaa820245135e0bc2c3650ba596c5d925
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502906"
---
# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="7fd1a-102">загрузка топологии из существующего развертывания;</span><span class="sxs-lookup"><span data-stu-id="7fd1a-102">Download topology from existing deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fd1a-103">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="7fd1a-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="7fd1a-104">При создании пула Lync Server 2013 вы будете использовать центральное хранилище управления, связанное с Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7fd1a-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="7fd1a-105">При запуске построителя топологий при первом использовании и в последующих сеансах редактирования, отображается запрос на ввод расположения, из которого построитель топологий должен загрузить текущий документ конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7fd1a-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="7fd1a-106">Так как вы уже определили топологию Lync Server 2010 и установили центральное хранилище управления, необходимо выбрать загрузку топологии из существующего развертывания.</span><span class="sxs-lookup"><span data-stu-id="7fd1a-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="7fd1a-107">Построитель топологии прочитает базу данных и извлечет текущее определение.</span><span class="sxs-lookup"><span data-stu-id="7fd1a-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="7fd1a-108">**Загрузка топологии из существующего развертывания**</span><span class="sxs-lookup"><span data-stu-id="7fd1a-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="7fd1a-109">Откройте **мастер развертывания Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7fd1a-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="7fd1a-110">На странице **Lync Server 2013 — мастер развертывания** нажмите кнопку **Установить средства администрирования**.</span><span class="sxs-lookup"><span data-stu-id="7fd1a-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="7fd1a-111">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013** и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7fd1a-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="7fd1a-112">Выберите пункт **Download Topology from existing deployment** (Загрузить топологию из существующего развертывания).</span><span class="sxs-lookup"><span data-stu-id="7fd1a-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="7fd1a-113">![Параметры построителя топологии мастера развертывания](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Параметры построителя топологии мастера развертывания")</span><span class="sxs-lookup"><span data-stu-id="7fd1a-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="7fd1a-114">Выберите имя файла и сохраните топологию с типом файла по умолчанию (TBXML).</span><span class="sxs-lookup"><span data-stu-id="7fd1a-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="7fd1a-115">Разверните узел Lync Server, как показано, чтобы отобразить различные роли сервера в развертывании.</span><span class="sxs-lookup"><span data-stu-id="7fd1a-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="7fd1a-116">![Общие свойства роли сервера построителя топологии](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Общие свойства роли сервера построителя топологии")</span><span class="sxs-lookup"><span data-stu-id="7fd1a-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

