---
title: Требования Lync Server 2013 к конференц-связи с телефонным подключением
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6847c0e96da546d2387a66b9215e5c64b4743241
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="0a326-102">Требования к конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a326-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a326-103">_**Последнее изменение темы:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="0a326-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="0a326-104">Перед запуском процесса развертывания Lync Server 2013 необходимо спланировать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="0a326-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="0a326-105">конфигурацию, которая будет использоваться для подключения к телефонной сети общего пользования (ТСОП);</span><span class="sxs-lookup"><span data-stu-id="0a326-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="0a326-106">стратегию для назначения областей конференц-связи с телефонным подключением номерам доступа с телефонным подключением;</span><span class="sxs-lookup"><span data-stu-id="0a326-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="0a326-107">стратегию для создания каталогов конференций.</span><span class="sxs-lookup"><span data-stu-id="0a326-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="0a326-108">Планирование возможности телефонного подключения к сети ТСОП</span><span class="sxs-lookup"><span data-stu-id="0a326-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="0a326-109">Для конференц-связи с телефонным подключением требуется по крайней мере один сервер-посредник и хотя бы один шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="0a326-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="0a326-110">Сервер-посредник можно развернуть на центральном сайте или на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="0a326-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="0a326-111">На центральном сайте можно разместить сервер-посредник в пуле переднего плана или на сервере Standard Edition или развернуть его на изолированном сервере или в пуле.</span><span class="sxs-lookup"><span data-stu-id="0a326-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="0a326-112">На сайте филиала можно развернуть сервер-посредник на изолированном сервере или в качестве компонента устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="0a326-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="0a326-113">Шлюз ТСОП можно разворачивать на центральном сайте или на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="0a326-113">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="0a326-114">В сайте филиала шлюз PSTN может быть изолированным или компонентом устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="0a326-114">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a326-115">В конференц-связи с телефонным подключением не используется обход сервера-посредника, так как сервер видеоконференций не поддерживает обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="0a326-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="0a326-116">Сведения о планировании конфигурации сервера-посредника и шлюза PSTN для конференц-связи с телефонным подключением можно найти в статье [компоненты и топологии для сервера-посредника в Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="0a326-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="0a326-117">Планирование областей конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="0a326-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="0a326-p103">Во время настройки телефонного подключения создаются абонентские группы и номера доступа к конференциям с телефонным подключением. Абонентские группы — это наборы правил нормализации, которые задают количество и шаблон цифр в телефонном номере и преобразуют этот номер в стандартный формат E.164 для маршрутизации вызова. Номера доступа к конференции с телефонным подключением — это номера, которые набирают участники, чтобы присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="0a326-p103">During dial-in configuration, you create dial plans and dial-in conferencing access numbers. Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing. Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="0a326-p104">Каждый номер доступа к конференции с телефонным подключением должен быть связан хотя бы с одной абонентской группой. Области конференц-связи с телефонным подключением связывают номер доступа к конференции с телефонным подключением с его абонентскими группами. При настройке абонентской группы указывается область конференц-связи с телефонным подключением, которая использует эту абонентскую группу. При создании номера доступа для телефонного подключения выбираются те области, которые связывают этот номер доступа с соответствующими абонентскими группами.</span><span class="sxs-lookup"><span data-stu-id="0a326-p104">Every dial-in conferencing access number must be associated with at least one dial plan. Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans. When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="0a326-p105">При создании абонентской группы указывается ее область: уровень пользователя, уровень пула или уровень сайта. Каждому пользователю назначается абонентская группа из ближайшей области, подходящей пользователю. Например, пользователю назначается абонентская группа уровня пользователя, если она применима. Если она не применима, то пользователю назначается абонентская группа уровня пула. Если абонентская группа уровня пула не применима, то пользователю назначается абонентская группа уровня сайта. Если абонентская группа уровня сайта не применима, то пользователю назначается глобальная абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="0a326-p105">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope. Every user is assigned the dial plan from the narrowest scope that applies to the user. For example, a user is assigned a user-level dial plan, if one applies. If a user-level dial plan does not apply, the user is assigned a pool-level dial plan. If a pool-level dial plan does not apply, the user is assigned a site-level dial plan. If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="0a326-p106">Перед настройкой абонентских групп важно понять, как лучше назвать и использовать области. следующие соображения относятся к областям конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="0a326-p106">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="0a326-133">Обычно область — это географическая область, связанная с офисом или группой офисов.</span><span class="sxs-lookup"><span data-stu-id="0a326-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="0a326-p107">Языки связываются с номерами доступа для телефонного подключения. Если поддерживаются географические области, имеющие несколько языков, то следует решить, как следует задать области для поддержки нескольких языков. Например, можно задать несколько областей исходя из комбинации географической области и языка, или задать одну область исходя из географической области, а затем задать разные номера доступа для каждого языка.</span><span class="sxs-lookup"><span data-stu-id="0a326-p107">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="0a326-137">Когда пользователь планирует собрание, по умолчанию это собрание использует область, указанную абонентской группой этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="0a326-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="0a326-138">По умолчанию в приглашение на собрание включаются все номера доступа для телефонного подключения для конкретной области.</span><span class="sxs-lookup"><span data-stu-id="0a326-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="0a326-139">Важно давать областям такие имена, чтобы их можно было легко распознавать.</span><span class="sxs-lookup"><span data-stu-id="0a326-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="0a326-140">Пользователь может использовать имена областей для изменения области собрания, чтобы в приглашение включались разные номера доступа.</span><span class="sxs-lookup"><span data-stu-id="0a326-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="0a326-141">(Когда пользователи используют Outlook для планирования собрания, пользователь использует надстройку "собрание по сети" для Lync 2013, чтобы изменить регион).</span><span class="sxs-lookup"><span data-stu-id="0a326-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="0a326-142">Области должны быть построены таким образом, чтобы любой приглашенный, желающий присоединиться к собранию, мог видеть локальный номер доступа в приглашении на конференцию.</span><span class="sxs-lookup"><span data-stu-id="0a326-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="0a326-143">Вы можете настроить порядок, в котором номера доступа в области отображаются на странице параметров конференц-связи с телефонным подключением (и, следовательно, порядок их появления в приглашении на конференцию) с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a326-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="0a326-144">Любой пользователь из любого расположения может набрать любой номер доступа для присоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="0a326-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="0a326-145">Планирование каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="0a326-145">Planning for Conference Directories</span></span>

<span data-ttu-id="0a326-146">Каталоги конференций поддерживают сопоставление буквенно-цифрового идентификатора собраний, который участник использует для присоединения к Конференции при использовании Lync 2013, и идентификатор одноранговой конференции, который используется участником конференц-связи с телефонным подключением для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="0a326-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="0a326-147">Формат идентификатора конференции:</span><span class="sxs-lookup"><span data-stu-id="0a326-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="0a326-p110">Создание нескольких каталогов конференций позволяет использовать для конференций короткие идентификаторы, пока не будет создано значительное количество конференций. В организациях со стандартным количеством конференций на пользователя рекомендуется создавать по одному каталогу конференций для каждых 999 пользователей в пуле. Это правило позволит сохранить короткие идентификаторы конференций. Однако, когда количество каталогов конференций (во всех пулах) превысит 9, идентификационный номер конференций будет увеличиваться, чтобы поддерживать дополнительные конференции.</span><span class="sxs-lookup"><span data-stu-id="0a326-p110">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created. In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a326-152">См. также</span><span class="sxs-lookup"><span data-stu-id="0a326-152">See Also</span></span>


[<span data-ttu-id="0a326-153">Компонент сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a326-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="0a326-154">Абонентские группы и правила нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a326-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

