---
title: 'Lync Server 2013: абонентские группы и правила нормализации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6195baf2cdff30cad74dfddc31337d9d429c5d8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520026"
---
# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="82c5b-102">Абонентские группы и правила нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82c5b-102">Dial plans and normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82c5b-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="82c5b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="82c5b-104">Абонентская группа ? это именованный набор правил нормализации, которые преобразуют номера телефонов для именованного расположения, отдельного пользователя или контактного объекта в единый стандартный формат (E.164) для целей авторизации телефонов и маршрутизации вызовов.</span><span class="sxs-lookup"><span data-stu-id="82c5b-104">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="82c5b-p101">Правила нормализации определяют, как номера телефонов, заданные в различных форматах, перенаправляются в требуемое расположение, требуемому пользователю или контактному объекту. Одна и та же строка набора номера может интерпретироваться и преобразовываться по-разному, в зависимости от расположения, в котором она была набрана, и лица или контактного объекта, разместившего вызов.</span><span class="sxs-lookup"><span data-stu-id="82c5b-p101">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="82c5b-107">Область абонентской группы</span><span class="sxs-lookup"><span data-stu-id="82c5b-107">Dial Plan Scope</span></span>

<span data-ttu-id="82c5b-108">*Область* абонентской группы определяет иерархический уровень, на котором может применяться эта группа.</span><span class="sxs-lookup"><span data-stu-id="82c5b-108">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="82c5b-109">В Lync Server пользователю можно назначить определенную абонентскую абонентскую абонентскую абонентскую систему.</span><span class="sxs-lookup"><span data-stu-id="82c5b-109">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="82c5b-110">Если абонентская группа пользователя не назначена, применяется группа пула регистратора.</span><span class="sxs-lookup"><span data-stu-id="82c5b-110">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="82c5b-111">Если абонентская группа пула регистратора также отсутствует, применяется группа уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="82c5b-111">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="82c5b-112">Наконец, если для пользователя не заданы никакие другие группы, применяется глобальная абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="82c5b-112">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="82c5b-113">Клиенты получают уровни области абонентской группы с помощью параметров подготовки в стандартном расположении, которые предоставляются при входе пользователей на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82c5b-113">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="82c5b-114">Администратор может управлять и назначать уровни области абонентской группы с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82c5b-114">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82c5b-115">Абонентская группа шлюза телефонной сети общего пользования (ТСОП) уровня служб применяется к входящим звонкам с конкретного шлюза.</span><span class="sxs-lookup"><span data-stu-id="82c5b-115">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="82c5b-116">Уровни области абонентской группы определяются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="82c5b-116">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="82c5b-117">**Абонентская схема пользователя:** Можно назначить отдельным пользователям, группам или контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="82c5b-117">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="82c5b-118">Голосовые приложения могут запрашивать абонентскую группу на уровне пользователей в случае получения звонка, для которого установлено пользовательское значение по умолчанию телефонного контекста.</span><span class="sxs-lookup"><span data-stu-id="82c5b-118">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="82c5b-119">В рамках назначения абонентской группы контактный объект считается отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="82c5b-119">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="82c5b-120">**Абонентская группа пула:** Можно создать на уровне обслуживания для любого шлюза или регистратора PSTN в топологии.</span><span class="sxs-lookup"><span data-stu-id="82c5b-120">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="82c5b-121">Для определения абонентской группы пула необходимо указать конкретную службу (шлюз ТСОП или пул регистратора), к которой применяется абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="82c5b-121">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="82c5b-122">**Абонентская Схема сайта:** Может создаваться для всего сайта, за исключением пользователей, групп или контактных объектов, которым назначена абонентская группа пула или абонентская группа пользователя.</span><span class="sxs-lookup"><span data-stu-id="82c5b-122">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="82c5b-123">Чтобы определить абонентскую группу, следует указать сайт, к которому она применяется.</span><span class="sxs-lookup"><span data-stu-id="82c5b-123">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="82c5b-124">**Глобальная абонентская схема:** Абонентская схема по умолчанию, установленная вместе с продуктом.</span><span class="sxs-lookup"><span data-stu-id="82c5b-124">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="82c5b-125">Вы можете изменить глобальную абонентскую группу, но не можете удалить ее.</span><span class="sxs-lookup"><span data-stu-id="82c5b-125">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="82c5b-126">Эта абонентская группа применяется ко всем пользователям, группам и контактам корпоративной голосовой связи в развертывании, если не настроена и не назначена абонентская группа с более определенной областью.</span><span class="sxs-lookup"><span data-stu-id="82c5b-126">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="82c5b-127">Планирование абонентских групп</span><span class="sxs-lookup"><span data-stu-id="82c5b-127">Planning for Dial Plans</span></span>

