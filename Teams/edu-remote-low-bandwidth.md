---
title: Microsoft Teams. инструкции по низкой пропускной способности для образовательных учреждений
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Статья Microsoft Teams для образовательных учреждений, которая поможет решить проблемы с видеосвязью и видео, связанные с низкой пропускной способностью. Являетесь ли вы родителем, педагогом или ITAdmin, у вас есть возможность улучшить работу с Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f34ea2e65906c648081a019d6acf8a3f8a5cd5
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2020
ms.locfileid: "43034091"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="3e580-104">Помощь в ситуациях с низкой пропускной способностью для Teams для образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="3e580-104">Help for low bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="3e580-105">Когда речь идет о работе с Microsoft Teams, существует множество сетевых элементов, которые могут повлиять на производительность, а низкая пропускная способность - одна из ситуаций, которая может полностью ощущаться вне вашего контроля.</span><span class="sxs-lookup"><span data-stu-id="3e580-105">There are a lot of network elements when it comes to working with Microsoft Teams that can affect performance, and low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="3e580-106">Примите во внимание следующее:</span><span class="sxs-lookup"><span data-stu-id="3e580-106">Consider the following:</span></span>

- <span data-ttu-id="3e580-107">Низкоскоростное интернет-соединение для школы.</span><span class="sxs-lookup"><span data-stu-id="3e580-107">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="3e580-108">Низкоскоростное интернет-соединение для одного или нескольких студентов.</span><span class="sxs-lookup"><span data-stu-id="3e580-108">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="3e580-109">Время суток, когда пропускная способность низкая из-за использования сети в регионе.</span><span class="sxs-lookup"><span data-stu-id="3e580-109">Times of the day when there is low bandwidth due to network usage in an area.</span></span>
- <span data-ttu-id="3e580-110">Периоды с низкой пропускной способностью из-за локальных отключений ни у школы, ни у учащихся, но, тем не менее, влияющих на производительность.</span><span class="sxs-lookup"><span data-stu-id="3e580-110">Low bandwidth periods due to outages local to neither the school nor to students, but which impact performance nonetheless.</span></span>
- <span data-ttu-id="3e580-111">Проблемы, не связанные с пропускной способностью (например, проблемы с оборудованием), которые маскируются под проблемы с низкой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="3e580-111">Non-bandwidth issues (for example, issues with hardware) that masquerade as low bandwidth issues.</span></span>

<span data-ttu-id="3e580-112">В этой статье вы найдете рекомендации по выполнению различных действий Teams, когда столкнетесь с проблемой низкой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="3e580-112">This article will give you best practices to follow for a variety of Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e580-113">Здесь есть информация о том, [Как Microsoft Teams использует память](teams-memory-usage-perf.md), потому что помимо проблем с низкой пропускной способностью у вас могут быть проблемы с ресурсами на вашем устройстве.</span><span class="sxs-lookup"><span data-stu-id="3e580-113">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="3e580-114">Если вы ищете сетевое руководство для Microsoft Teams, ознакомьтесь с разделом [Подготовка сети вашей организации для команд Microsoft](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="3e580-114">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a><span data-ttu-id="3e580-115">Решение проблем с низкой пропускной способностью для ITAdmins</span><span class="sxs-lookup"><span data-stu-id="3e580-115">Resolving low bandwidth issues for ITAdmins</span></span>

