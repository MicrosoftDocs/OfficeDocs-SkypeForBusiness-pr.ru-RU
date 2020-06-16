---
title: Объединение с помощью мастера объединения в построителе топологий
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4760dcd8810d12b112c3bb042e0f28a039683a08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="d1af7-102">Объединение с помощью мастера объединения в построителе топологий</span><span class="sxs-lookup"><span data-stu-id="d1af7-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1af7-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d1af7-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="d1af7-104">Загрузите существующее развертывание с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="d1af7-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="d1af7-105">В меню **Action** (Действие) выберите команду **Merge Office Communications Server 2007 R2** (Объединить Office Communications Server 2007 R2).</span><span class="sxs-lookup"><span data-stu-id="d1af7-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="d1af7-106">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d1af7-106">Click **Next**.</span></span>

4.  <span data-ttu-id="d1af7-107">В диалоговом окне **настройки пограничного сервера** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d1af7-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="d1af7-108">![Мастер создания топологии слиянием, задать страницу настройки пограничного сервера](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Мастер создания топологии слиянием, задать страницу настройки пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="d1af7-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="d1af7-109">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="d1af7-109">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**.</span></span> <span data-ttu-id="d1af7-110">This example uses the **Single Edge Server** option.</span><span class="sxs-lookup"><span data-stu-id="d1af7-110">This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d1af7-111"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration.</span><span class="sxs-lookup"><span data-stu-id="d1af7-111"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration.</span></span> <span data-ttu-id="d1af7-112">An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span><span class="sxs-lookup"><span data-stu-id="d1af7-112">An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="d1af7-113">В поле **Укажите параметры внутреннего края** введите необходимые сведения о ВНУТРЕННЕМ полном доменном имени и портах пограничного пула, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d1af7-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="d1af7-114">![Диалоговое окно указания параметров внутреннего пограничного сервера](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Диалоговое окно указания параметров внутреннего пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="d1af7-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="d1af7-115">В диалоговом окне **указания внешнего пограничного сервера** введите сведения о полном доменном имени веб-конференций для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="d1af7-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d1af7-116">Before you click <STRONG>Next</STRONG>, do the next step in this procedure.</span><span class="sxs-lookup"><span data-stu-id="d1af7-116">Before you click <STRONG>Next</STRONG>, do the next step in this procedure.</span></span> <span data-ttu-id="d1af7-117">It is very important that you do not miss this step.</span><span class="sxs-lookup"><span data-stu-id="d1af7-117">It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="d1af7-118">Установите флажок **этот пограничный пул используется для Федерации и общедоступной службы обмена мгновенными сообщениями** , если вы планируете использовать устаревшее пограничный сервер Office Communications Server 2007 R2 для Федерации.</span><span class="sxs-lookup"><span data-stu-id="d1af7-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="d1af7-119">Если развернуто несколько пограничных серверов, то для федерации будет включен только один из них.</span><span class="sxs-lookup"><span data-stu-id="d1af7-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="d1af7-120">Если этот флажок не установить, а впоследствии потребуется включить федерацию, то придется запустить мастер слияния построителя топологий и снова опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="d1af7-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="d1af7-121">![Диалоговое окно пограничного сервера, укажите внешнюю страницу](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Диалоговое окно пограничного сервера, укажите внешнюю страницу")</span><span class="sxs-lookup"><span data-stu-id="d1af7-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="d1af7-122">В диалоговом окне **указания следующего прыжка** введите полное доменное имя расположения следующего прыжка в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="d1af7-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="d1af7-123">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d1af7-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="d1af7-124">![Диалоговое окно пограничного сервера, укажите страницу следующего прыжка](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Диалоговое окно пограничного сервера, укажите страницу следующего прыжка")</span><span class="sxs-lookup"><span data-stu-id="d1af7-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="d1af7-125">В окне **задать настройку пограничного**сервера, если были добавлены все пограничные серверы Office Communications Server 2007 R2, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d1af7-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="d1af7-126">Если вы добавляете дополнительные пограничные серверы Office Communications Server 2007 R2, повторите эту процедуру, начиная с шага 4.</span><span class="sxs-lookup"><span data-stu-id="d1af7-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="d1af7-127">В поле **укажите внутренний порт SIP** выберите значение по умолчанию (то есть, если вы не изменили порт SIP по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d1af7-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="d1af7-128">Если порт по умолчанию 5061 не используется, измените параметр соответствующим образом и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d1af7-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="d1af7-129">В окне **Сводка** нажмите кнопку **Далее**, чтобы начать слияние топологий.</span><span class="sxs-lookup"><span data-stu-id="d1af7-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="d1af7-130">Страница мастера проверяет успешность слияния топологий.</span><span class="sxs-lookup"><span data-stu-id="d1af7-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="d1af7-131">Убедитесь, что в столбце **Состояние** указано значение **Успешно**, и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d1af7-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="d1af7-132">На левой панели построителя топологий вы увидите **BackCompatSite**, который указывает, что ваша среда Office Communications Server 2007 R2 объединена с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1af7-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="d1af7-133">![Построитель топологий, демонстрирующий объединенную топологию](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Построитель топологий, демонстрирующий объединенную топологию")</span><span class="sxs-lookup"><span data-stu-id="d1af7-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="d1af7-134">В меню **Action** (Действие) выберите команду **Publish Topology** (Опубликовать топологию) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d1af7-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="d1af7-135">Когда **мастер публикации** завершит работу, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d1af7-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1af7-136">Важно выполнить следующий раздел, <A href="import-policies-and-settings.md">импортировать политики и параметры</A>, чтобы убедиться, что устаревшие параметры политики импортированы в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1af7-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

