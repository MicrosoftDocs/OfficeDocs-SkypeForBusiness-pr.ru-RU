---
title: Инструкции для образовательных учреждений по работе с Microsoft Teams при низкой пропускной способности сети
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Статья о Microsoft Teams для образовательных учреждений, которая поможет решить проблемы с виртуальными собраниями и видео, вызванные низкой пропускной способностью сети. Кем бы вы ни были — родителем, педагогом или ИТ-администратором, у вас есть возможность улучшить эффективность взаимодействия с Teams.
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
ms.openlocfilehash: 17520645f23500550c6bc991c9d25ad2f72b2b6e
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598428"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="21648-104">Помощь в ситуациях с низкой пропускной способностью Teams для образовательных учреждений.</span><span class="sxs-lookup"><span data-stu-id="21648-104">Help for low-bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="21648-105">Когда речь идет о работе с Microsoft Teams, существует множество сетевых факторов, которые могут повлиять на производительность.</span><span class="sxs-lookup"><span data-stu-id="21648-105">There are numerous network elements when it comes to working with Microsoft Teams that can affect performance.</span></span> <span data-ttu-id="21648-106">Возможно, вам кажется, что низкая пропускная способность сети - нечто такое, на что вы совершенно не можете повлиять.</span><span class="sxs-lookup"><span data-stu-id="21648-106">Low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="21648-107">У вас может возникнуть какая-то из следующих ситуаций:</span><span class="sxs-lookup"><span data-stu-id="21648-107">Consider the following situations:</span></span>

- <span data-ttu-id="21648-108">Низкоскоростное интернет-соединение для школы.</span><span class="sxs-lookup"><span data-stu-id="21648-108">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="21648-109">Низкоскоростное интернет-соединение для одного или нескольких студентов.</span><span class="sxs-lookup"><span data-stu-id="21648-109">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="21648-110">Время суток, когда пропускная способность низка из-за использования сети в регионе.</span><span class="sxs-lookup"><span data-stu-id="21648-110">Times of the day when there's low bandwidth because of network usage in an area.</span></span>
- <span data-ttu-id="21648-111">Периоды с низкой пропускной способностью из-за локальных отключений не у школы и не у учащихся, но всё же влияющие на производительность.</span><span class="sxs-lookup"><span data-stu-id="21648-111">Low-bandwidth periods because of outages local to neither the school nor to students, but, which affect performance nonetheless.</span></span>
- <span data-ttu-id="21648-112">Проблемы, не связанные с пропускной способностью (например, проблемы с оборудованием), которые выглядят как проблемы с низкой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="21648-112">Non-bandwidth issues (for example, issues with hardware) that masquerade as low-bandwidth issues.</span></span>

<span data-ttu-id="21648-113">В этой статье вы найдете рекомендации по работе с Teams в случаях, когда возникает проблема низкой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="21648-113">This article will give you best practices to follow for various Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21648-114">Здесь есть информация о том, [Как Microsoft Teams использует память](teams-memory-usage-perf.md), потому что помимо проблем с низкой пропускной способностью у вас могут быть проблемы с ресурсами на вашем устройстве.</span><span class="sxs-lookup"><span data-stu-id="21648-114">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="21648-115">Если вы ищете сетевое руководство для Microsoft Teams, ознакомьтесь с разделом [Подготовка сети вашей организации для команд Microsoft](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="21648-115">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-admins"></a><span data-ttu-id="21648-116">Решение проблем низкой пропускной способности для администраторов</span><span class="sxs-lookup"><span data-stu-id="21648-116">Resolving low-bandwidth issues for Admins</span></span>

