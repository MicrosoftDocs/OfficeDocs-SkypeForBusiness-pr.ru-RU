---
title: 'Lync Server 2013: процесс развертывания для отправки группового звонка'
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
ms.openlocfilehash: 015aa2817b7d829d1714288182775b42ba2bb1f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="6dbab-102">Процесс развертывания для отправки группового звонка в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dbab-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dbab-103">_**Тема последнего изменения:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="6dbab-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="6dbab-104">В этом разделе приводятся общие сведения о процедуре развертывания группового звонка.</span><span class="sxs-lookup"><span data-stu-id="6dbab-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="6dbab-105">Перед настройкой отправки группового звонка необходимо развернуть Enterprise Edition или Standard Edition с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="6dbab-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="6dbab-106">Компоненты, необходимые для отправки группового звонка, устанавливаются и включаются при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="6dbab-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="6dbab-107">Процесс развертывания компонента группового ответа на звонки</span><span class="sxs-lookup"><span data-stu-id="6dbab-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dbab-108">Этап</span><span class="sxs-lookup"><span data-stu-id="6dbab-108">Phase</span></span></th>
<th><span data-ttu-id="6dbab-109">Шаги</span><span class="sxs-lookup"><span data-stu-id="6dbab-109">Steps</span></span></th>
<th><span data-ttu-id="6dbab-110">Необходимые группы и роли</span><span class="sxs-lookup"><span data-stu-id="6dbab-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="6dbab-111">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="6dbab-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dbab-112">Включение средства набора ресурсов Сефаутил в топологии</span><span class="sxs-lookup"><span data-stu-id="6dbab-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6dbab-113">С помощью командлета <strong>New-CsTrustedApplicationPool</strong> создайте новый доверенный пул приложений.</span><span class="sxs-lookup"><span data-stu-id="6dbab-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="6dbab-114">С помощью командлета<strong>New-CsTrustedApplication</strong> задайте инструмент SEFAUtil в качестве доверенного приложения.</span><span class="sxs-lookup"><span data-stu-id="6dbab-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="6dbab-115">Выполните командлет <strong>Enable-CsTopology</strong> для включения топологии.</span><span class="sxs-lookup"><span data-stu-id="6dbab-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="6dbab-116">Установите средства набора ресурсов на сервере переднего плана, который находится в надежном пуле приложений, созданном на этапе 1.</span><span class="sxs-lookup"><span data-stu-id="6dbab-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="6dbab-117">Убедитесь, что SEFAUtil выполняется правильно, воспользовавшись им для отображения параметров переадресации звонков какого-либо пользователя в развертывании.</span><span class="sxs-lookup"><span data-stu-id="6dbab-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6dbab-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6dbab-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="6dbab-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6dbab-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dbab-120">Настройте диапазоны номеров для ответа на звонки в таблице орбит парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="6dbab-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="6dbab-121">С помощью командлета <strong>New-кскаллпаркорбит</strong> можно создать диапазоны номеров для отправки звонков в таблице "приостановить Звонок", а затем назначить диапазон раскладки для набора грауппиккуп.</span><span class="sxs-lookup"><span data-stu-id="6dbab-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6dbab-122">Вы должны использовать командную консоль Lync Server для создания, изменения, удаления и просмотра диапазонов номеров отправки групп в таблице "приостановить Звонок".</span><span class="sxs-lookup"><span data-stu-id="6dbab-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="6dbab-123">На панели управления Lync Server не доступны диапазоны номеров для отправки групповых звонков.</span><span class="sxs-lookup"><span data-stu-id="6dbab-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="6dbab-p103">Для простой интеграции с существующими абонентскими группами диапазоны номеров обычно настраиваются как блок виртуальных расширений. Назначение номеров DID как номеров диапазона в таблице орбит парковки вызовов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6dbab-p103">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="6dbab-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6dbab-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6dbab-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="6dbab-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="6dbab-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="6dbab-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="6dbab-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6dbab-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6dbab-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Настройка номеров групп для отправки звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6dbab-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dbab-131">Назначение абоненту номера для отправки и включения группового приема для пользователей</span><span class="sxs-lookup"><span data-stu-id="6dbab-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="6dbab-132">Используйте параметр/енаблеграуппиккуп в средстве Сефаутил Resource Kit для включения отправки группового звонка и назначения номера для отправки звонков пользователям.</span><span class="sxs-lookup"><span data-stu-id="6dbab-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6dbab-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Включение отправки группового звонка для пользователей в Lync Server 2013 и назначение номера группы</a></span><span class="sxs-lookup"><span data-stu-id="6dbab-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dbab-134">Уведомление пользователей о назначенном им номере ответа на звонок и любом другом важном номере</span><span class="sxs-lookup"><span data-stu-id="6dbab-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="6dbab-135">Поскольку любой пользователь может получить звонок пользователю для отправки группового звонка, пользователям может потребоваться мониторинг нескольких групп.</span><span class="sxs-lookup"><span data-stu-id="6dbab-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6dbab-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Связь групп раскладки звонков для пользователей в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6dbab-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dbab-137">Проверка развертывания для группового приема звонков</span><span class="sxs-lookup"><span data-stu-id="6dbab-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="6dbab-138">Тестирование размещения и получения звонков для обеспечения работоспособности вашей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6dbab-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6dbab-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Необязательно Проверка развертывания отправки группового звонка в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6dbab-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

