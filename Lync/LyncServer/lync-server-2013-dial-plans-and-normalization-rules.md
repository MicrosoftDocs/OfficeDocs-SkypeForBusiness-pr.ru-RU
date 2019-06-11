---
title: 'Lync Server 2013: абонентские группы и правила нормализации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d399c49db109a7bac1a1cd3ac430280cb70f665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="fa0e3-102">Абонентские группы и правила нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa0e3-102">Dial plans and normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa0e3-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="fa0e3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="fa0e3-104">Абонентская группа — это именованный набор правил нормализации, которые преобразуют номера телефонов для именованного расположения, отдельного пользователя или контактного объекта в единый стандартный формат (E.164) для авторизации телефонов и маршрутизации вызовов.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-104">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="fa0e3-p101">Правила нормализации определяют, как номера телефонов, заданные в различных форматах, перенаправляются в требуемое расположение, требуемому пользователю или контактному объекту. Одна и та же строка набора номера может интерпретироваться и преобразовываться по-разному в зависимости от расположения, в котором она была набрана, и лица или контактного объекта, разместившего вызов.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-p101">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="fa0e3-107">Область абонентской группы</span><span class="sxs-lookup"><span data-stu-id="fa0e3-107">Dial Plan Scope</span></span>

<span data-ttu-id="fa0e3-108">*Область действия* абонентской группы определяет уровень иерархии, на котором эта группа может применяться.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-108">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="fa0e3-109">В Lync Server пользователю может быть назначена определенная абонентская группа для пользователей.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-109">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="fa0e3-110">Если абонентская группа не назначена, будет применена абонентская группа для пула регистраторов.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-110">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="fa0e3-111">Если абонентская группа из пула регистраторов не существует, будет применена абонентская группа сайта.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-111">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="fa0e3-112">Наконец, если к пользователя не применимы никакие другие абонентские группы, применяется глобальная абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-112">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="fa0e3-113">Клиенты получают доступ к уровням области для абонентской группы с помощью параметров подготовки по частоте, которые предоставляются при входе пользователей на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-113">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="fa0e3-114">Администратор может управлять и назначать уровни области абонентской группы с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-114">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa0e3-115">Абонентская группа шлюза телефонной сети общего пользования (ТСОП) уровня служб применяется к входящим звонкам с конкретного шлюза.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-115">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="fa0e3-116">Уровни области абонентской группы определяются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-116">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="fa0e3-117">**Абонентская группа:** Может назначаться отдельным пользователям, группам или объектам контактов.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-117">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="fa0e3-118">Голосовые приложения могут запрашивать абонентскую группу на уровне пользователей в случае получения звонка, для которого установлено пользовательское значение по умолчанию телефонного контекста.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-118">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="fa0e3-119">В рамках назначения абонентской группы контактный объект считается отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-119">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="fa0e3-120">Абонентская группа для **пула:** Можно создать на уровне обслуживания для любого шлюза или регистратора PSTN в вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-120">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="fa0e3-121">Для определения абонентской группы пула необходимо указать конкретную службу (шлюз ТСОП или пул регистратора), к которой применяется абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-121">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="fa0e3-122">**Абонентская группа для сайта:** Может создаваться для всего сайта, за исключением пользователей, групп или контактов, которым назначена абонентская группа или абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-122">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="fa0e3-123">Чтобы определить абонентскую группу, следует указать сайт, к которому она применяется.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-123">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="fa0e3-124">**Глобальная абонентская группа:** Абонентская группа по умолчанию, установленная вместе с продуктом.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-124">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="fa0e3-125">Вы можете изменить глобальную абонентскую группу, но не можете удалить ее.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-125">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="fa0e3-126">Эта абонентская группа применима ко всем пользователям, группам и контактам, находящимся в развертывании, если только вы не настраиваете и не назначаете абонентскую группу с более определенной областью действия.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-126">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="fa0e3-127">Планирование абонентских групп</span><span class="sxs-lookup"><span data-stu-id="fa0e3-127">Planning for Dial Plans</span></span>

