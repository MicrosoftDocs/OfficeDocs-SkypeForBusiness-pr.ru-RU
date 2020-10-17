---
title: 'Lync Server 2013: определение и Настройка топологии в построителе топологий'
description: 'Lync Server 2013: определение и Настройка топологии в построителе топологий.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a1f29ec78cf7cfd3856d3f1aa87a22dc0bbe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569945"
---
# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="0c6bc-103">Определение и Настройка топологии в построителе топологий для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c6bc-103">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c6bc-104">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0c6bc-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0c6bc-105">С помощью построителя топологий, чтобы определить новую топологию или изменить существующую, не требуется членство в группе "локальный администратор" или "Привилегированный домен".</span><span class="sxs-lookup"><span data-stu-id="0c6bc-105">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="0c6bc-106">В построителе топологий рассказывается о том, как определить топологию для пула переднего плана Enterprise Edition или Standard Edition в соответствии с вашими требованиями к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-106">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="0c6bc-107">Для завершения и публикации топологии перед установкой Lync Server 2013 на серверах необходимо использовать построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-107">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="0c6bc-108">Приведенная ниже процедура включает в себя действия по определению новой топологии.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-108">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="0c6bc-109">Определение топологии</span><span class="sxs-lookup"><span data-stu-id="0c6bc-109">To define a topology</span></span>

1.  <span data-ttu-id="0c6bc-110">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="0c6bc-111">В построителе топологий выберите **создать топологию**.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-111">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="0c6bc-112">Отображается запрос на указание расположения и имени файла для сохранения топологии.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-112">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="0c6bc-113">Задайте для файла смысловое имя и подтвердите расширение по умолчанию TBXML.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-113">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="0c6bc-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-114">Click **OK**.</span></span>

3.  <span data-ttu-id="0c6bc-115">Перейдите в расположение, куда требуется сохранить XML-файл новой топологии, введите имя файла и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-115">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="0c6bc-116">На странице **Назначение основного домена** введите имя основного SIP-домена для своей организации и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-116">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="0c6bc-117">На странице **Указание дополнительных поддерживаемых доменов** введите имена дополнительных доменов (при их наличии) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-117">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="0c6bc-118">На странице **Назначение первого сайта** введите имя и описание первого сайта и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-118">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="0c6bc-119">На странице **Указание подробных сведений о сайте** введите информацию о размещении сайта и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-119">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="0c6bc-120">На странице **Новая топология успешно определена** убедитесь, что установлен флажок **открыть мастер создания переднего плана при закрытии мастера** , а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-120">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="0c6bc-121">После определения и сохранения топологии воспользуйтесь новым мастером переднего плана, чтобы определить интерфейсный пул или сервер Standard Edition для вашего сайта.</span><span class="sxs-lookup"><span data-stu-id="0c6bc-121">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="0c6bc-122">Дополнительные сведения см [в разделе Определение и Настройка пула переднего плана или сервера Standard Edition в Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="0c6bc-122">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

