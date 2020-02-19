---
title: Настройка серверов доверенных приложений
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
ms.openlocfilehash: dcce9e045abbc0ad3d56362c37ac3e888a74130c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="1cfba-102">Настройка серверов доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="1cfba-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cfba-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="1cfba-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="1cfba-104">В смешанной среде при создании нового доверенного сервера приложений после объединения устаревшей топологии Office Communications Server с Lync Server 2013 и определения нового доверенного сервера приложений с помощью построителя топологий необходимо настроить пул следующего прыжка в значение Пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cfba-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="1cfba-105">В Объединенной среде в раскрывающемся списке отображаются устаревший пул Office Communications Server и пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cfba-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="1cfba-106">Выбор устаревшего пула *не* поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1cfba-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="1cfba-107">Выбор Lync Server 2013 в качестве следующего перехода при создании доверенного сервера приложений</span><span class="sxs-lookup"><span data-stu-id="1cfba-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="1cfba-108">Откройте существующую топологию в окне построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="1cfba-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="1cfba-109">В левой панели щелкните правой кнопкой мыши **Серверы доверенных приложений**, затем щелкните **Создать пул надежных приложений**.</span><span class="sxs-lookup"><span data-stu-id="1cfba-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="1cfba-110">Введите **Полное доменное имя пула** пула доверенных приложений и выберите будет ли это развертывание с одним или несколькими серверами.</span><span class="sxs-lookup"><span data-stu-id="1cfba-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="1cfba-111">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1cfba-111">Click **Next**.</span></span>

5.  <span data-ttu-id="1cfba-112">На странице **Выбор следующего прыжка** в списке выберите пул переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cfba-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="1cfba-113">![Диалоговое окно определения нового пула доверенных приложений](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Диалоговое окно определения нового пула доверенных приложений")</span><span class="sxs-lookup"><span data-stu-id="1cfba-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="1cfba-114">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="1cfba-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="1cfba-115">Выберите верхний узел **Lync Server**, затем на панели **Действия** выберите **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="1cfba-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="1cfba-116">Убедитесь, что **пул надежных приложений** был создан успешно и связан с надлежащим интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="1cfba-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