<span data-ttu-id="21648-117">Как ИТ-администратор вы должны помнить: возможно, у вас есть решения для распространенных проблем с низкой пропускной способностью, но к этим решениям следует подходить с вниманием.</span><span class="sxs-lookup"><span data-stu-id="21648-117">The important thing to remember, as an IT Admin, is that while you have solutions for low-bandwidth issues that are wide-spread that will resolve problems quickly, solutions should be considered carefully.</span></span> <span data-ttu-id="21648-118">Некоторые проблемы можно решить, сосредоточившись на более узкой области: например, на уровне преподавателя или даже учащихся и их семей.</span><span class="sxs-lookup"><span data-stu-id="21648-118">Some issues may be able to resolve with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="21648-119">Короче говоря, если проблема с низкой пропускной способностью возникает для широкой группы студентов, вы как ИТ-администратор можете что-то сделать. Ваше вмешательство также имеет смысл, если действия, предпринятые на уровне учащихся или преподавателей, не помогли.</span><span class="sxs-lookup"><span data-stu-id="21648-119">In short, if the low-bandwidth issue occurs for a wide group of students, taking action as an IT Admin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="21648-120">Если у вас есть время, чтобы инвестировать, стоит прочитать [Руководство по анализу качества взаимодействия](quality-of-experience-review-guide.md) (оно не относится к EDU, но оно все равно будет содержать ценную информацию).</span><span class="sxs-lookup"><span data-stu-id="21648-120">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="21648-121">Это руководство поможет опытным ИТ-администраторам рассмотреть в деталях взаимодействие преподавателей и студентов в сети.</span><span class="sxs-lookup"><span data-stu-id="21648-121">This guide will allow experienced IT Admins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="21648-122">Виртуальные собрания и видео</span><span class="sxs-lookup"><span data-stu-id="21648-122">Meetings and video</span></span>

<span data-ttu-id="21648-123">При решении проблем с низкой пропускной способностью основное внимание уделяется виртуальным собраниям, конкретно — видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="21648-123">A primary focus for low-bandwidth issues is meetings; specifically, video in meetings.</span></span> <span data-ttu-id="21648-124">Если студенты или преподаватели сообщают о проблемах, ИТ-администратор может предпринять ряд действий для обеспечения качества видеосвязи в контексте образовательного процесса.</span><span class="sxs-lookup"><span data-stu-id="21648-124">An IT Admin should consider the actions below when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="21648-125">Правила для видеособраний</span><span class="sxs-lookup"><span data-stu-id="21648-125">Meeting policies</span></span>

<span data-ttu-id="21648-126">Одна из наиболее проблемных областей для ситуаций с низкой пропускной способностью возникает при проведении виртуальных собраний по видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="21648-126">Regarding meetings, one of the most concerning areas for low-bandwidth situations has to do with videos.</span></span> <span data-ttu-id="21648-127">Teams может автоматически масштабировать обнаруженную полосу пропускания. К тому же вы как ИТ-администратор можете установить определенные параметры политики на уровне организатора и / или пользователей.</span><span class="sxs-lookup"><span data-stu-id="21648-127">In addition to Teams being able to scale to detected bandwidth automatically, you as an IT Admin have policy options you can set at the per-organizer and/or per-user level.</span></span> <span data-ttu-id="21648-128">Эти настройки позволят каждому участнику использовать видеосвязь максимально эффективно при существующей пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="21648-128">These options allow you to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="21648-129">Некоторые из вещей, которые вы можете установить с помощью политики:</span><span class="sxs-lookup"><span data-stu-id="21648-129">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="21648-130">Отключение видео в целом, так что никто не мог включить его.</span><span class="sxs-lookup"><span data-stu-id="21648-130">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="21648-131">Скорость передачи медиа (устанавливается для каждого пользователя).</span><span class="sxs-lookup"><span data-stu-id="21648-131">Media bit rate (this setting is set per-user).</span></span>

<span data-ttu-id="21648-132">Чтобы узнать больше о возможностях и получить пошаговое руководство по настройке политик для собраний и видео, ознакомьтесь со статьей [Настройка политики для собраний в Teams: аудио и видео](meeting-policies-audio-and-video.md).</span><span class="sxs-lookup"><span data-stu-id="21648-132">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](meeting-policies-audio-and-video.md).</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="21648-133">Правила совместного использования экрана</span><span class="sxs-lookup"><span data-stu-id="21648-133">Screen sharing policies</span></span>

