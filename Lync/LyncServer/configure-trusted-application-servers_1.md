---
title: Настройка доверенных серверов приложений
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92e7f2c808e9ea5a3e8dfbf3010715c86e02596e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="857a9-102">Настройка доверенных серверов приложений</span><span class="sxs-lookup"><span data-stu-id="857a9-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="857a9-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="857a9-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="857a9-104">В смешанной среде при создании нового доверенного сервера приложений после объединения старой топологии сервера Office Communications с Lync Server 2013 и определения нового доверенного сервера приложений с помощью Topology Builder необходимо настроить пул следующего прыжка как Пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="857a9-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="857a9-105">В Объединенной среде в раскрывающемся списке отображаются устаревшая группа Office Communications Server и пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="857a9-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="857a9-106">Выбор устаревшего пула *не* поддерживается.</span><span class="sxs-lookup"><span data-stu-id="857a9-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="857a9-107">Выбор пункта Lync Server 2013 в качестве следующего прыжка при создании надежного сервера приложений</span><span class="sxs-lookup"><span data-stu-id="857a9-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="857a9-108">Откройте существующую топологию в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="857a9-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="857a9-109">В левой области щелкните правой кнопкой мыши **Доверенные серверы приложений** и выберите команду **создать доверенный пул приложений**.</span><span class="sxs-lookup"><span data-stu-id="857a9-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="857a9-110">Введите **полное доменное имя пула** для доверенного пула приложений и укажите, будет ли это развертывание одним сервером или с несколькими серверами.</span><span class="sxs-lookup"><span data-stu-id="857a9-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="857a9-111">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="857a9-111">Click **Next**.</span></span>

5.  <span data-ttu-id="857a9-112">На странице **Выбор следующего прыжка** в списке выберите пул внешних интерфейсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="857a9-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="857a9-113">![Диалоговое окно определения нового доверенного пула приложений](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Диалоговое окно определения нового доверенного пула приложений")</span><span class="sxs-lookup"><span data-stu-id="857a9-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="857a9-114">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="857a9-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="857a9-115">Выберите верхний узел **Lync Server** и на панели **действия** нажмите кнопку **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="857a9-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="857a9-116">Убедитесь, что **доверенный пул приложений** успешно создан и связан с правильным пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="857a9-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

