---
title: Подключение пилотного пула к старым пограничным серверам
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b83877505bfc9c2accc2057a9ebb1fb62355b3d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="68842-102">Подключение пилотного пула к старым пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="68842-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68842-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="68842-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="68842-104">После развертывания Lync Server 2013 маршрут Федерации для этого сайта не настроен.</span><span class="sxs-lookup"><span data-stu-id="68842-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="68842-105">Чтобы использовать федеративный маршрут, используемый Office Communications Server 2007 R2, Lync Server 2013 должен быть настроен для использования этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="68842-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="68842-106">Чтобы разрешить сайту Lync Server 2013 использовать директор и пограничный сервер BackCompatSite, используйте построитель топологий для связи устаревшего пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="68842-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="68842-107">Сопоставление старого пограничного пула с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="68842-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="68842-108">Откройте пилотную топологию пула в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="68842-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="68842-109">Выберите сайт Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68842-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="68842-110">В меню **Действие** щелкните **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="68842-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="68842-111">В разделе **назначение федеративного маршрута сайта**выберите **включить федерацию SIP**, а затем выберите Office Communications Server 2007 R2 или пограничный сервер Office Communications Server 2007 R2, если в списке нет директоров.</span><span class="sxs-lookup"><span data-stu-id="68842-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="68842-112">![Диалоговое окно "изменение свойств", страница "маршрут Федерации"](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Диалоговое окно "изменение свойств", страница "маршрут Федерации"")</span><span class="sxs-lookup"><span data-stu-id="68842-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="68842-113">Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.</span><span class="sxs-lookup"><span data-stu-id="68842-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="68842-114">В построителе топологий разверните узел Lync Server 2013 и перейдите к пулам **переднего плана** **сервера Standard Edition** или Enterprise Edition, щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="68842-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="68842-115">В разделе **Связи** установите флажок **Сопоставить пограничный пул (для компонентов мультимедиа)**.</span><span class="sxs-lookup"><span data-stu-id="68842-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="68842-116">Выберите из списка интерфейс пограничного сервера для BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="68842-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="68842-117">![Диалоговое окно "изменение свойств", страница "Общие"](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Диалоговое окно "изменение свойств", страница "Общие"")</span><span class="sxs-lookup"><span data-stu-id="68842-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="68842-118">Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.</span><span class="sxs-lookup"><span data-stu-id="68842-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="68842-119">В **построителе топологий** выберите самый верхний узел, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="68842-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="68842-120">В меню **Action** (Действие) выберите команду **Publish Topology** (Опубликовать топологию) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="68842-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="68842-121">Когда **мастер публикации** завершит работу, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="68842-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