<span data-ttu-id="21648-134">В других случаях преподаватели могут делиться всем своим экраном с учащимися, когда обмен должен ограничиваться приложением, соответствующим уроку.</span><span class="sxs-lookup"><span data-stu-id="21648-134">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="21648-135">Это также можно установить на уровне политики, если такой способ более предпочтителен, чем индивидуальная установка этого параметра каждым преподавателем.</span><span class="sxs-lookup"><span data-stu-id="21648-135">This setting can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="21648-136">Узнать, что даёт ограничение общего доступа к экрану с помощью параметров политики, можно в разделе [Параметры политики собраний в Teams: общий доступ к экрану](meeting-policies-audio-and-video.md).</span><span class="sxs-lookup"><span data-stu-id="21648-136">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Audio and video](meeting-policies-audio-and-video.md).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="21648-137">Телефонный номер для встреч</span><span class="sxs-lookup"><span data-stu-id="21648-137">Dial-in number for meetings</span></span>

<span data-ttu-id="21648-138">Некоторым студентам может быть проще попытаться дозвониться до некоторых занятий в классе.</span><span class="sxs-lookup"><span data-stu-id="21648-138">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="21648-139">Вы можете предоставить телефонный номер для собраний Teams, чтобы учащиеся с проблемами могли позвонить в качестве альтернативы посещению видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="21648-139">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="21648-140">Для получения дополнительной информации об этом вы можете прочитать [Установка телефонных номеров, включенных в приглашения в Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="21648-140">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="21648-141">Сценарии низкой пропускной способности для преподавателей</span><span class="sxs-lookup"><span data-stu-id="21648-141">Low-bandwidth scenarios as an educator</span></span>

<span data-ttu-id="21648-142">Преподаватели должны чувствовать, что у них есть возможности решения проблем с низкой пропускной способностью, и это лучше, чем решение проблемы на уровне ИТ-администратора, в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="21648-142">Educators should feel empowered to take steps to resolve low-bandwidth issues, and may be a superior choice to IT Admin action in the following situations:</span></span>

- <span data-ttu-id="21648-143">Если проблема временная или относительно временная.</span><span class="sxs-lookup"><span data-stu-id="21648-143">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="21648-144">Если есть определенное время суток, вы можете предвидеть возникновение проблемы, или период низкой пропускной способности имеет некоторую предсказуемость.</span><span class="sxs-lookup"><span data-stu-id="21648-144">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="21648-145">В этих ситуациях вы можете предпринять некоторые действия.</span><span class="sxs-lookup"><span data-stu-id="21648-145">In these situations, you can take some actions.</span></span>

<span data-ttu-id="21648-146">Дополнительные сведения см. в статье [использование Teams для учебных достижений, если пропускная способность слаба](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span><span class="sxs-lookup"><span data-stu-id="21648-146">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="21648-147">Сценарии низкой пропускной способности со стороны родителя или ученика</span><span class="sxs-lookup"><span data-stu-id="21648-147">Low-bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="21648-148">Существуют также ситуации, и вы должны заранее обсудить их со своими преподавателями, где проблема пропускной способности может быть на стороне студента (например, большое количество студентов могут смотреть видео уроки без проблем, но небольшое количество студентов есть трудности).</span><span class="sxs-lookup"><span data-stu-id="21648-148">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="21648-149">Будьте готовы к тому, что большинство родителей окажутся неспособны найти и устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="21648-149">It's not reasonable to expect many parents to be able to troubleshoot these issues.</span></span> <span data-ttu-id="21648-150">Проблемы с низкой пропускной способностью могут быть вне контроля ученика или родителей (например, их дом не подключен к сети с высокой пропускной способностью, несколько человек в семье используют полосу пропускания и возникает высокая нагрузка, сеть работает нестабильно и т. д.).</span><span class="sxs-lookup"><span data-stu-id="21648-150">Low-bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have numerous people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="21648-151">Мы собрали руководство в нашей статье [Использование Teams для работы в школе при низкой пропускной способности](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262), а также для родителей и учащихся, вы можете просмотреть и попробовать эти рекомендации, если у вас возникнут проблемы.</span><span class="sxs-lookup"><span data-stu-id="21648-151">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>