<span data-ttu-id="fa0e3-128">Для планирования абонентской группы выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-128">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="fa0e3-129">Укажите все адреса, по которым у вашей организации есть офис.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-129">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="fa0e3-p108">Этот список должен быть полным и актуальным. По мере роста и развития организации его следует пересматривать. В большой международной компании с большим количеством небольших филиалов эта задача может потребовать довольно много времени.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-p108">The list must be up-to-date and complete. It will need to be revised as company organization evolves. In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="fa0e3-133">Укажите допустимые шаблоны номеров для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-133">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="fa0e3-p109">Наиболее трудоемкой частью планирования абонентские группы является определение допустимых шаблонов номеров для каждого сайта. В некоторых случаях, возможно, получится скопировать правила нормализации, созданные для одной абонентской группы, в другие группы (особенно если соответствующие сайты находятся в пределах той же страны или региона или даже континента). В других случаях внесение небольших изменений в номера одной абонентской группы может быть достаточным для их использования в других абонентских группах.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-p109">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site. In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent. In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="fa0e3-137">Разработайте схему для именования абонентских групп в рамках всей организации.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-137">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="fa0e3-138">Принятие стандартной схемы именования гарантирует согласованность данных в пределах организации и упрощает решение задач обслуживания и обновления.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-138">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="fa0e3-139">Решите, требуется ли использовать несколько абонентских групп для одного расположения.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-139">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="fa0e3-140">Если ваша организация поддерживает одну абонентскую группу для нескольких местоположений, вам по-прежнему потребуется создать отдельную абонентскую группу для пользователей голосовой связи, которые переходят с УАТС (Private Branch Exchange) и которые должны поддерживаться существующими расширениями.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-140">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="fa0e3-141">Решите, требуются ли абонентские группы для индивидуальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-141">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="fa0e3-142">Например, если у вас есть пользователи на сайте филиала, которые зарегистрированы на центральном сайте или если у вас есть пользователи, зарегистрированные для работающего устройства филиала, вы можете использовать специальные сценарии набора номера для пользователей, использующих абонентские планы и правила нормализации. .</span><span class="sxs-lookup"><span data-stu-id="fa0e3-142">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="fa0e3-143">Дополнительные сведения можно найти в разделе [требования к устойчивости сайтов филиалов для Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa0e3-143">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="fa0e3-144">Определите область абонентской группы (как описано выше в данном разделе).</span><span class="sxs-lookup"><span data-stu-id="fa0e3-144">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="fa0e3-145">Чтобы создать абонентскую группу, заполните указанные ниже поля в соответствии с требованиями, используя панель управления Lync Server или консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-145">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="fa0e3-146">Имя и простое имя</span><span class="sxs-lookup"><span data-stu-id="fa0e3-146">Name and Simple Name</span></span>

<span data-ttu-id="fa0e3-147">Для абонентских групп пользователей следует указать информативное имя, указывающее пользователей, группы или контактные объекты, которым будет назначена данная абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-147">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="fa0e3-148">Для абонентских планов поле "имя" предварительно заполнено именем сайта и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-148">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="fa0e3-149">Для абонентов из пула в поле Name (имя) добавляется только полное доменное имя шлюза PSTN или интерфейс полного домена (FQDN) и его невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-149">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="fa0e3-150">*Простое имя* абонентской группы предзаполнено строкой, которая является производной от названия абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-150">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="fa0e3-151">Поле "Простое имя" доступно для редактирования, что позволяет создать для абонентских групп информативное соглашение об именовании.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-151">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="fa0e3-152">Поле *Простое имя* должно быть заполненным и содержать неповторяющееся значение.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-152">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="fa0e3-153">Рекомендуется разработать соглашение об именовании для всей организации и последовательно применять его для всех сайтов и пользователей.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-153">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="fa0e3-154">Описание</span><span class="sxs-lookup"><span data-stu-id="fa0e3-154">Description</span></span>

<span data-ttu-id="fa0e3-p113">Рекомендуется вводить общеупотребительные узнаваемые имена географических расположений, к которым применяются соответствующие абонентские группы. Например, если имя абонентской группы — London.Contoso.com, рекомендуемым описанием будет "Лондон".</span><span class="sxs-lookup"><span data-stu-id="fa0e3-p113">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies. For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="fa0e3-157">Регион конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="fa0e3-157">Dial-in Conferencing Region</span></span>

<span data-ttu-id="fa0e3-158">Если выполняется развертывание конференц-связи с телефонным подключением, необходимо указать регион конференц-связи с телефонным подключением, чтобы связать соответствующие номера доступа с абонентской группой.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-158">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="fa0e3-159">Префикс внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="fa0e3-159">External Access Prefix</span></span>

<span data-ttu-id="fa0e3-160">Вы можете указать префикс внешнего доступа длиной до 4 символов (\# \*и 0-9), если пользователям необходимо набирать одну или несколько начальных цифр (например, 9) для получения внешней линии.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-160">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa0e3-161">Если указан префикс внешнего доступа, не требуется создавать дополнительное правило нормализации для обработки префикса.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-161">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="fa0e3-162">Правила нормализации</span><span class="sxs-lookup"><span data-stu-id="fa0e3-162">Normalization Rules</span></span>

<span data-ttu-id="fa0e3-p114">Правила нормализации определяют, как номера телефонов, заданные в различных форматах, перенаправляются в заданное расположение. Одна и та же строка номера может интерпретироваться и преобразовываться по-разному в зависимости от адреса, в котором она была набрана. Правила нормализации необходимы для маршрутизации вызовов, так как пользователи могут использовать и используют различные форматы при вводе номеров телефонов в своих списках контактов.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-p114">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="fa0e3-166">Нормализация указанных пользователями номеров телефонов позволяет получить согласованный формат, облегчающий выполнение следующих задач.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-166">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="fa0e3-167">Сравнение набранного номера с URI SIP требуемого получателя.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-167">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="fa0e3-168">Применение правил авторизации набора номера к вызывающей стороне.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-168">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="fa0e3-169">Следующие поля номера могут потребоваться правилу нормализации при обработке набираемого номера.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-169">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="fa0e3-170">Абонентская группа</span><span class="sxs-lookup"><span data-stu-id="fa0e3-170">Dial plan</span></span>

  - <span data-ttu-id="fa0e3-171">Код страны</span><span class="sxs-lookup"><span data-stu-id="fa0e3-171">Country code</span></span>

  - <span data-ttu-id="fa0e3-172">Код города</span><span class="sxs-lookup"><span data-stu-id="fa0e3-172">Area code</span></span>

  - <span data-ttu-id="fa0e3-173">Длина расширения</span><span class="sxs-lookup"><span data-stu-id="fa0e3-173">Length of extension</span></span>

  - <span data-ttu-id="fa0e3-174">Префикс сайта</span><span class="sxs-lookup"><span data-stu-id="fa0e3-174">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="fa0e3-175">Создание правил нормализации</span><span class="sxs-lookup"><span data-stu-id="fa0e3-175">Creating Normalization Rules</span></span>

<span data-ttu-id="fa0e3-176">Правила нормализации используют регулярные выражения .NET Framework для указания шаблонов совпадения номеров, используемых сервером для преобразования строк набора номера в формат E.164 с целью выполнения обратного поиска номеров.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-176">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="fa0e3-177">Вы можете создать правила нормализации на панели управления Lync Server, введя выражения вручную или вводя начальные и конечные цифры и длину строк набора номера, чтобы обеспечить соответствие регулярное выражение.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-177">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="fa0e3-178">В любом случае после завершения вы можете ввести тестовый номер, чтобы убедиться в правильной работе правил нормализации.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-178">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="fa0e3-179">Подробнее об использовании регулярных выражений .NET Framework можно узнать в [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)разделе "регулярные выражения .NET Framework".</span><span class="sxs-lookup"><span data-stu-id="fa0e3-179">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="fa0e3-180">Примеры правил нормализации</span><span class="sxs-lookup"><span data-stu-id="fa0e3-180">Sample Normalization Rules</span></span>

<span data-ttu-id="fa0e3-p116">В следующей таблице приведены примеры правил нормализации, созданные как регулярные выражения .NET Framework. Они приводятся только для справки и не являются предписывающим эталоном для создания собственных правил нормализации.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="fa0e3-183">Таблица 1. Правила нормализации на основе регулярных выражений .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fa0e3-183">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

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
<th><span data-ttu-id="fa0e3-184">Имя правила</span><span class="sxs-lookup"><span data-stu-id="fa0e3-184">Rule name</span></span></th>
<th><span data-ttu-id="fa0e3-185">Описание</span><span class="sxs-lookup"><span data-stu-id="fa0e3-185">Description</span></span></th>
<th><span data-ttu-id="fa0e3-186">Шаблон номера</span><span class="sxs-lookup"><span data-stu-id="fa0e3-186">Number pattern</span></span></th>
<th><span data-ttu-id="fa0e3-187">Преобразование</span><span class="sxs-lookup"><span data-stu-id="fa0e3-187">Translation</span></span></th>
<th><span data-ttu-id="fa0e3-188">Пример</span><span class="sxs-lookup"><span data-stu-id="fa0e3-188">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa0e3-189">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="fa0e3-189">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-190">Преобразование 4-значных расширений</span><span class="sxs-lookup"><span data-stu-id="fa0e3-190">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-191">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="fa0e3-191">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-192">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="fa0e3-192">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-193">0100 преобразуется в +14255550100</span><span class="sxs-lookup"><span data-stu-id="fa0e3-193">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0e3-194">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="fa0e3-194">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-195">Преобразование 5-значных расширений</span><span class="sxs-lookup"><span data-stu-id="fa0e3-195">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-196">^ 5 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="fa0e3-196">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-197">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="fa0e3-197">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-198">50100 преобразуется в +14255550100</span><span class="sxs-lookup"><span data-stu-id="fa0e3-198">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0e3-199">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="fa0e3-199">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-200">Преобразование 7-значных номеров в локальные номера Редмонда</span><span class="sxs-lookup"><span data-stu-id="fa0e3-200">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-201">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="fa0e3-201">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-202">+1425$1</span><span class="sxs-lookup"><span data-stu-id="fa0e3-202">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-203">5550100 преобразуется в +14255550100</span><span class="sxs-lookup"><span data-stu-id="fa0e3-203">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0e3-204">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="fa0e3-204">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-205">Преобразование 7-значных номеров в локальные номера Далласа</span><span class="sxs-lookup"><span data-stu-id="fa0e3-205">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-206">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="fa0e3-206">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-207">+1972$1</span><span class="sxs-lookup"><span data-stu-id="fa0e3-207">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-208">5550100 преобразуется в +19725550100</span><span class="sxs-lookup"><span data-stu-id="fa0e3-208">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0e3-209">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="fa0e3-209">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-210">Преобразование 10-значных номеров в номера США</span><span class="sxs-lookup"><span data-stu-id="fa0e3-210">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-211">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="fa0e3-211">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-212">+1$1</span><span class="sxs-lookup"><span data-stu-id="fa0e3-212">+1$1</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-213">2065550100 преобразуется в +12065550100</span><span class="sxs-lookup"><span data-stu-id="fa0e3-213">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0e3-214">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="fa0e3-214">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-215">Преобразование номеров с междугородными префиксами в номера США</span><span class="sxs-lookup"><span data-stu-id="fa0e3-215">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-216">^ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="fa0e3-216">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-217">+$1</span><span class="sxs-lookup"><span data-stu-id="fa0e3-217">+$1</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-218">12145550100 преобразуется в +2145550100</span><span class="sxs-lookup"><span data-stu-id="fa0e3-218">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0e3-219">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="fa0e3-219">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-220">Преобразование номеров с международными префиксами в номера США</span><span class="sxs-lookup"><span data-stu-id="fa0e3-220">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-221">^011(\d\*)$</span><span class="sxs-lookup"><span data-stu-id="fa0e3-221">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-222">+$1</span><span class="sxs-lookup"><span data-stu-id="fa0e3-222">+$1</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-223">01191445550100 преобразуется в +91445550100</span><span class="sxs-lookup"><span data-stu-id="fa0e3-223">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0e3-224">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="fa0e3-224">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-225">Преобразование 0 в оператора Редмонда</span><span class="sxs-lookup"><span data-stu-id="fa0e3-225">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-226">^0$</span><span class="sxs-lookup"><span data-stu-id="fa0e3-226">^0$</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-227">+14255550100</span><span class="sxs-lookup"><span data-stu-id="fa0e3-227">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-228">0 преобразуется в +14255550100</span><span class="sxs-lookup"><span data-stu-id="fa0e3-228">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0e3-229">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="fa0e3-229">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-230">Преобразование номеров с сетевым префиксом (6) и кодами сайта Редмонда (222)</span><span class="sxs-lookup"><span data-stu-id="fa0e3-230">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-231">^ 6222 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="fa0e3-231">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-232">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="fa0e3-232">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-233">62220100 преобразуется в +14255550100</span><span class="sxs-lookup"><span data-stu-id="fa0e3-233">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0e3-234">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="fa0e3-234">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-235">Преобразование номеров с сетевым префиксом (6) и кодами сайта Нью-Йорка (333)</span><span class="sxs-lookup"><span data-stu-id="fa0e3-235">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-236">^ 6333 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="fa0e3-236">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-237">+1202555$1</span><span class="sxs-lookup"><span data-stu-id="fa0e3-237">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-238">63330100 преобразуется в +12025550100</span><span class="sxs-lookup"><span data-stu-id="fa0e3-238">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0e3-239">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="fa0e3-239">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-240">Преобразование номеров с сетевым префиксом (6) и кодами сайта Далласа (444)</span><span class="sxs-lookup"><span data-stu-id="fa0e3-240">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-241">^ 6444 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="fa0e3-241">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-242">+1972555$1</span><span class="sxs-lookup"><span data-stu-id="fa0e3-242">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="fa0e3-243">64440100 преобразуется в +19725550100</span><span class="sxs-lookup"><span data-stu-id="fa0e3-243">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fa0e3-244">В следующей таблице приводится пример абонентской группы для сайта Редмонда (шт. Вашингтон, США) на основе правил нормализации, приведенных в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="fa0e3-244">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="fa0e3-p117">Таблица 2. Абонентская группа Редмонда, основанная на правилах нормализации из таблицы 1</span><span class="sxs-lookup"><span data-stu-id="fa0e3-p117">Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa0e3-247">Redmond.forestFQDN</span><span class="sxs-lookup"><span data-stu-id="fa0e3-247">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa0e3-248">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="fa0e3-248">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0e3-249">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="fa0e3-249">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0e3-250">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="fa0e3-250">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0e3-251">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="fa0e3-251">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0e3-252">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="fa0e3-252">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0e3-253">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="fa0e3-253">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0e3-254">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="fa0e3-254">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0e3-255">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="fa0e3-255">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fa0e3-p118">Названия правил нормализации из предыдущей таблицы не содержат пробелов, но вы можете использовать пробелы в названиях своих правил. Например, первое правило в таблице могло называться 5 digit extension или 5-digit Extension (добавочный номер из 5 цифр).</span><span class="sxs-lookup"><span data-stu-id="fa0e3-p118">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

