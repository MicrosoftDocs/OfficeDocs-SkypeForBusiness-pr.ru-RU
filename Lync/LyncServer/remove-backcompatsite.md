---
title: Удаление BackCompatSite
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
ms.openlocfilehash: 792fcf29033a7495a7da340decb561e25084612d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="218d4-102">Удаление BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="218d4-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="218d4-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="218d4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="218d4-104">После отключения всех пулов и удаления всех пограничных серверов запустите мастер объединения построителя топологий, чтобы удалить узел **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="218d4-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="218d4-105">Удаление сайта BackCompat из построителя топологий</span><span class="sxs-lookup"><span data-stu-id="218d4-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="218d4-106">Откройте существующую среду в окне построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="218d4-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="218d4-107">В меню **Действие** выберите **Объединить топологию 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="218d4-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="218d4-108">Нажмите кнопку **Далее**, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="218d4-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="218d4-109">На странице **указание устаревшей пограничной** страницы убедитесь, что список пограничных серверов пуст.</span><span class="sxs-lookup"><span data-stu-id="218d4-109">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span></span> <span data-ttu-id="218d4-110">Если этот список не пуст, нажмите кнопку **Удалить**, чтобы удалить все унаследованные пограничные серверы, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="218d4-110">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="218d4-111">![Мастер создания топологии слиянием, задать страницу настройки пограничного сервера](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Мастер создания топологии слиянием, задать страницу настройки пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="218d4-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="218d4-112">На странице **Определение значения внутреннего порта SIP** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="218d4-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="218d4-113">На странице **Сводка** нажмите кнопку **Далее** , чтобы начать объединение топологий для удаления устаревшего сайта.</span><span class="sxs-lookup"><span data-stu-id="218d4-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="218d4-114">Убедитесь, что столбец **Состояние** содержит значение **Успешно**, а затем нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="218d4-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="218d4-115">В левой части построителя топологий разверните BackCompatSite и убедитесь в отсутствии серверов в списке.</span><span class="sxs-lookup"><span data-stu-id="218d4-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="218d4-116">Щелкните правой кнопкой мыши **BackCompatSite** и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="218d4-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="218d4-117">В **Построителе топологий** выберите узел верхнего уровня **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="218d4-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="218d4-118">В меню **Действие** выберите пункт **Опубликовать топологию**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="218d4-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="218d4-119">По завершении работы **мастера публикации** нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="218d4-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

