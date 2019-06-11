---
title: Требования Lync Server 2013 к конференц-связи с телефонным подключением
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f4878e81a28b5d51726cb1f3e2dc5c7c5aa0fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="6652e-102">Требования к конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6652e-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6652e-103">_**Тема последнего изменения:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="6652e-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="6652e-104">Прежде чем приступить к работе с Lync Server 2013, вам нужно спланировать указанные ниже возможности.</span><span class="sxs-lookup"><span data-stu-id="6652e-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="6652e-105">Конфигурация, используемая для подключения к телефонной сети с открытым коммутируемым подключением (КТСОП)</span><span class="sxs-lookup"><span data-stu-id="6652e-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="6652e-106">Стратегия назначения областей конференц-связи с телефонным подключением для номеров доступа с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="6652e-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="6652e-107">Стратегия создания каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="6652e-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="6652e-108">Планирование подключений с телефонным подключением через коммутируемую сеть</span><span class="sxs-lookup"><span data-stu-id="6652e-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="6652e-109">Для конференц-связи с телефонным подключением необходим хотя бы один сервер-посредник и хотя бы один шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="6652e-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="6652e-110">Сервер-посредник можно развернуть на центральном сайте или на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="6652e-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="6652e-111">На центральном сайте сервер-посредник можно разместить в пуле переднего плана или на сервере стандартного выпуска; его также можно развернуть его на изолированном сервере или в изолированном пуле.</span><span class="sxs-lookup"><span data-stu-id="6652e-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="6652e-112">На сайте филиала можно развернуть сервер-посредник на изолированном сервере или как компонент системы обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="6652e-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="6652e-p102">Шлюз ТСОП можно развернуть на центральном сайте или на сайте филиала. На сайте филиала шлюз ТСОП может быть изолированным или служить компонентом системы обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="6652e-p102">You can deploy a PSTN gateway in a central site or in a branch site. In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6652e-115">В конференц-связи с телефонным подключением не используется обход мультимедиа, так как сервер конференций/V не поддерживает мультимедийный обход.</span><span class="sxs-lookup"><span data-stu-id="6652e-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="6652e-116">Подробные сведения о планировании конфигурации сервера-посредников и шлюзов PSTN для конференц-связи с телефонным подключением можно найти в разделе [компоненты и топологии для сервера-посредника в Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="6652e-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="6652e-117">Планирование областей конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="6652e-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="6652e-118">Во время настройки телефонного подключения создаются абонентские группы и номера доступа для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="6652e-118">During dial-in configuration, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="6652e-119">Абонентские группы — это наборы правил нормализации, задающих число и количество цифр в номере телефона, а также перевод номера телефона в стандартный формат E. 164 для маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="6652e-119">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing.</span></span> <span data-ttu-id="6652e-120">Номера доступа к конференции с телефонным подключением — это номера, которые набирают участники, чтобы присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="6652e-120">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="6652e-121">Каждый номер доступа к конференции с телефонным подключением должен быть связан хотя бы с одной абонентской группой.</span><span class="sxs-lookup"><span data-stu-id="6652e-121">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> <span data-ttu-id="6652e-122">Регионы конференц-связи с телефонным подключением связывают номер доступа конференц-связи с телефонным подключением и абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="6652e-122">Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="6652e-123">Когда вы настраиваете абонентскую группу, вы указываете область конференц-связи с телефонным подключением, которая относится к абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="6652e-123">When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="6652e-124">При создании номера доступа по телефонной линии следует выбрать регион, связывающий номер доступа с подходящими абонентскими группами.</span><span class="sxs-lookup"><span data-stu-id="6652e-124">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="6652e-125">Когда вы создаете абонентскую группу, вы указываете область абонентской группы: область пользователя, область пула или область сайта.</span><span class="sxs-lookup"><span data-stu-id="6652e-125">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="6652e-126">Каждому пользователю назначается применимая к нему абонентская группа наиболее узкой области действия.</span><span class="sxs-lookup"><span data-stu-id="6652e-126">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="6652e-127">Например, если применима абонентская группа уровня пользователя, назначается эта абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="6652e-127">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="6652e-128">Если она не применима, пользователю назначается абонентская группа уровня пула.</span><span class="sxs-lookup"><span data-stu-id="6652e-128">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="6652e-129">Если абонентская группа уровня пула также не применима, назначается абонентская группа уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="6652e-129">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="6652e-130">Если и эта абонентская группа не применима, назначается глобальная абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="6652e-130">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="6652e-p106">Перед настройкой абонентских групп важно понять, как лучше назвать и использовать области. следующие соображения относятся к областям конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="6652e-p106">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="6652e-133">Обычно область — это географическая область, связанная с офисом или группой офисов.</span><span class="sxs-lookup"><span data-stu-id="6652e-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="6652e-p107">Языки связываются с номерами доступа для телефонного подключения. Если поддерживаются географические области, имеющие несколько языков, то следует решить, как следует задать области для поддержки нескольких языков. Например, можно задать несколько областей исходя из комбинации географической области и языка, или задать одну область исходя из географической области, а затем задать разные номера доступа для каждого языка.</span><span class="sxs-lookup"><span data-stu-id="6652e-p107">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="6652e-137">Когда пользователь планирует собрание, по умолчанию это собрание использует область, указанную абонентской группой этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="6652e-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="6652e-138">По умолчанию все номера доступа для телефонного подключения для региона включаются в приглашение на собрание.</span><span class="sxs-lookup"><span data-stu-id="6652e-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="6652e-139">It is important to name regions so that they are clearly recognizable.</span><span class="sxs-lookup"><span data-stu-id="6652e-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="6652e-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span><span class="sxs-lookup"><span data-stu-id="6652e-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="6652e-141">(Когда пользователи используют Outlook для планирования собрания, пользователь использует надстройку "собрание по сети" для Lync 2013, чтобы изменить регион).</span><span class="sxs-lookup"><span data-stu-id="6652e-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="6652e-142">Области должны быть построены таким образом, чтобы любой приглашенный, желающий присоединиться к собранию, мог видеть локальный номер доступа в приглашении на конференцию.</span><span class="sxs-lookup"><span data-stu-id="6652e-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="6652e-143">Вы можете настроить порядок, в котором номера доступа в регионе отображаются на странице параметров конференц-связи с телефонным подключением (и, соответственно, в том порядке, в котором они отображаются в приглашении на конференцию) с помощью командлетов командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6652e-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="6652e-144">Любой пользователь из любого расположения может набрать любой номер доступа для присоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="6652e-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="6652e-145">Планирование каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="6652e-145">Planning for Conference Directories</span></span>

