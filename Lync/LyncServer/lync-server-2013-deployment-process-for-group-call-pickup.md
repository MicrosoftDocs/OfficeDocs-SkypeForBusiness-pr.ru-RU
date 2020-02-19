---
title: 'Lync Server 2013: процесс развертывания для групповой отправки звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150434b57aa90048c1009851473349093435c116
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="f2fad-102">Процесс развертывания для группового ответа на звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2fad-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2fad-103">_**Последнее изменение темы:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="f2fad-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="f2fad-104">В этом разделе представлен обзор действий, необходимых для развертывания групповой отправки вызовов.</span><span class="sxs-lookup"><span data-stu-id="f2fad-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="f2fad-105">Перед настройкой групповой отправки звонков необходимо развернуть Enterprise Edition или Standard Edition с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="f2fad-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="f2fad-106">Компоненты, необходимые для групповой отправки звонков, устанавливаются и включаются при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f2fad-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="f2fad-107">Процесс развертывания группового ответа на звонки</span><span class="sxs-lookup"><span data-stu-id="f2fad-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2fad-108">Этап</span><span class="sxs-lookup"><span data-stu-id="f2fad-108">Phase</span></span></th>
<th><span data-ttu-id="f2fad-109">Шаги</span><span class="sxs-lookup"><span data-stu-id="f2fad-109">Steps</span></span></th>
<th><span data-ttu-id="f2fad-110">Необходимые группы и роли</span><span class="sxs-lookup"><span data-stu-id="f2fad-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="f2fad-111">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="f2fad-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2fad-112">Включение средства SEFAUtil Resource Kit в топологии</span><span class="sxs-lookup"><span data-stu-id="f2fad-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f2fad-113">Используйте командлет <strong>New – кструстедаппликатионпул</strong> для создания нового пула доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="f2fad-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="f2fad-114">Используйте командлет <strong>New – кструстедаппликатион</strong> , чтобы указать средство SEFAUtil в качестве доверенного приложения.</span><span class="sxs-lookup"><span data-stu-id="f2fad-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="f2fad-115">Выполните командлет <strong>Enable – CsTopology</strong> , чтобы включить топологию.</span><span class="sxs-lookup"><span data-stu-id="f2fad-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="f2fad-116">Установите средства набора ресурсов на сервер переднего плана, который находится в пуле доверенных приложений, созданном на этапе 1.</span><span class="sxs-lookup"><span data-stu-id="f2fad-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="f2fad-117">Убедитесь, что SEFAUtil работает правильно, выполнив его, чтобы отобразить параметры переадресации звонков пользователя в развертывании.</span><span class="sxs-lookup"><span data-stu-id="f2fad-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f2fad-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f2fad-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="f2fad-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Развертывание средства SEFAUtil в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f2fad-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fad-120">Настройка диапазонов номеров для ответа на звонки в таблице орбит парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="f2fad-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="f2fad-121">Используйте командлет <strong>New – CSCallParkOrbit</strong> для создания диапазонов номеров для ответа на звонки в таблице орбит парковки вызовов и назначения диапазона ответа на звонки типу грауппиккуп.</span><span class="sxs-lookup"><span data-stu-id="f2fad-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f2fad-122">Для создания, изменения, удаления и просмотра групп номеров для ответа на звонки в таблице орбит парковки вызовов необходимо использовать командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2fad-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="f2fad-123">Диапазоны номеров для группового ответа на звонки недоступны в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2fad-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="f2fad-124">Для тесной интеграции с существующими абонентами, диапазоны номеров обычно настраиваются как блок виртуальных расширений.</span><span class="sxs-lookup"><span data-stu-id="f2fad-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="f2fad-125">Назначение непосредственных номеров (выполненных) в качестве номеров диапазонов в таблице орбит парковки вызовов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f2fad-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="f2fad-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f2fad-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f2fad-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f2fad-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="f2fad-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f2fad-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f2fad-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f2fad-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f2fad-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Настройка номеров групп для ответа на звонки в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f2fad-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fad-131">Назначение номера для ответа пользователям и включение групповой отправки звонков для пользователей</span><span class="sxs-lookup"><span data-stu-id="f2fad-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="f2fad-132">Используйте параметр/енаблеграуппиккуп в средстве SEFAUtil Resource Kit, чтобы включить отправке группового ответа и назначить для пользователей номер для ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="f2fad-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="f2fad-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Включение групповой отправки звонков для пользователей в Lync Server 2013 и назначение номера группы</a></span><span class="sxs-lookup"><span data-stu-id="f2fad-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2fad-134">Уведомлять пользователей о назначенном им номере для ответа и любое другое количество интересов</span><span class="sxs-lookup"><span data-stu-id="f2fad-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="f2fad-135">Так как любой пользователь может получить вызов, выполненный для группы пользователя ответа на звонок, пользователям может понадобиться мониторинг нескольких групп.</span><span class="sxs-lookup"><span data-stu-id="f2fad-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="f2fad-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Обмен назначениями группового ответа на звонки пользователям в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f2fad-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2fad-137">Проверка развертывания группового приема звонков</span><span class="sxs-lookup"><span data-stu-id="f2fad-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="f2fad-138">Тестирование размещения и извлечения вызовов убедитесь, что конфигурация работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="f2fad-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="f2fad-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Необязательно Проверка развертывания группового ответа на звонки в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f2fad-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

