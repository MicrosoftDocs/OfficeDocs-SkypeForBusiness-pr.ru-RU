---
title: Удаление BackCompatSite
description: Удаление BackCompatSite.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809324320ec1869ac0c9d324b8fc270a3cf8f174
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570275"
---
# <a name="remove-backcompatsite"></a><span data-ttu-id="90cf7-103">Удаление BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="90cf7-103">Remove BackCompatSite</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90cf7-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="90cf7-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="90cf7-105">После отключения всех пулов и удаления всех пограничных серверов запустите мастер объединения построителя топологий, чтобы удалить узел **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="90cf7-105">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="90cf7-106">Удаление сайта BackCompat из построителя топологий</span><span class="sxs-lookup"><span data-stu-id="90cf7-106">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="90cf7-107">Откройте существующую среду в окне построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="90cf7-107">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="90cf7-108">В меню **Действие** выберите **Объединить топологию 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="90cf7-108">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="90cf7-109">Нажмите кнопку **Далее**, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="90cf7-109">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="90cf7-110">На странице **указание устаревшей пограничной** страницы убедитесь, что список пограничных серверов пуст.</span><span class="sxs-lookup"><span data-stu-id="90cf7-110">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span></span> <span data-ttu-id="90cf7-111">Если этот список не пуст, нажмите кнопку **Удалить**, чтобы удалить все унаследованные пограничные серверы, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90cf7-111">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="90cf7-112">![Мастер создания топологии слиянием, задать страницу настройки пограничного сервера](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Мастер создания топологии слиянием, задать страницу настройки пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="90cf7-112">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="90cf7-113">На странице **Определение значения внутреннего порта SIP** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90cf7-113">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="90cf7-114">На странице **Сводка** нажмите кнопку **Далее** , чтобы начать объединение топологий для удаления устаревшего сайта.</span><span class="sxs-lookup"><span data-stu-id="90cf7-114">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="90cf7-115">Убедитесь, что столбец **Состояние** содержит значение **Успешно**, а затем нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="90cf7-115">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="90cf7-116">В левой части построителя топологий разверните BackCompatSite и убедитесь в отсутствии серверов в списке.</span><span class="sxs-lookup"><span data-stu-id="90cf7-116">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="90cf7-117">Щелкните правой кнопкой мыши **BackCompatSite** и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="90cf7-117">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="90cf7-118">В **Построителе топологий** выберите узел верхнего уровня **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="90cf7-118">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="90cf7-119">В меню **Действие** выберите пункт **Опубликовать топологию**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90cf7-119">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="90cf7-120">По завершении работы **мастера публикации** нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="90cf7-120">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

