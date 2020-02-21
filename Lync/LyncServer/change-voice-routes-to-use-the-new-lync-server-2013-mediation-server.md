---
title: Изменение маршрутов голосовой связи для использования нового сервера-посредника Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4998057543f6695104ecbe759135b6735160c23
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="276e3-102">Изменение маршрутов голосовой связи для использования нового сервера-посредника Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="276e3-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="276e3-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="276e3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="276e3-104">Эта процедура изменяет маршруты голосовой связи для использования сервера-посредника Lync Server 2013 вместо устаревшего сервера-посредника Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="276e3-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="276e3-105">Изменение маршрутов голосовых вызовов для использования нового сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="276e3-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="276e3-106">Панель управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="276e3-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="276e3-107">В левой области выберите пункт **Маршрутизация голосовой связи**, а затем — **Route**.</span><span class="sxs-lookup"><span data-stu-id="276e3-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="276e3-108">Нажмите кнопку **Создать**, чтобы создать маршрут голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="276e3-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="276e3-109">Заполните следующие поля.</span><span class="sxs-lookup"><span data-stu-id="276e3-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="276e3-p101">**Имя** — введите описательное имя маршрута голосовых вызовов. Для примера мы используем имя **W15PSTNRoute**.</span><span class="sxs-lookup"><span data-stu-id="276e3-p101">**Name**: Type a descriptive name of the voice route. For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="276e3-112">**Описание** — введите краткое описание маршрута голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="276e3-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="276e3-p102">Пропустите следующие разделы до раздела **Связанные шлюзы**. Нажмите кнопку **Добавить**. Выберите новый шлюз по умолчанию и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="276e3-p102">Skip all remaining sections until you reach **Associated gateways**. Click **Add**. Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="276e3-116">В разделе **Связанные использования ТСОП** нажмите кнопку **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="276e3-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="276e3-117">На странице **Выбор записи об использовании ТСОП** выберите имя записи и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="276e3-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="276e3-118">На странице **Новый маршрут голосовой связи** нажмите кнопку **ОК**, чтобы создать **маршрут голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="276e3-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="276e3-119">На странице **Маршрутизация голосовой связи** выберите пункт **Route**.</span><span class="sxs-lookup"><span data-stu-id="276e3-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="276e3-120">Переместите созданный маршрут в начало списка и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="276e3-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