<span data-ttu-id="82c5b-128">Для планирования абонентской группы выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="82c5b-128">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="82c5b-129">Укажите все адреса, по которым у вашей организации есть офис.</span><span class="sxs-lookup"><span data-stu-id="82c5b-129">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="82c5b-p108">Этот список должен быть полным и актуальным. По мере роста и развития организации его следует пересматривать. В большой международной компании с большим количеством небольших филиалов эта задача может потребовать довольно много времени.</span><span class="sxs-lookup"><span data-stu-id="82c5b-p108">The list must be up-to-date and complete. It will need to be revised as company organization evolves. In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="82c5b-133">Укажите допустимые шаблоны номеров для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="82c5b-133">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="82c5b-p109">Наиболее трудоемкой частью планирования абонентские группы является определение допустимых шаблонов номеров для каждого сайта. В некоторых случаях, возможно, получится скопировать правила нормализации, созданные для одной абонентской группы, в другие группы (особенно если соответствующие сайты находятся в пределах той же страны или региона или даже континента). В других случаях внесение небольших изменений в номера одной абонентской группы может быть достаточным для их использования в других абонентских группах.</span><span class="sxs-lookup"><span data-stu-id="82c5b-p109">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site. In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent. In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="82c5b-137">Разработайте схему для именования абонентских групп в рамках всей организации.</span><span class="sxs-lookup"><span data-stu-id="82c5b-137">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="82c5b-138">Принятие стандартной схемы именования гарантирует согласованность данных в пределах организации и упрощает решение задач обслуживания и обновления.</span><span class="sxs-lookup"><span data-stu-id="82c5b-138">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="82c5b-139">Решите, требуется ли использовать несколько абонентских групп для одного расположения.</span><span class="sxs-lookup"><span data-stu-id="82c5b-139">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="82c5b-140">Если ваша организация поддерживает одну абонентскую абонентскую систему для нескольких расположений, вам по-прежнему потребуется создать отдельную абонентскую схему для пользователей корпоративной голосовой связи, которые переходят с УАТС, и которые должны сохранить существующие расширения.</span><span class="sxs-lookup"><span data-stu-id="82c5b-140">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="82c5b-141">Решите,требуются ли абонентские группы для индивидуальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="82c5b-141">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="82c5b-142">Например, если у вас есть пользователи на сайте филиала, которые зарегистрированы на центральном сайте, или если у вас есть пользователи, зарегистрированные на устройстве для обеспечения связи в филиалах, вы можете рассмотреть специальные сценарии набора номера для таких пользователей, используя абонентские группы и правила нормализации для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="82c5b-142">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="82c5b-143">Дополнительные сведения см. в статье [требования к устойчивости для сайтов филиалов для Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82c5b-143">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="82c5b-144">Определите область абонентской группы (как описано выше в данном разделе).</span><span class="sxs-lookup"><span data-stu-id="82c5b-144">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="82c5b-145">Чтобы создать абонентскую абонентскую систему, укажите значения в следующих полях, как это необходимо, с помощью панели управления Lync Server или консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82c5b-145">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="82c5b-146">Имя и простое имя</span><span class="sxs-lookup"><span data-stu-id="82c5b-146">Name and Simple Name</span></span>

<span data-ttu-id="82c5b-p111">Для абонентских групп пользователей следует указать описательное имя, обозначающее пользователей, группы или контактные объекты, которым эта абонентская группа будет назначена. Для абонентских групп сайтов поле "Имя" предварительно заполняется именем сайта и не может быть изменено. Для абонентских групп пулов поле "Имя" предварительно заполняется полным доменным именем шлюза ТСОП или интерфейсного пула и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="82c5b-p111">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned. For site dial plans, the Name field is prepopulated with the site name and cannot be changed. For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="82c5b-p112">Абонентская группа *Простое имя* предварительно заполняется строкой, получаемой из имени абонентской группы. Поле "Простое имя" доступно для редактирования, что позволяет вам создать для абонентских групп более описательный контекст именования. Значение *Простое имя* не может быть пустым и должно быть уникальным. Рекомендуется разработать контекст именования для всей организации и последовательно использовать его для всех сайтов и пользователей.</span><span class="sxs-lookup"><span data-stu-id="82c5b-p112">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name. The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans. The *Simple Name* value cannot be empty and must be unique. A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="82c5b-154">Описание</span><span class="sxs-lookup"><span data-stu-id="82c5b-154">Description</span></span>

<span data-ttu-id="82c5b-p113">Рекомендуется вводить общеупотребительные узнаваемые имена географических расположений, к которым применяются соответствующие абонентские группы. Например, если имя абонентской группы — London.Contoso.com, рекомендуемым описанием будет "Лондон".</span><span class="sxs-lookup"><span data-stu-id="82c5b-p113">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies. For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="82c5b-157">Регион конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="82c5b-157">Dial-in Conferencing Region</span></span>

<span data-ttu-id="82c5b-158">Если выполняется развертывание конференц-связи с телефонным подключением, необходимо указать регион конференц-связи с телефонным подключением, чтобы связать соответствующие номера доступа с абонентской группой.</span><span class="sxs-lookup"><span data-stu-id="82c5b-158">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="82c5b-159">Префикса внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="82c5b-159">External Access Prefix</span></span>

<span data-ttu-id="82c5b-160">Можно указать префикс внешнего доступа длиной до четырех символов ( \# , \* и 0-9), если пользователям требуется набирать одну или несколько дополнительных начальных цифр (например, 9), чтобы получить внешнюю линию.</span><span class="sxs-lookup"><span data-stu-id="82c5b-160">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82c5b-161">Если указан префикс внешнего доступа, не требуется создавать дополнительное правило нормализации для обработки префикса.</span><span class="sxs-lookup"><span data-stu-id="82c5b-161">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="82c5b-162">Правила нормализации</span><span class="sxs-lookup"><span data-stu-id="82c5b-162">Normalization Rules</span></span>

<span data-ttu-id="82c5b-p114">Правила нормализации определяют, как номера телефонов, заданные в различных форматах, перенаправляются в заданное расположение. Одна и та же строка номера может интерпретироваться и преобразовываться по-разному, в зависимости от адреса, в котором она была набрана. Правила нормализации необходимы для маршрутизации вызовов, так как пользователи могут использовать и используют различные форматы при вводе номеров телефонов в своих списках контактов.</span><span class="sxs-lookup"><span data-stu-id="82c5b-p114">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="82c5b-166">Нормализация указанных пользователями номеров телефонов позволяет получить согласованный формат, облегчающий выполнение следующих задач:</span><span class="sxs-lookup"><span data-stu-id="82c5b-166">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="82c5b-167">Сравнение набранного номера с URI SIP требуемого получателя.</span><span class="sxs-lookup"><span data-stu-id="82c5b-167">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="82c5b-168">Применение правил авторизации набора номера к вызывающей стороне.</span><span class="sxs-lookup"><span data-stu-id="82c5b-168">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="82c5b-169">Следующие поля номера могут потребоваться правилу нормализации при обработке набираемого номера:</span><span class="sxs-lookup"><span data-stu-id="82c5b-169">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="82c5b-170">абонентская группа,</span><span class="sxs-lookup"><span data-stu-id="82c5b-170">Dial plan</span></span>

  - <span data-ttu-id="82c5b-171">код страны,</span><span class="sxs-lookup"><span data-stu-id="82c5b-171">Country code</span></span>

  - <span data-ttu-id="82c5b-172">код города,</span><span class="sxs-lookup"><span data-stu-id="82c5b-172">Area code</span></span>

  - <span data-ttu-id="82c5b-173">длина расширения,</span><span class="sxs-lookup"><span data-stu-id="82c5b-173">Length of extension</span></span>

  - <span data-ttu-id="82c5b-174">префикс сайта.</span><span class="sxs-lookup"><span data-stu-id="82c5b-174">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="82c5b-175">Создание правил нормализации</span><span class="sxs-lookup"><span data-stu-id="82c5b-175">Creating Normalization Rules</span></span>

<span data-ttu-id="82c5b-176">Правила нормализации используют регулярные выражения .NET Framework для указания шаблонов совпадения номеров, используемых сервером для преобразования строк набора номера в формат E.164 с целью выполнения обратного поиска номеров.</span><span class="sxs-lookup"><span data-stu-id="82c5b-176">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="82c5b-177">Правила нормализации создаются в панели управления Lync Server путем ввода выражений вручную или при вводе начальных цифр и длины строк набора номера, которые должны быть сопоставляемыми и позволяющие панели управления Lync Server создать соответствующее регулярное выражение.</span><span class="sxs-lookup"><span data-stu-id="82c5b-177">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="82c5b-178">В любом случае после завершения вы можете ввести тестовый номер, чтобы убедиться в правильной работе правил нормализации.</span><span class="sxs-lookup"><span data-stu-id="82c5b-178">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="82c5b-179">Более подробную информацию об использовании регулярных выражений .NET Framework можно узнать в разделе "регулярные выражения .NET Framework" [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="82c5b-179">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="82c5b-180">Примеры правил нормализации</span><span class="sxs-lookup"><span data-stu-id="82c5b-180">Sample Normalization Rules</span></span>

<span data-ttu-id="82c5b-p116">В следующей таблице приведены примеры правил нормализации, созданные как регулярные выражения .NET Framework. Они приводятся только для справки и не являются предписывающим эталоном для создания собственных правил нормализации.</span><span class="sxs-lookup"><span data-stu-id="82c5b-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="82c5b-183">Таблица 1. Правила нормализации на основе регулярных выражений .NET Framework</span><span class="sxs-lookup"><span data-stu-id="82c5b-183">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82c5b-184">Имя правила</span><span class="sxs-lookup"><span data-stu-id="82c5b-184">Rule name</span></span></th>
<th><span data-ttu-id="82c5b-185">Описание</span><span class="sxs-lookup"><span data-stu-id="82c5b-185">Description</span></span></th>
<th><span data-ttu-id="82c5b-186">Шаблон номера</span><span class="sxs-lookup"><span data-stu-id="82c5b-186">Number pattern</span></span></th>
<th><span data-ttu-id="82c5b-187">Translation</span><span class="sxs-lookup"><span data-stu-id="82c5b-187">Translation</span></span></th>
<th><span data-ttu-id="82c5b-188">Пример</span><span class="sxs-lookup"><span data-stu-id="82c5b-188">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82c5b-189">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="82c5b-189">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="82c5b-190">Преобразование 4-значных расширений</span><span class="sxs-lookup"><span data-stu-id="82c5b-190">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="82c5b-191">^ (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="82c5b-191">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="82c5b-192">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="82c5b-192">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="82c5b-193">0100 преобразуется в +14255550100</span><span class="sxs-lookup"><span data-stu-id="82c5b-193">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5b-194">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="82c5b-194">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="82c5b-195">Преобразование 5-значных расширений</span><span class="sxs-lookup"><span data-stu-id="82c5b-195">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="82c5b-196">^ 5 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="82c5b-196">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="82c5b-197">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="82c5b-197">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="82c5b-198">50100 преобразуется в +14255550100</span><span class="sxs-lookup"><span data-stu-id="82c5b-198">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5b-199">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="82c5b-199">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="82c5b-200">Преобразование 7-значных номеров в локальные номера Редмонда</span><span class="sxs-lookup"><span data-stu-id="82c5b-200">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="82c5b-201">^ (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="82c5b-201">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="82c5b-202">+ 1425 $1</span><span class="sxs-lookup"><span data-stu-id="82c5b-202">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="82c5b-203">5550100 преобразуется в +14255550100</span><span class="sxs-lookup"><span data-stu-id="82c5b-203">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5b-204">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="82c5b-204">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="82c5b-205">Преобразование 7-значных номеров в локальные номера Далласа</span><span class="sxs-lookup"><span data-stu-id="82c5b-205">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="82c5b-206">^ (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="82c5b-206">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="82c5b-207">+ 1972 $1</span><span class="sxs-lookup"><span data-stu-id="82c5b-207">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="82c5b-208">5550100 преобразуется в +19725550100</span><span class="sxs-lookup"><span data-stu-id="82c5b-208">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5b-209">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="82c5b-209">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="82c5b-210">Преобразование 10-значных номеров в номера США</span><span class="sxs-lookup"><span data-stu-id="82c5b-210">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="82c5b-211">^ (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="82c5b-211">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="82c5b-212">+ 1 $1</span><span class="sxs-lookup"><span data-stu-id="82c5b-212">+1$1</span></span></p></td>
<td><p><span data-ttu-id="82c5b-213">2065550100 преобразуется в +12065550100</span><span class="sxs-lookup"><span data-stu-id="82c5b-213">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5b-214">лдкаллингус</span><span class="sxs-lookup"><span data-stu-id="82c5b-214">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="82c5b-215">Преобразование номеров с междугородными префиксами в номера США</span><span class="sxs-lookup"><span data-stu-id="82c5b-215">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="82c5b-216">^ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="82c5b-216">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="82c5b-217">+ $1</span><span class="sxs-lookup"><span data-stu-id="82c5b-217">+$1</span></span></p></td>
<td><p><span data-ttu-id="82c5b-218">12145550100 преобразуется в +2145550100</span><span class="sxs-lookup"><span data-stu-id="82c5b-218">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5b-219">интлкаллингус</span><span class="sxs-lookup"><span data-stu-id="82c5b-219">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="82c5b-220">Преобразование номеров с международными префиксами в номера США</span><span class="sxs-lookup"><span data-stu-id="82c5b-220">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="82c5b-221">^ 011 (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="82c5b-221">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="82c5b-222">+ $1</span><span class="sxs-lookup"><span data-stu-id="82c5b-222">+$1</span></span></p></td>
<td><p><span data-ttu-id="82c5b-223">01191445550100 преобразуется в +91445550100</span><span class="sxs-lookup"><span data-stu-id="82c5b-223">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5b-224">редмондоператор</span><span class="sxs-lookup"><span data-stu-id="82c5b-224">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="82c5b-225">Преобразование 0 в оператора Редмонда</span><span class="sxs-lookup"><span data-stu-id="82c5b-225">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="82c5b-226">^ $0</span><span class="sxs-lookup"><span data-stu-id="82c5b-226">^0$</span></span></p></td>
<td><p><span data-ttu-id="82c5b-227">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="82c5b-227">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="82c5b-228">0 преобразуется в +14255550100</span><span class="sxs-lookup"><span data-stu-id="82c5b-228">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5b-229">редмондситепрефикс</span><span class="sxs-lookup"><span data-stu-id="82c5b-229">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="82c5b-230">Преобразование номеров с сетевым префиксом (6) и кодами сайта Редмонда (222)</span><span class="sxs-lookup"><span data-stu-id="82c5b-230">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="82c5b-231">^ 6222 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="82c5b-231">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="82c5b-232">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="82c5b-232">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="82c5b-233">62220100 преобразуется в +14255550100</span><span class="sxs-lookup"><span data-stu-id="82c5b-233">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5b-234">ниситепрефикс</span><span class="sxs-lookup"><span data-stu-id="82c5b-234">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="82c5b-235">Преобразование номеров с сетевым префиксом (6) и кодами сайта Нью-Йорка (333)</span><span class="sxs-lookup"><span data-stu-id="82c5b-235">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="82c5b-236">^ 6333 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="82c5b-236">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="82c5b-237">+ 1202555 $1</span><span class="sxs-lookup"><span data-stu-id="82c5b-237">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="82c5b-238">63330100 преобразуется в +12025550100</span><span class="sxs-lookup"><span data-stu-id="82c5b-238">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5b-239">далласситепрефикс</span><span class="sxs-lookup"><span data-stu-id="82c5b-239">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="82c5b-240">Преобразование номеров с сетевым префиксом (6) и кодами сайта Далласа (444)</span><span class="sxs-lookup"><span data-stu-id="82c5b-240">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="82c5b-241">^ 6444 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="82c5b-241">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="82c5b-242">+ 1972555 $1</span><span class="sxs-lookup"><span data-stu-id="82c5b-242">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="82c5b-243">64440100 преобразуется в +19725550100</span><span class="sxs-lookup"><span data-stu-id="82c5b-243">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82c5b-244">В следующей таблице приводится пример абонентской группы для сайта Редмонда (шт. Вашингтон, США) на основе правил нормализации, приведенных в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="82c5b-244">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="82c5b-p117">Таблица 2. Абонентская группа Редмонда, основанная на правилах нормализации из таблицы 1</span><span class="sxs-lookup"><span data-stu-id="82c5b-p117">Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82c5b-247">Redmond. Форестфкдн</span><span class="sxs-lookup"><span data-stu-id="82c5b-247">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82c5b-248">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="82c5b-248">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5b-249">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="82c5b-249">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5b-250">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="82c5b-250">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5b-251">интлкаллингус</span><span class="sxs-lookup"><span data-stu-id="82c5b-251">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5b-252">редмондситепрефикс</span><span class="sxs-lookup"><span data-stu-id="82c5b-252">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5b-253">ниситепрефикс</span><span class="sxs-lookup"><span data-stu-id="82c5b-253">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82c5b-254">далласситепрефикс</span><span class="sxs-lookup"><span data-stu-id="82c5b-254">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82c5b-255">редмондоператор</span><span class="sxs-lookup"><span data-stu-id="82c5b-255">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="82c5b-p118">Имена правил нормализации, приведенные в предыдущей таблице, не включают пробелы, но это не является обязательным требованием. Например, первое имя в таблице можно записать как "5 значное расширение" или "5-значное расширение", и оно будет допустимым.</span><span class="sxs-lookup"><span data-stu-id="82c5b-p118">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

