---
title: "Использование Microsoft Teams параллельно со Skype для бизнеса"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Руководство по параллельному использованию Skype для бизнеса и Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 760fa47db7965e0c2a74b01ae25f1d23d37d3180
ms.sourcegitcommit: 2592b268977460d0d483a75d741b1ce9fa8da908
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2017
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a><span data-ttu-id="009f7-103">Использование Microsoft Teams параллельно со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="009f7-103">Enable Microsoft Teams side-by-side with Skype for Business</span></span> 
=============================================================

<span data-ttu-id="009f7-104">Недавнее появление Microsoft Teams предоставило организациям с существующими развертываниями Skype для бизнеса Online возможность определить потенциал Teams в качестве отдельного решения для взаимодействия и совместной работы, а также сравнить эти два решения и оценить их сосуществование в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="009f7-104">For organizations with existing deployments of Skype for Business Online, the recent introduction of Microsoft Teams presents an opportunity to evaluate the potential of Teams as a sole, communications and collaboration solution, and a challenge to tip the scale between the two solutions and how they can coexist in your environment.</span></span>

<span data-ttu-id="009f7-105">Если Teams удовлетворяет вашим актуальным бизнес-требованиям, вы можете начать внедрение Teams в качестве единого решения для взаимодействия и совместной работы в организации.</span><span class="sxs-lookup"><span data-stu-id="009f7-105">If Teams can meet your business requirements today, you can start adopting Teams to become your single communications and collaboration solution for your organization.</span></span>

<span data-ttu-id="009f7-106">Продукт Teams по умолчанию активен для всех соответствующих клиентов.</span><span class="sxs-lookup"><span data-stu-id="009f7-106">Teams is enabled by default, on all eligible tenants.</span></span> <span data-ttu-id="009f7-107">Поэтому вам следует решить, как управлять Teams параллельно со Skype для бизнеса так, чтобы оправдать ожидания пользователей.</span><span class="sxs-lookup"><span data-stu-id="009f7-107">Therefore, you need to decide on how to manage Teams side-by-side with Skype for Business, and continue to meet user expectations.</span></span>

<span data-ttu-id="009f7-108">В общем случае доступны два основных цикла взаимодействия с клиентом при параллельном размещении.</span><span class="sxs-lookup"><span data-stu-id="009f7-108">In general, there are two major side-by-side customer journeys.</span></span> <span data-ttu-id="009f7-109">Они описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="009f7-109">They are:</span></span>

-   <span data-ttu-id="009f7-110">**Вариант 1:** неуправляемый цикл взаимодействия с клиентом при параллельном размещении.</span><span class="sxs-lookup"><span data-stu-id="009f7-110">**Option 1:** Unmanaged side-by-side customer journey.</span></span>

    <span data-ttu-id="009f7-111">ИТ-отдел не осуществляет активный контроль параллельного размещения, а пользователи могут выбрать предпочитаемое приложение.</span><span class="sxs-lookup"><span data-stu-id="009f7-111">IT does not actively control the side-by-side experience, and users are empowered to make the choice of preferred app.</span></span>

-   <span data-ttu-id="009f7-112">**Вариант 2:** управляемый цикл взаимодействия с клиентом при параллельном размещении.</span><span class="sxs-lookup"><span data-stu-id="009f7-112">**Option 2:** Managed side-by-side customer journey.</span></span>

    <span data-ttu-id="009f7-113">ИТ-отдел контролирует параллельное размещение и обеспечивает постепенное освоение Teams пользователями — сначала новой основанной на чате рабочей области для совместной работы, поддерживающей приватный чат, затем работу с собраниями и, наконец, интерфейс звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="009f7-113">IT controls the side-by-side experience, taking users through a journey of gradually introducing Teams to first introduce a new chat-based collaboration workspace with private chat, then meeting experiences, and finally the calling experiences in Teams.</span></span>

