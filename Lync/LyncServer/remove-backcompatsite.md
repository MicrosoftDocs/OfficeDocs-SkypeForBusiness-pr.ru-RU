---
title: Удалить Бакккомпатсите
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6a3d1dc92e45bc99892e7827394376b6f28b12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="86ddf-102">Удалить Бакккомпатсите</span><span class="sxs-lookup"><span data-stu-id="86ddf-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86ddf-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="86ddf-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="86ddf-104">После деактивации всех пулов и удаления всех пограничных серверов запустите мастер слияния построителя топологии, чтобы удалить **бакккомпатсите**.</span><span class="sxs-lookup"><span data-stu-id="86ddf-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="86ddf-105">Удаление несовместимого веб-сайта из построителя топологии</span><span class="sxs-lookup"><span data-stu-id="86ddf-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="86ddf-106">Откройте существующее развертывание в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="86ddf-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="86ddf-107">В меню **действия** выберите пункт **топология слиянием 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="86ddf-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="86ddf-108">Для продолжения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="86ddf-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="86ddf-109">Убедитесь, что на странице **Определение устаревшего** пограничного сервера установлен пустой список пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="86ddf-109">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span></span> <span data-ttu-id="86ddf-110">Если список не пуст, удалите все старые пограничные серверы с помощью кнопки " **Удалить** ", а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="86ddf-110">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="86ddf-111">![Мастер топологии слиянием, задание страницы настройки ребра] (images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Мастер топологии слиянием, задание страницы настройки ребра")</span><span class="sxs-lookup"><span data-stu-id="86ddf-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="86ddf-112">На странице **Определение параметров внутреннего порта SIP** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="86ddf-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="86ddf-113">На странице **Сводка** нажмите кнопку **Далее** , чтобы начать объединение топологий для удаления устаревшего сайта.</span><span class="sxs-lookup"><span data-stu-id="86ddf-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="86ddf-114">В столбце **Status (состояние** ) убедитесь, что значение установлено **успешно** , и нажмите кнопку **Готово** , чтобы закрыть окно мастера.</span><span class="sxs-lookup"><span data-stu-id="86ddf-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="86ddf-115">На левой панели построителя топологии разверните узел Бакккомпатсите и убедитесь, что серверы не указаны в списке.</span><span class="sxs-lookup"><span data-stu-id="86ddf-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="86ddf-116">Щелкните **бакккомпатсите**правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="86ddf-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="86ddf-117">В **построителе топологии**выберите самый верхний узел **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="86ddf-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="86ddf-118">В меню **действие** выберите пункт **топология публикации** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="86ddf-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="86ddf-119">После завершения работы **мастера публикации** нажмите кнопку **Готово** , чтобы закрыть окно мастера.</span><span class="sxs-lookup"><span data-stu-id="86ddf-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