<span data-ttu-id="3e580-116">Как ИТ-администратор, важно помнить, что, хотя у вас есть решения для проблем с низкой пропускной способностью, которые широко распространены и будут быстро решать проблемы, к этому следует относиться осторожно, поскольку некоторые проблемы могут быть решены с более узким фокусом взят на воспитателя или даже на уровне ученика / родителей.</span><span class="sxs-lookup"><span data-stu-id="3e580-116">The important thing to remember, as an ITAdmin, is that while you have solutions for low bandwidth issues that are wide-spread that will resolve problems quickly, this should be considered carefully, as some issues may be able to resolved with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="3e580-117">Короче говоря, если проблема с низкой пропускной способностью возникает для широкой группы студентов, принятие мер в качестве ITAdmin имеет смысл, а также имеет смысл, если действия, предпринятые на уровне учащихся / преподавателей, не были полезными.</span><span class="sxs-lookup"><span data-stu-id="3e580-117">In short, if the low bandwidth issue occurs for a wide group of students, taking action as an ITAdmin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="3e580-118">Если у вас есть время, чтобы инвестировать, стоит прочитать [Руководство по анализу качества взаимодействия](quality-of-experience-review-guide.md) (оно не относится к EDU, но оно все равно будет содержать ценную информацию).</span><span class="sxs-lookup"><span data-stu-id="3e580-118">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="3e580-119">Это позволит опытным ITAdmins углубиться в опыт своих преподавателей и студентов.</span><span class="sxs-lookup"><span data-stu-id="3e580-119">This will allow experienced ITAdmins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="3e580-120">Встречи и видео</span><span class="sxs-lookup"><span data-stu-id="3e580-120">Meetings and video</span></span>

<span data-ttu-id="3e580-121">Основное внимание при решении проблем с низкой пропускной способностью уделяется встречам, и особенно видео на собраниях</span><span class="sxs-lookup"><span data-stu-id="3e580-121">A primary focus for low bandwidth issues are meetings, and specifically video in meetings.</span></span> <span data-ttu-id="3e580-122">У нас есть некоторые из нижеприведенных действий, которые ITAdmin должен учитывать при решении вопросов, о которых сообщают студенты или преподаватели, в отношении обеспечения наилучшего опыта встреч в образовательной среде.</span><span class="sxs-lookup"><span data-stu-id="3e580-122">We have some of the actions below that an ITAdmin should consider when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="3e580-123">Политики собрания</span><span class="sxs-lookup"><span data-stu-id="3e580-123">Meeting policies</span></span>

<span data-ttu-id="3e580-124">Что касается встреч, одна из наиболее важных областей для ситуаций с низкой пропускной способностью связана с видео.</span><span class="sxs-lookup"><span data-stu-id="3e580-124">In regards to meetings, one of the most concerning areas for low bandwidth situations has to do with videos.</span></span> <span data-ttu-id="3e580-125">К счастью, помимо того, что Teams может автоматически масштабировать обнаруженную полосу пропускания, у вас, как у ITAdmin, есть параметры политики, которые вы можете установить на уровне организатора и / или уровня пользователя, чтобы предоставить каждому наилучшее представление о пропускной способности, которую они имеют. работать с в данное время.</span><span class="sxs-lookup"><span data-stu-id="3e580-125">Fortunately, in addition to Teams being able to scale to detected bandwidth automatically, you as an ITAdmin have policy options you can set at the per-organizer and/or per-user level to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="3e580-126">Некоторые из вещей, которые вы можете установить с помощью политики:</span><span class="sxs-lookup"><span data-stu-id="3e580-126">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="3e580-127">Отключение видео в целом, так что никто не мог включить его.</span><span class="sxs-lookup"><span data-stu-id="3e580-127">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="3e580-128">Скорость передачи медиа (это устанавливается для каждого пользователя).</span><span class="sxs-lookup"><span data-stu-id="3e580-128">Media bit rate (this is set per-user).</span></span>

<span data-ttu-id="3e580-129">Чтобы узнать больше о своих возможностях и ознакомиться со спецификой политик, которые необходимо установить для собраний и видео, ознакомьтесь с [настройками политики собраний в Teams: аудио и видео](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video) для получения подробной информации о пошаговом руководстве.</span><span class="sxs-lookup"><span data-stu-id="3e580-129">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video) for detailed walk-through information.</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="3e580-130">Правила совместного использования экрана</span><span class="sxs-lookup"><span data-stu-id="3e580-130">Screen sharing policies</span></span>