![](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a><span data-ttu-id="009f7-114">Преимущества и особенности, связанные с параллельным размещением</span><span class="sxs-lookup"><span data-stu-id="009f7-114">Side-by-side benefits and considerations</span></span>
----------------------------------------

<span data-ttu-id="009f7-115">Определяя вектор дальнейшего развития с учетом профиля организации, следует учитывать различные преимущества и особенности, связанные с конкретным циклом взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="009f7-115">Each journey has benefits and considerations to evaluate when determining the right path forward based on your organization's profile.</span></span> <span data-ttu-id="009f7-116">В следующей таблице сравниваются управляемый и неуправляемый циклы взаимодействия с клиентом при параллельном размещении.</span><span class="sxs-lookup"><span data-stu-id="009f7-116">The table below provides the comparisons between managed and unmanaged side-by-side customer journeys.</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="009f7-117">Пути миграции</span><span class="sxs-lookup"><span data-stu-id="009f7-117">Migration Paths</span></span></th>
<th align="left"><span data-ttu-id="009f7-118">Неуправляемое параллельное размещение</span><span class="sxs-lookup"><span data-stu-id="009f7-118">Unmanaged Side-by-Side</span></span></th>
<th align="left"><span data-ttu-id="009f7-119">Управляемое параллельное размещение</span><span class="sxs-lookup"><span data-stu-id="009f7-119">Managed Side-by-Side</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="009f7-120"><strong>Профиль организации</strong></span><span class="sxs-lookup"><span data-stu-id="009f7-120"><strong>Organization profile</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="009f7-121">Обычно это небольшие организации без выделенных ИТ-ресурсов</span><span class="sxs-lookup"><span data-stu-id="009f7-121">Typically, smaller organizations with no dedicated IT resources</span></span></li>
<li><span data-ttu-id="009f7-122">ИТ-служба позволяет пользователям самостоятельно выбирать подходящие средства для выполнения работы</span><span class="sxs-lookup"><span data-stu-id="009f7-122">IT allows user discretion in selecting right tools for their work</span></span></li>
<li><span data-ttu-id="009f7-123">Skype для бизнеса используется в основном для обмена мгновенными сообщениями, определения присутствия и собраний</span><span class="sxs-lookup"><span data-stu-id="009f7-123">Primary Skype for Business usage is IM/P and meetings</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="009f7-124">Обычно это организации среднего или крупного размера</span><span class="sxs-lookup"><span data-stu-id="009f7-124">Typically, mid-size to larger organizations</span></span></li>
<li><span data-ttu-id="009f7-125">ИТ-служба стремится более тщательно контролировать развертывание новых средств</span><span class="sxs-lookup"><span data-stu-id="009f7-125">IT wants to control roll out of new tools more rigorously</span></span></li>
<li><span data-ttu-id="009f7-126">Более глубокое внедрение Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="009f7-126">Deeper adoption of Skype for Business today</span></span></li>
<li><span data-ttu-id="009f7-127">Повышенная сложность сети и инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="009f7-127">Increased complexity in network and infrastructure</span></span></li>
<li><span data-ttu-id="009f7-128">Несколько расположений</span><span class="sxs-lookup"><span data-stu-id="009f7-128">Multiple locations</span></span></p>
<li><span data-ttu-id="009f7-129">Предпочтение отдается одному приложению с уникальными функциями объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="009f7-129">Preference for single app with unique UC capabilities</span></span></li></ul></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="009f7-130"><strong>Преимущества</strong></span><span class="sxs-lookup"><span data-stu-id="009f7-130"><strong>Benefits</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="009f7-131">Использование тех возможностей Teams, которые недоступны в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="009f7-131">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="009f7-132">Улучшенная современная рабочая область на базе Office 365</span><span class="sxs-lookup"><span data-stu-id="009f7-132">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="009f7-133">Повышенная гибкость работы для пользователей</span><span class="sxs-lookup"><span data-stu-id="009f7-133">Increased user flexibility</span></span></li>
<li><span data-ttu-id="009f7-134">Доступ сразу ко всем возможностям</span><span class="sxs-lookup"><span data-stu-id="009f7-134">Enable all capabilities at once</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="009f7-135">Использование тех возможностей Teams, которые недоступны в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="009f7-135">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="009f7-136">Улучшенная современная рабочая область на базе Office 365</span><span class="sxs-lookup"><span data-stu-id="009f7-136">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="009f7-137">Минимизация негативного влияния на производительность пользователей</span><span class="sxs-lookup"><span data-stu-id="009f7-137">Minimize user productivity impact</span></span></li>
<li><span data-ttu-id="009f7-138">Уменьшение перекрытия возможностей</span><span class="sxs-lookup"><span data-stu-id="009f7-138">Reduce capability overlap</span></span></li>
<li><span data-ttu-id="009f7-139">Упрощение выбора средства для сценариев объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="009f7-139">Streamline tool choice for UC scenarios</span></span></li>
<li><span data-ttu-id="009f7-140">Возможность активации нужных организации ИТ- и бизнес-возможностей</span><span class="sxs-lookup"><span data-stu-id="009f7-140">Empower IT and business to enable capabilities as appropriate in organization</span></span></li>
<li><span data-ttu-id="009f7-141">Управление темпом перемен для пользователей</span><span class="sxs-lookup"><span data-stu-id="009f7-141">Control the pace of change for users</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="009f7-142"><strong>Особенности</strong></span><span class="sxs-lookup"><span data-stu-id="009f7-142"><strong>Considerations</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="009f7-143">Несколько приложений с перекрывающимися возможностями</span><span class="sxs-lookup"><span data-stu-id="009f7-143">Multiple apps with similar, overlapping capabilities</span></span></li>
<li><span data-ttu-id="009f7-144">Выше вероятность путаницы на стороне пользователя, что может привести к более частым обращениям в службу поддержки, использованию теневых ИТ и снижению производительности</span><span class="sxs-lookup"><span data-stu-id="009f7-144">Increased potential for user confusion which can lead to increased support calls, shadow IT, impacted productivity</span></span></li>
<li><span data-ttu-id="009f7-145">При планировании и мониторинге сети требуется принимать во внимание две службы</span><span class="sxs-lookup"><span data-stu-id="009f7-145">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="009f7-146">Требуются дополнительные и немедленные меры по управлению изменениями: информирование, обучение и поддержка</span><span class="sxs-lookup"><span data-stu-id="009f7-146">Increased and immediate change management efforts required: awareness, training, and support</span></span></li>
<li><span data-ttu-id="009f7-147">Пользователи могут сталкиваться с ограничениями взаимодействия между приложениями</span><span class="sxs-lookup"><span data-stu-id="009f7-147">Users may experience interoperability limitations between apps</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="009f7-148">ИТ-служба обладает более детализированными возможностями управления, от лицензирования до взаимодействия с пользователями, что требует дополнительных циклов планирования и внедрения</span><span class="sxs-lookup"><span data-stu-id="009f7-148">IT has granular control, from licensing to user experiences, requiring additional cycles of planning and implementation</span></span></li>
<li><span data-ttu-id="009f7-149">Для отключения отдельных возможностей в Teams требуется обучение пользователей и принятие специальных мер</span><span class="sxs-lookup"><span data-stu-id="009f7-149">User education and action required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="009f7-150">Для отключения отдельных возможностей в Teams требуются меры по управлению изменениями</span><span class="sxs-lookup"><span data-stu-id="009f7-150">Change management efforts required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="009f7-151">При планировании и мониторинге сети требуется принимать во внимание две службы</span><span class="sxs-lookup"><span data-stu-id="009f7-151">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="009f7-152">Пользователи могут сталкиваться с ограничениями взаимодействия между приложениями</span><span class="sxs-lookup"><span data-stu-id="009f7-152">Users may experience interoperability limitations between apps</span></span></li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a><span data-ttu-id="009f7-153">Неуправляемый цикл взаимодействия с клиентом при параллельном размещении</span><span class="sxs-lookup"><span data-stu-id="009f7-153">Unmanaged side-by-side customer journey</span></span>
---------------------------------------


![](media/guidance_SkypeforBusiness_image4.png)

<span data-ttu-id="009f7-154">В рамках неуправляемого цикла взаимодействия с клиентом при параллельном размещении продукт Teams позиционируется в качестве решения для совместной работы (рабочая область на основе чата, каналы, приложения, интеграция с другими рабочими нагрузками Office 365 и т. д.), включающего в себя клиентское программное обеспечение и веб-клиент на настольных компьютерах (ПК или Mac) и мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="009f7-154">In an unmanaged side-by-side customer journey, Teams is introduced as a collaboration solution (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.) that involves client software and web client on desktop computers (PC or Mac) and mobile devices.</span></span>


<span data-ttu-id="009f7-155">По умолчанию Teams также предоставляет возможности, перекрывающиеся со Skype для бизнеса, включая приватный чат, звонки и запланированные собрания.</span><span class="sxs-lookup"><span data-stu-id="009f7-155">By default, Teams also presents overlapping capabilities with Skype for Business, these include private chat and calling, and scheduled meetings.</span></span> <span data-ttu-id="009f7-156">Таким образом, Teams предоставляет организации полный спектр возможностей для взаимодействия и совместной работы, при этом схожей функциональностью обладает и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="009f7-156">This means Teams ends up providing complete communications and collaboration for the organization, while at the same time Skype for Business provides similar capabilities.</span></span>

<span data-ttu-id="009f7-157">Teams поддерживает взаимодействие с пользователями Skype для бизнеса Online, и при запуске Teams пользователи могут выбрать предпочитаемое приложение для чата и звонков.</span><span class="sxs-lookup"><span data-stu-id="009f7-157">Teams supports interoperability with Skype for Business Online users, and users will be given an opportunity to choose their preferred chat and calling app when they launch Teams.</span></span> <span data-ttu-id="009f7-158">Если один пользователь выбирает в качестве предпочитаемого приложения Teams, а другой еще не установил Teams или выбрал в качестве предпочитаемого Skype для бизнеса, они могут продолжить общение с помощью чата и звонков благодаря входящим в Teams функциям взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="009f7-158">If one user picks Teams as the preferred app, and another user hasn’t installed Teams or picked Skype for Business as the preferred chat and calling app, they can continue to chat and call each other through the interop capabilities that are part of Teams.</span></span>

<span data-ttu-id="009f7-159">Корпорация Майкрософт непрерывно работает над улучшением интерфейса взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="009f7-159">Microsoft is continuously improving the interop experiences.</span></span> <span data-ttu-id="009f7-160">В начале могут возникать ситуации, когда этот интерфейс не оправдает ожидания пользователей.</span><span class="sxs-lookup"><span data-stu-id="009f7-160">In the beginning, there may be some cases whereby the interop experiences are not meeting user expectations.</span></span> <span data-ttu-id="009f7-161">Так как Skype для бизнеса по-прежнему доступен, пользователи могут переложить на него те функции, которые не обслуживаются в Teams.</span><span class="sxs-lookup"><span data-stu-id="009f7-161">Since Skype for Business is still available to users, they can switch to Skype for Business for the capabilities that currently cannot be served by Teams.</span></span>

<span data-ttu-id="009f7-162">Запланированные собрания в Teams также относятся к перекрывающимся возможностям и позволяют пользователям планировать собрания в Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="009f7-162">Scheduled meetings in Teams is another overlapping capability that lets users schedule Teams meetings, or Skype for Business meetings.</span></span> <span data-ttu-id="009f7-163">Каждый из вариантов имеет свои преимущества, а со временем, когда работа с собраниями в Teams начнет отвечать бизнес-требованиям либо станет более функциональной, чем в Skype для бизнеса, пользователи естественным образом перейдут на собрания в Teams.</span><span class="sxs-lookup"><span data-stu-id="009f7-163">Each has its own advantages, and over time, when Teams meeting experience meets business requirements or surpasses the functionalities of Skype for Business meetings, we expect users to naturally switch to Teams meetings.</span></span>

<span data-ttu-id="009f7-164">При таком неуправляемом цикле взаимодействия с клиентом при параллельном размещении вам следует подготовить специалистов службы поддержки к обработке обращений, касающихся проблем с функциями взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="009f7-164">In this unmanaged side-by-side customer journey, prepare your helpdesk team to handle support calls from users when facing issues with interop capabilities.</span></span> <span data-ttu-id="009f7-165">Вы также можете напрямую указать пользователям, когда следует использовать собрания Teams, а когда — собрания Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="009f7-165">Or advise users when to choose Teams meetings over Skype for Business meetings, and vice versa.</span></span>

<span data-ttu-id="009f7-166">Этот цикл взаимодействия с клиентом при параллельном размещении может подходить вашей организации, если пользователи предпочитают неуправляемое взаимодействие при параллельном размещении, а организация открыто позволяет пользователям выбирать оптимальные средства для взаимодействия и совместной работы под свои задачи.</span><span class="sxs-lookup"><span data-stu-id="009f7-166">This side-by-side customer journey may be applicable to your organization, whereby the users are more receptive to the nature of the unmanaged side-by-side experience, and the organization openly allows the users to pick the best communications and collaboration tools that suit their requirements.</span></span>

<a name="managed-side-by-side-customer-journey"></a><span data-ttu-id="009f7-167">Управляемый цикл взаимодействия с клиентом при параллельном размещении</span><span class="sxs-lookup"><span data-stu-id="009f7-167">Managed side-by-side customer journey</span></span>
-------------------------------------

![](media/guidance_SkypeforBusiness_image2.png)

<span data-ttu-id="009f7-168">Управляемый цикл взаимодействия с клиентом при параллельном размещении подходит для организаций, стремящихся более детально контролировать внедрение Teams.</span><span class="sxs-lookup"><span data-stu-id="009f7-168">A managed side-by-side customer journey starts with organization wanting more control over how Teams is introduced.</span></span>

-   <span data-ttu-id="009f7-169">**Первым этапом** этого цикла является ограниченный пилотный проект Teams, учитывающий современные требования к совместной работе (рабочая область на основе чата, каналы, приложения, интеграция с другими рабочими нагрузками Office 365 и т. д.).</span><span class="sxs-lookup"><span data-stu-id="009f7-169">The **first step** of this journey is a limited pilot of Teams scoped to modern collaboration requirements (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.).</span></span> <span data-ttu-id="009f7-170">В Teams также активны незапланированные собрания канала и приватный чат, позволяющие пользователям пилотного проекта оценить соответствующие функции в Teams.</span><span class="sxs-lookup"><span data-stu-id="009f7-170">Ad-hoc channel meetings and private chat in Teams is also enabled to provide a chance for pilot users to evaluate the Teams meetings experience and private chat experiences.</span></span> <span data-ttu-id="009f7-171">Запланированные собрания и частные звонки в Teams на этом этапе отключены.</span><span class="sxs-lookup"><span data-stu-id="009f7-171">Scheduled meetings and private calling capabilities in Teams are disabled at this stage.</span></span> <span data-ttu-id="009f7-172">Чтобы запустить пилотный проект, см. статью [Пилотное использование Teams параллельно со Skype для бизнеса](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="009f7-172">To get started with a pilot, go to [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>
    
-   <span data-ttu-id="009f7-173">**Вторым этапом** является развертывание Teams для современной совместной работы с поддержкой приватного чата в рамках всей организации.</span><span class="sxs-lookup"><span data-stu-id="009f7-173">The **second step** of this journey is extending the rollout of Teams for modern collaboration with private chat throughout the organization.</span></span> <span data-ttu-id="009f7-174">При этом запланированные собрания и частные звонки в Teams все еще отключены, чтобы сократить перекрытие с возможностями Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="009f7-174">Scheduled meetings, and private calling continue to be disabled in Teams to reduce the overlap  with with Skype for Business capabilities.</span></span>

    <span data-ttu-id="009f7-175">На этом этапе вам может потребоваться выбрать Teams или Skype для бизнеса в качестве предпочитаемого приложения чата для всей организации.</span><span class="sxs-lookup"><span data-stu-id="009f7-175">At this stage, you may need to consider whether preferred chat application should be set to Teams or Skype for Business for the entire organization.</span></span>

    - <span data-ttu-id="009f7-176">При выборе Teams подготовьте пользователей к возможным проблемам взаимодействия, которые могут возникать на раннем этапе при общении с людьми как внутри организации, так и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="009f7-176">If set to Teams, prepare your users to handle early interoperability challenges when communicating with other parties within and across the organization.</span></span>
    
    - <span data-ttu-id="009f7-177">Если выбран Skype для бизнеса, приватный чат Teams останется в этой системе, а конечные пользователи сразу же получат доступ к кроссплатформенным функциям сохраняемости чата в Teams и продолжат использовать приватный чат Skype для бизнеса при общении с пользователями Skype для бизнеса как внутри организации, так и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="009f7-177">If set to Skype for Business, private chats within Teams will remain in Teams, and end users can immediately take advantage of the cross-platform persistent nature of chat capabilities within Teams, and they will continue to use Skype for Business for private chats among Skype for Business users, within the organization and across the organization.</span></span>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="009f7-178">Примечание.</span><span class="sxs-lookup"><span data-stu-id="009f7-178">Note:</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="009f7-179">Сейчас выбор предпочитаемого приложения чата доступен только на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="009f7-179">Currently the preferred chat application setting is available only at the client level.</span></span> <span data-ttu-id="009f7-180">Для обеспечения требуемой конфигурации в масштабах организации потребуется кампания по обучению пользователей и их адаптации.</span><span class="sxs-lookup"><span data-stu-id="009f7-180">User training and adoption campaign will be required to drive the intended organization-wide configuration.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="009f7-181">**Третий этап** цикла начинается, когда организация решает, что работа с собраниями в Teams отвечает ее бизнес-требованиям.</span><span class="sxs-lookup"><span data-stu-id="009f7-181">The **third step** of the managed side-by-side customer journey starts when the organization decides that Teams meeting experience and capabilities meet their business requirements.</span></span> <span data-ttu-id="009f7-182">После включения частных собраний и собраний канала в Teams пользователи получают возможность планировать собрания как в Teams, так и в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="009f7-182">By enabling private and channel meetings in Teams, users are presented with options to schedule both Teams meetings and Skype for Business meetings.</span></span> <span data-ttu-id="009f7-183">Таким образом, можно ожидать, что благодаря постоянному усовершенствованию пользователи со временем сами перейдут на собрания в Teams.</span><span class="sxs-lookup"><span data-stu-id="009f7-183">Therefore, it is expected that over time users will naturally switch to Teams meetings given the continued innovations in Teams.</span></span> <span data-ttu-id="009f7-184">Чтобы успешнее управлять переходом из Skype для бизнеса в Teams, реализуйте комплексную программу по управлению изменениями, включающую обучение, поддержку и материалы, разъясняющие преимущества Teams для пользователя и содержащие инструкции по началу работы с этой системой.</span><span class="sxs-lookup"><span data-stu-id="009f7-184">To be successful in steering usage from Skype for Business to Teams, implement a robust change management program inclusive of training, support and communications that explains the value-add that Teams offers to the user, with clear guidance on how to get started with Teams.</span></span> <span data-ttu-id="009f7-185">При проектировании этой информационной кампании вы можете использовать наши ресурсы по [подготовке пользователей](http://aka.ms/UserReadiness).</span><span class="sxs-lookup"><span data-stu-id="009f7-185">Leverage our [User Readiness](http://aka.ms/UserReadiness) resources to help design your awareness campaign.</span></span>


<span data-ttu-id="009f7-186">**Четвертый этап** начинается с включения в Teams звонков.</span><span class="sxs-lookup"><span data-stu-id="009f7-186">The **fourth step** of the managed side-by-side customer journey begins with enabling calling in Teams.</span></span> <span data-ttu-id="009f7-187">На этом этапе активно используются функции взаимодействия Teams, обеспечивающие беспроблемную параллельную работу.</span><span class="sxs-lookup"><span data-stu-id="009f7-187">Teams interoperability capabilities will feature heavily in this step to ensure a seamless side-by-side experience.</span></span> <span data-ttu-id="009f7-188">Чтобы поспособствовать использованию Teams для частных звонков, можно задать это средство в качестве приложения для звонков по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="009f7-188">Ideally, to enforce the use of Teams for private calling, Teams is set as the default calling app.</span></span> 

<span data-ttu-id="009f7-189">Вероятнее всего, что со временем Teams начнет отвечать всем требованиям организации по взаимодействию и совместной работе, после чего начнется **пятый этап**.</span><span class="sxs-lookup"><span data-stu-id="009f7-189">Over time, potentially the whole organization can rely solely on Teams to meet communications and collaboration requirements and take the **fifth step**.</span></span> <span data-ttu-id="009f7-190">Чтобы узнать о новых возможностях в Teams, см. статью [Стратегия Office 365](http://aka.ms/TeamsRoadmap).</span><span class="sxs-lookup"><span data-stu-id="009f7-190">To see when new features are coming in Teams, see the [Office 365 Roadmap](http://aka.ms/TeamsRoadmap).</span></span> 

<a name="managing-side-by-side-experience"></a><span data-ttu-id="009f7-191">Управление параллельной работой</span><span class="sxs-lookup"><span data-stu-id="009f7-191">Managing side-by-side experience</span></span>
--------------------------------

<span data-ttu-id="009f7-192">В организациях с соответствующими подписками Office 365 продукт Microsoft Teams активен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="009f7-192">By default, for organizations with eligible Office 365 subscriptions, Microsoft Teams is enabled.</span></span> <span data-ttu-id="009f7-193">Если ваша организация удовлетворяет профилю для неуправляемого цикла взаимодействия с клиентом при параллельном размещении, мы настоятельно рекомендуем оставить все как есть, чтобы обеспечить естественное освоение Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="009f7-193">If your organization fits the profile for unmanaged side-by-side customer journey, we highly recommend you keep it as-is to foster organic adoption of Microsoft Teams.</span></span>

<span data-ttu-id="009f7-194">Продукт Teams доступен через современный веб-браузер и классические клиенты, не требующие прав ИТ-администратора для установки (сейчас актуально только для ПК), а также мобильные клиенты.</span><span class="sxs-lookup"><span data-stu-id="009f7-194">Teams is accessible via modern Web browser desktop clients which require no IT administrative privilege (for installation, currently applicable to PC only) and mobile clients.</span></span>

<span data-ttu-id="009f7-195">Все возможности в Teams, включая приватный чат и звонки, незапланированные и запланированные собрания, а также приложения, активны по умолчанию, что позволяет пользователям экспериментировать и подбирать себе наиболее удобные функции.</span><span class="sxs-lookup"><span data-stu-id="009f7-195">All capabilities in Teams, from private chat and calling, ad-hoc and scheduled meetings, and apps are enabled by default, allowing users to experiment and use the capabilities that suit their needs.</span></span> <span data-ttu-id="009f7-196">При первом запуске в Teams пользователь получает указания по выбору предпочитаемого приложения для чата и звонков (Microsoft Teams или Skype для бизнеса).</span><span class="sxs-lookup"><span data-stu-id="009f7-196">A first-run experience in Teams guides users to pick their preferred chat and calling application (Microsoft Teams or Skype for Business).</span></span>

<span data-ttu-id="009f7-197">Если вашей организации требуется более детально контролировать выпуск новых средств, таких как Teams, можно рассмотреть следующие варианты для управляемого цикла взаимодействия с клиентом при параллельном размещении:</span><span class="sxs-lookup"><span data-stu-id="009f7-197">Should your organization require a more controlled release of new tools such as Teams, the following options can be considered for your managed side-by-side customer journey, they are:</span></span>

-   <span data-ttu-id="009f7-198">Пилотное использование и развертывание Teams для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="009f7-198">Pilot and rollout of Teams for collaboration.</span></span> <span data-ttu-id="009f7-199">См. статью [Пилотное использование Teams параллельно со Skype для бизнеса](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="009f7-199">See [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>

-   <span data-ttu-id="009f7-200">Развертывание Teams для собраний</span><span class="sxs-lookup"><span data-stu-id="009f7-200">Rollout of Teams for meetings</span></span>

-   <span data-ttu-id="009f7-201">Развертывание Teams для звонков</span><span class="sxs-lookup"><span data-stu-id="009f7-201">Rollout of Teams for calling</span></span>

### <a name="teams-pilot-and-rollout-for-collaboration"></a><span data-ttu-id="009f7-202">Пилотное использование и развертывание Teams для совместной работы</span><span class="sxs-lookup"><span data-stu-id="009f7-202">Teams pilot and rollout for collaboration</span></span>

<span data-ttu-id="009f7-203">В основе Microsoft Teams лежит сохраняемый чат и интеграция с Office 365, а также усовершенствованный функционал Групп Office 365.</span><span class="sxs-lookup"><span data-stu-id="009f7-203">At its core, Microsoft Teams was built around persistent chat and integration with Office 365 by enhancing Office 365 Groups.</span></span>

<span data-ttu-id="009f7-204">Так как пользователи вашей организации с лицензией по соответствующей подписке Office 365 по умолчанию имеют доступ к Teams, для реализации ограниченного пилотного проекта потребуется отключить лицензию Teams у всех сотрудников, не вошедших в пилотную группу.</span><span class="sxs-lookup"><span data-stu-id="009f7-204">Since by default users in your organization with an eligible Office 365 subscription license are enabled for Teams, a limited Teams pilot will involve disabling the Teams license for all users who are outside of the pilot group.</span></span>

<span data-ttu-id="009f7-205">Чтобы ограничить применение Teams совместной работой и приватным чатом, а также сократить путаницу на стороне пользователя, вызванную перекрытием возможностей со Skype для бизнеса, вы можете изменить указанные ниже параметры на уровне клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="009f7-205">To focus the Teams release as a collaboration and private chat solution, and to reduce user confusion due to overlapping capabilities with Skype for Business, you can change the following settings at the Office 365 tenant level.</span></span> <span data-ttu-id="009f7-206">Чтобы изменить эти параметры Office 365, см. статью [Настройка Microsoft Teams в вашей организации Office 365](Office-365-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="009f7-206">To change these Office 365 settings, see [Set up Microsoft Teams in your Office 365 organization](Office-365-set-up.md).</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="009f7-207">Раздел</span><span class="sxs-lookup"><span data-stu-id="009f7-207">Section Heading</span></span></th>
<th align="left"><span data-ttu-id="009f7-208">Параметр</span><span class="sxs-lookup"><span data-stu-id="009f7-208">Setting</span></span></th>
<th align="left"><span data-ttu-id="009f7-209">Описание</span><span class="sxs-lookup"><span data-stu-id="009f7-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="009f7-210">Звонки и собрания</strong></span><span class="sxs-lookup"><span data-stu-id="009f7-210">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="009f7-211">Allow scheduling for private meetings (Разрешить планирование для частных собраний): <strong>Отключено</strong></span><span class="sxs-lookup"><span data-stu-id="009f7-211">Allow scheduling for private meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="009f7-212">Allow scheduling for channel meetings (Разрешить планирование для собраний канала): <strong>Отключено</strong></span><span class="sxs-lookup"><span data-stu-id="009f7-212">Allow scheduling for channel meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="009f7-213">Allow private calling (Разрешить частные звонки): <strong>Отключено</strong></span><span class="sxs-lookup"><span data-stu-id="009f7-213">Allow private calling: <strong>Off</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="009f7-214">Отключив этот параметр, вы запретите пользователям планировать частные собрания.</span><span class="sxs-lookup"><span data-stu-id="009f7-214">Disabling this setting prevents users from scheduling private meetings</span></span></p><p><span data-ttu-id="009f7-215">Отключив этот параметр, вы запретите пользователям планировать собрания канала.</span><span class="sxs-lookup"><span data-stu-id="009f7-215">Disabling this setting prevents users from scheduling channel meetings</span></span></p><p><span data-ttu-id="009f7-216">Отключив этот параметр, вы запретите пользователям выполнять частные звонки (как голосовые, так и видеозвонки).</span><span class="sxs-lookup"><span data-stu-id="009f7-216">Disabling this setting prevents users from making private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="009f7-217">Примечание.</span><span class="sxs-lookup"><span data-stu-id="009f7-217">Note:</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="009f7-218">Вам следует отключить частные звонки для бизнес-пользователей, корпоративных пользователей, а также гостевых пользователей (если в вашей организации применяется гостевой доступ).</span><span class="sxs-lookup"><span data-stu-id="009f7-218">You must disable Private Calling to both Business and Enterprise users, and Guest users (if Guest Access is applicable to your organization).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>



<span data-ttu-id="009f7-219">При такой конфигурации пользователей можно познакомить с принципами работы собраний в Teams, продвигая использование специальных встреч в канале и разрешая использование голосовой и видеосвязи, а также демонстрации экрана в рамках современного подхода к совместной работе.</span><span class="sxs-lookup"><span data-stu-id="009f7-219">With this configuration, users can be introduced to how meetings work in Teams by advocating the use of ad-hoc channel meetup, enabling the use of voice, video, and screen sharing as part of the modern collaboration experience.</span></span> <span data-ttu-id="009f7-220">Кроме того, в Teams сотрудники могут пользоваться сохраняемыми и кроссплатформенными функциями приватного чата.</span><span class="sxs-lookup"><span data-stu-id="009f7-220">End users can also benefit from Teams persistent, cross-platform, private chat capabilities.</span></span>

<span data-ttu-id="009f7-221">За успешным пилотным проектом по использованию Teams для совместной работы и приватного чата может последовать масштабное развертывание в рамках всей организации, для чего потребуется активировать лицензию Teams у всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="009f7-221">A successful Teams pilot for collaboration and private chat can be followed up with broad rollout throughout the organization by enabling Teams license for all users.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="009f7-222">Примечание.</span><span class="sxs-lookup"><span data-stu-id="009f7-222">Note:</span></span></p></td>
<td align="left"><span data-ttu-id="009f7-223">Во время пилотного проекта и на втором этапе, когда активируется приватный чат, пользователь Teams, общающийся с пользователем Skype для бизнес посредством чата, не сможет:</span><span class="sxs-lookup"><span data-stu-id="009f7-223">During the pilot, and in phase two when private chat is enabled, a Teams user chatting with a Skype for Business user will not be able to do the following:</span></span><br><span data-ttu-id="009f7-224">
- запустить видеозвонок из сеанса чата;</span><span class="sxs-lookup"><span data-stu-id="009f7-224">
- Start video call from a chat session</span></span><br><span data-ttu-id="009f7-225">
- передавать файлы;</span><span class="sxs-lookup"><span data-stu-id="009f7-225">
- Transfers files</span></span> <br><span data-ttu-id="009f7-226">
- запустить многосторонний звонок из сеанса чата;</span><span class="sxs-lookup"><span data-stu-id="009f7-226">
- Initiate a multiparty call from the chat session</span></span><br><span data-ttu-id="009f7-227">
- запустить сеанс совместного доступа к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="009f7-227">
- Users will not be able to start a desktop sharing session</span></span><br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a><span data-ttu-id="009f7-228">Развертывание Teams для собраний</span><span class="sxs-lookup"><span data-stu-id="009f7-228">Rollout of Teams for meetings</span></span>

<span data-ttu-id="009f7-229">После того как пользователи привыкнут к совместной работе с помощью Microsoft Teams, можно рассмотреть возможность включения в организации запланированных собраний.</span><span class="sxs-lookup"><span data-stu-id="009f7-229">As users are getting accustomed to collaborating using Microsoft Teams, scheduled meetings can be considered as the next capability to enable in the organization.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="009f7-230">Примечание.</span><span class="sxs-lookup"><span data-stu-id="009f7-230">Note:</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="009f7-231">Почтовые ящики организаторов запланированных собраний должны находиться в мультитенантной среде Exchange Online (или Exchange Online Dedicated vNext).</span><span class="sxs-lookup"><span data-stu-id="009f7-231">The organizers of scheduled meetings must have their mailboxes in Exchange Online multi-tenant (or Exchange Online Dedicated vNext).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="009f7-232">Чтобы включить запланированные собрания в Teams, можно настроить на уровне клиента указанные ниже параметры, которые применяются только к бизнес-пользователям и корпоративным пользователям.</span><span class="sxs-lookup"><span data-stu-id="009f7-232">The following settings can be configured at the tenant level to enable scheduled meetings in Teams, and the settings are applicable to Business and Enterprise users only.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="009f7-233">Раздел</span><span class="sxs-lookup"><span data-stu-id="009f7-233">Section Heading</span></span></th>
<th align="left"><span data-ttu-id="009f7-234">Параметр</span><span class="sxs-lookup"><span data-stu-id="009f7-234">Setting</span></span></th>
<th align="left"><span data-ttu-id="009f7-235">Описание</span><span class="sxs-lookup"><span data-stu-id="009f7-235">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="009f7-236">Звонки и собрания</strong></span><span class="sxs-lookup"><span data-stu-id="009f7-236">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="009f7-237">Allow scheduling for private meetings (Разрешить планирование для частных собраний): <strong>Включено</strong></span><span class="sxs-lookup"><span data-stu-id="009f7-237">Allow scheduling for private meetings: <strong>On</strong></span></span></p><p><span data-ttu-id="009f7-238">Allow scheduling for channel meetings (Разрешить планирование для собраний канала): <strong>Включено</strong></span><span class="sxs-lookup"><span data-stu-id="009f7-238">Allow scheduling for channel meetings: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="009f7-239">Включив этот параметр, вы разрешите пользователям планировать частные собрания.</span><span class="sxs-lookup"><span data-stu-id="009f7-239">Enabling this setting allows users to schedule private meetings</span></span></p><p><span data-ttu-id="009f7-240">Включив этот параметр, вы разрешите пользователям планировать собрания канала.</span><span class="sxs-lookup"><span data-stu-id="009f7-240">Enabling this setting allows users to schedule channel meetings</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="009f7-241">Запланированные собрания можно организовать через классический клиент Teams, браузер или Microsoft Outlook с помощью соответствующей надстройки для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="009f7-241">Scheduled meetings can be organized via the Teams desktop client, a browser, or via Microsoft Outlook using the meeting add-in for Microsoft Teams.</span></span> <span data-ttu-id="009f7-242">После включения запланированных собраний в Teams мы рекомендуем начать обучать пользователей созданию собраний Teams или обновлению существующих собраний Skype для бизнеса до собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="009f7-242">Once scheduled meetings in Teams is enabled, we recommend you start educating users to create new Teams meetings or update existing Skype for Business meetings to Teams meetings.</span></span>

### <a name="rollout-of-teams-for-calling"></a><span data-ttu-id="009f7-243">Развертывание Teams для звонков</span><span class="sxs-lookup"><span data-stu-id="009f7-243">Rollout of Teams for calling</span></span>

<span data-ttu-id="009f7-244">Функции частных звонков в Teams будут непрерывно совершенствоваться и со временем смогут полностью заменить Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="009f7-244">Private calling is the Teams capability that will be continuously developed, and over time provide a compelling replacement to Skype for Business.</span></span> <span data-ttu-id="009f7-245">Если вашей организации нужно определить, соответствуют ли такие функции ее бизнес-требованиям, можно настроить указанные ниже параметры на уровне клиента, чтобы включить частные звонки в Teams.</span><span class="sxs-lookup"><span data-stu-id="009f7-245">When your organization considers that Teams private calling capabilities meet key business requirements, the following settings can be configured at the tenant level to enable private calling in Teams.</span></span> 

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="009f7-246">Раздел</span><span class="sxs-lookup"><span data-stu-id="009f7-246">Section Heading</span></span></th>
<th align="left"><span data-ttu-id="009f7-247">Параметр</span><span class="sxs-lookup"><span data-stu-id="009f7-247">Setting</span></span></th>
<th align="left"><span data-ttu-id="009f7-248">Описание</span><span class="sxs-lookup"><span data-stu-id="009f7-248">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="009f7-249">Звонки и собрания</strong></span><span class="sxs-lookup"><span data-stu-id="009f7-249">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="009f7-250">Allow private calling (Разрешить частные звонки): <strong>Включено</strong></span><span class="sxs-lookup"><span data-stu-id="009f7-250">Allow private calling: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="009f7-251">Включив этот параметр, вы разрешите пользователям выполнять частные звонки (как голосовые, так и видеозвонки).</span><span class="sxs-lookup"><span data-stu-id="009f7-251">Enabling this setting allows users to place private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="009f7-252">Примечание.</span><span class="sxs-lookup"><span data-stu-id="009f7-252">Note:</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="009f7-253">Allow users to chat privately (Разрешить пользователям приватный чат). Включив этот параметр, вы разрешите пользователям осуществлять приватный чат с другими людьми.</span><span class="sxs-lookup"><span data-stu-id="009f7-253">Allow users to chat privately: Enabling this setting allows users to chat with other users privately.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>


<span data-ttu-id="009f7-254">На этом этапе нужно попросить всех пользователей выбрать Teams в качестве предпочитаемого приложения для звонков.</span><span class="sxs-lookup"><span data-stu-id="009f7-254">At this stage, all users must be instructed to choose Teams as the preferred calling app.</span></span>

<span data-ttu-id="009f7-255">После включения частных звонков Teams будет предоставлять все возможности, доступные в Skype для бизнеса, а сотрудники смогут использовать Teams для взаимодействия и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="009f7-255">With the enablement of private calling, Teams will deliver all capabilities currently provided by Skype for Business, and users can start using Teams to fulfill their communications and collaboration requirements.</span></span>


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><span data-ttu-id="009f7-256"><strong>Дальнейшие действия.</strong> Обеспечив работу Teams параллельно со Skype для бизнеса, перейдите к статье об [извлечении выгоды за счет освоения Teams пользователями](continue-journey.md), чтобы продолжить переход со Skype для бизнеса на Teams.</span><span class="sxs-lookup"><span data-stu-id="009f7-256"><strong>Next Action:</strong> Once Teams is up and running side-by-side with Skype for Business, [Drive Value through user adoption of Teams](continue-journey.md), while continuing your journey from Skype for Business to Teams.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>