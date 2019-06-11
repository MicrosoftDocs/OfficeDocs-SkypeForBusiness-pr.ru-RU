---
title: Изменение маршрутов голосовой связи для использования нового сервера исправлений Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 898901690b1caf5d57b33ffaec7231080554cca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="2e931-102">Изменение маршрутов голосовой связи для использования нового сервера исправлений Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e931-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e931-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2e931-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2e931-104">Эта процедура изменяет маршруты голосовой связи на использование сервера обновлений Lync Server 2013 вместо устаревшего сервера Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2e931-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="2e931-105">Изменение голосовых маршрутов для использования нового сервера обновлений</span><span class="sxs-lookup"><span data-stu-id="2e931-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="2e931-106">управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e931-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="2e931-107">На левой панели выберите пункт **Маршрутизация голоса** и щелкните **маршрут**.</span><span class="sxs-lookup"><span data-stu-id="2e931-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="2e931-108">Нажмите кнопку **создать** , чтобы создать новый голосовой маршрут.</span><span class="sxs-lookup"><span data-stu-id="2e931-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="2e931-109">Заполните следующие поля:</span><span class="sxs-lookup"><span data-stu-id="2e931-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="2e931-110">**Name (имя**): введите описательное имя маршрута голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2e931-110">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="2e931-111">Для этого документа мы будем использовать **W15PSTNRoute**.</span><span class="sxs-lookup"><span data-stu-id="2e931-111">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="2e931-112">**Описание**: введите краткое описание голосового маршрута.</span><span class="sxs-lookup"><span data-stu-id="2e931-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="2e931-113">Пропускать все оставшиеся разделы, пока не дойдете до **соответствующих шлюзов**.</span><span class="sxs-lookup"><span data-stu-id="2e931-113">Skip all remaining sections until you reach **Associated gateways**.</span></span> <span data-ttu-id="2e931-114">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2e931-114">Click **Add**.</span></span> <span data-ttu-id="2e931-115">Выберите новый шлюз по умолчанию и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2e931-115">Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="2e931-116">В разделе **связанные использование PSTN**нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="2e931-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="2e931-117">На странице **Выбор записи по использованию PSTN** выберите имя записи и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2e931-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="2e931-118">На странице **Новый голосовой маршрут** нажмите кнопку **ОК** , чтобы создать **голосовой маршрут**.</span><span class="sxs-lookup"><span data-stu-id="2e931-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="2e931-119">На странице **Маршрутизация голоса** нажмите кнопку **маршрут**.</span><span class="sxs-lookup"><span data-stu-id="2e931-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="2e931-120">Переместите созданный маршрут в верхнюю часть списка и нажмите кнопку **Commit (сохранить**).</span><span class="sxs-lookup"><span data-stu-id="2e931-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