<span data-ttu-id="3e580-131">В других случаях преподаватели могут делиться всем своим экраном с учащимися, когда обмен должен ограничиваться приложением, соответствующим уроку.</span><span class="sxs-lookup"><span data-stu-id="3e580-131">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="3e580-132">Это также может быть установлено с помощью политики, если это более желательный способ сделать это, чем сделать так, чтобы преподаватели делали этот выбор индивидуально.</span><span class="sxs-lookup"><span data-stu-id="3e580-132">This can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="3e580-133">Чтобы получить представление о том, что можно сделать с ограничением общего доступа к экрану с помощью параметров политики, ознакомьтесь с разделом [Параметры политики собраний в Teams: общий доступ к экрану](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video).</span><span class="sxs-lookup"><span data-stu-id="3e580-133">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Screen sharing](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="3e580-134">Телефонный номер для встреч</span><span class="sxs-lookup"><span data-stu-id="3e580-134">Dial-in number for meetings</span></span>

<span data-ttu-id="3e580-135">Некоторым студентам может быть проще попытаться дозвониться до некоторых занятий в классе.</span><span class="sxs-lookup"><span data-stu-id="3e580-135">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="3e580-136">Вы можете предоставить телефонный номер для собраний Teams, чтобы учащиеся с проблемами могли позвонить в качестве альтернативы посещению видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="3e580-136">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="3e580-137">Для получения дополнительной информации об этом вы можете прочитать [Установка телефонных номеров, включенных в приглашения в Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="3e580-137">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="3e580-138">Сценарии низкой пропускной способности для преподавателей</span><span class="sxs-lookup"><span data-stu-id="3e580-138">Low bandwidth scenarios as an educator</span></span>

<span data-ttu-id="3e580-139">Преподаватели должны чувствовать себя способными предпринять шаги для решения проблем с низкой пропускной способностью и могут быть лучшим выбором для действий ITAdmin в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="3e580-139">Educators should feel empowered to take steps to resolve low bandwidth issues, and may be a superior choice to ITAdmin action in the following situations:</span></span>

- <span data-ttu-id="3e580-140">Если проблема временная или относительно временная.</span><span class="sxs-lookup"><span data-stu-id="3e580-140">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="3e580-141">Если есть определенное время суток, вы можете предвидеть возникновение проблемы, или период низкой пропускной способности имеет некоторую предсказуемость.</span><span class="sxs-lookup"><span data-stu-id="3e580-141">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="3e580-142">В этих ситуациях вы можете предпринять некоторые действия.</span><span class="sxs-lookup"><span data-stu-id="3e580-142">In these situations, you can take some actions.</span></span>

<span data-ttu-id="3e580-143">Дополнительные сведения см. в статье [использование Teams для учебных достижений, если пропускная способность слаба](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span><span class="sxs-lookup"><span data-stu-id="3e580-143">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="3e580-144">Сценарии низкой пропускной способности как родитель или ученик</span><span class="sxs-lookup"><span data-stu-id="3e580-144">Low bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="3e580-145">Существуют также ситуации, и вы должны заранее обсудить их со своими преподавателями, где проблема пропускной способности может быть на стороне студента (например, большое количество студентов могут смотреть видео уроки без проблем, но небольшое количество студентов есть трудности).</span><span class="sxs-lookup"><span data-stu-id="3e580-145">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="3e580-146">Неразумно ожидать, что многие родители смогут решать эти проблемы, и проблемы с низкой пропускной способностью могут быть вне контроля ученика или родителей (их дом может не иметь доступа к высокой пропускной способности, у них может быть много людей в их непосредственной близости использование полосы пропускания и влияние на то, что они могут сделать, может быть нестабильность интернета и т. д.).</span><span class="sxs-lookup"><span data-stu-id="3e580-146">It's not reasonable to expect many parents to be able to troubleshoot these issues, and low bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have a lot of people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="3e580-147">Мы собрали руководство в нашей статье [Использование Teams для работы в школе при низкой пропускной способности](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262), а также для родителей и учащихся, вы можете просмотреть и попробовать эти рекомендации, если у вас возникнут проблемы.</span><span class="sxs-lookup"><span data-stu-id="3e580-147">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>