<span data-ttu-id="6652e-146">В каталогах конференций поддерживается сопоставление буквенно-цифровых ИДЕНТИФИКАТОРов собраний, используемых участниками для присоединения к Конференции с помощью Lync 2013, а также идентификатора конференции, который используется участниками конференц-связи с телефонным подключением для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="6652e-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="6652e-147">Идентификатор конференции представлен в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="6652e-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="6652e-148">Создание нескольких каталогов конференций позволяет присваивать конференциям короткие идентификаторы, если количество конференций не слишком велико.</span><span class="sxs-lookup"><span data-stu-id="6652e-148">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="6652e-149">В организациях, где количество конференций на каждого пользователя находится в обычных пределах, рекомендуется создавать по одному каталогу конференций для каждых 999 пользователей в пуле.</span><span class="sxs-lookup"><span data-stu-id="6652e-149">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="6652e-150">С помощью этого правила идентификаторы конференций обычно можно оставлять небольшим.</span><span class="sxs-lookup"><span data-stu-id="6652e-150">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="6652e-151">Однако, если каталогов конференций (во всех пулах) больше девяти, для поддержки дополнительных конференции назначаются боле длинные идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="6652e-151">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6652e-152">См. также</span><span class="sxs-lookup"><span data-stu-id="6652e-152">See Also</span></span>


[<span data-ttu-id="6652e-153">Компонент сервера «исправления» в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6652e-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="6652e-154">Абонентские группы и правила нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6652e-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

