---
title: Управление командами с помощью политик
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Подумайте о политиках Teams.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f06e9aa87cc0c1af758bf0c8c9abad6641debbd
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460499"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="58c79-103">Управление командами с помощью политик</span><span class="sxs-lookup"><span data-stu-id="58c79-103">Manage Teams with policies</span></span>

<span data-ttu-id="58c79-104">Политики являются важной частью управления Teams.</span><span class="sxs-lookup"><span data-stu-id="58c79-104">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="58c79-105">Эта статья посвящена использованию политик на пользу вашей организации.</span><span class="sxs-lookup"><span data-stu-id="58c79-105">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="58c79-106">Для чего используются политики</span><span class="sxs-lookup"><span data-stu-id="58c79-106">What you use policies for</span></span>

<span data-ttu-id="58c79-107">Политики используются для выполнения многих задач в организации в различных областях, таких как обмен сообщениями, собрания и приложения.</span><span class="sxs-lookup"><span data-stu-id="58c79-107">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="58c79-108">Вы можете разрешить пользователям планировать собрания в канале teams, разрешить пользователям редактировать отправленные сообщения и управлять возможностью закрепления приложений на панели приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="58c79-108">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="58c79-109">Назначение политик</span><span class="sxs-lookup"><span data-stu-id="58c79-109">How to assign policies</span></span>

<span data-ttu-id="58c79-110">Политики можно на должны быть назначены несколькими способами в зависимости от того, какую задачу выполняет ваша организация.</span><span class="sxs-lookup"><span data-stu-id="58c79-110">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="58c79-111">Вы можете делать и просматривать задания в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="58c79-111">You can make and view assignments in the Teams admin center.</span></span>

![Снимок экрана: назначение групповой политики.](media/group-policy-assignment.png)

<span data-ttu-id="58c79-113">Дополнительные информацию о назначении [политик](assign-policies.md)можно узнать здесь.</span><span class="sxs-lookup"><span data-stu-id="58c79-113">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="58c79-114">Управление политиками</span><span class="sxs-lookup"><span data-stu-id="58c79-114">How to manage policies</span></span>

<span data-ttu-id="58c79-115">Управление политиками можно в Центре администрирования Microsoft Teams или [с помощью PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="58c79-115">Policies are managed with the Microsoft Teams admin center or [using PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell).</span></span>

<span data-ttu-id="58c79-116">Например, политика настройки приложения позволяет пользователям загружать пользовательские приложения, устанавливать приложения от имени пользователей и закрепить приложения на панели приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="58c79-116">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="58c79-117">Эти политики настраиваются в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="58c79-117">These policies are configured in the Teams admin center.</span></span>

![Снимок экрана: политика настройки приложения.](media/app-setup-policy.png)

<span data-ttu-id="58c79-119">Кроме того, политика собрания может использоваться для управления настройками звука и видео в собраниях Teams, такими как транскрипция, записи в облаке, IP-аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="58c79-119">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![Снимок экрана: политика собрания.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="58c79-121">Teams для образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="58c79-121">Teams for Education</span></span>

<span data-ttu-id="58c79-122">Вы также можете использовать мастер политик [Teams](easy-policy-setup-edu.md) для образования, чтобы легко настроить политики для среды обучения и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="58c79-122">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Снимок экрана: мастер политики Teams для образовательных сфере.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="58c79-124">Типы политик</span><span class="sxs-lookup"><span data-stu-id="58c79-124">Types of policies</span></span>

<span data-ttu-id="58c79-125">В Microsoft Teams можно управлять следующими политиками:</span><span class="sxs-lookup"><span data-stu-id="58c79-125">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="58c79-126">Тип политики</span><span class="sxs-lookup"><span data-stu-id="58c79-126">Policy type</span></span> | <span data-ttu-id="58c79-127">Описание</span><span class="sxs-lookup"><span data-stu-id="58c79-127">Description</span></span>
------------|------------
[<span data-ttu-id="58c79-128">Пакеты политики</span><span class="sxs-lookup"><span data-stu-id="58c79-128">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="58c79-129">Пакет политики в Microsoft Teams — это набор предопределельных политик и параметров, которые можно назначить пользователям с похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="58c79-129">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="58c79-130">Политики собраний</span><span class="sxs-lookup"><span data-stu-id="58c79-130">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="58c79-131">Политика собрания используется для управления возможностями, доступными участникам собрания для собраний, запланированных пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="58c79-131">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="58c79-132">Политики собраний включают следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="58c79-132">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="58c79-133">— политики аудио- и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="58c79-133">- Audio and video policies</span></span><br> <span data-ttu-id="58c79-134">— политики общего доступа к содержимому и экрану</span><span class="sxs-lookup"><span data-stu-id="58c79-134">- Content and screen sharing policies</span></span><br> <span data-ttu-id="58c79-135">- Политики участников, гостей и доступа</span><span class="sxs-lookup"><span data-stu-id="58c79-135">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="58c79-136">- Общие политики</span><span class="sxs-lookup"><span data-stu-id="58c79-136">- General policies</span></span>
[<span data-ttu-id="58c79-137">Политики голосовой и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="58c79-137">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="58c79-138">Политики голосовой и голосовой почты управляют этими настройками с помощью команд, таких как экстренные вызовы, маршруты звонков и ИД звонив.</span><span class="sxs-lookup"><span data-stu-id="58c79-138">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="58c79-139">Политики приложений</span><span class="sxs-lookup"><span data-stu-id="58c79-139">App policies</span></span>](app-policies.md)| <span data-ttu-id="58c79-140">Политики приложений используются для управления приложениями в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="58c79-140">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="58c79-141">Администраторы могут разрешить или заблокировать приложения, которые пользователи могут устанавливать, закрепить приложения на панели приложений Teams и установить приложение от имени пользователей.</span><span class="sxs-lookup"><span data-stu-id="58c79-141">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="58c79-142">Политики обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="58c79-142">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="58c79-143">Политики обмена сообщениями контролируют доступность функций чата и каналов.</span><span class="sxs-lookup"><span data-stu-id="58c79-143">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="58c79-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="58c79-144">Related topics</span></span>

* [<span data-ttu-id="58c79-145">Управление политиками отзывов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58c79-145">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="58c79-146">Управление политиками команд в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58c79-146">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="58c79-147">Просмотр назначений политики в журнале действий</span><span class="sxs-lookup"><span data-stu-id="58c79-147">View policy assignments in the Activity Log</span></span>](activity-log.md)
* [<span data-ttu-id="58c79-148">Подготовка к трансляциям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58c79-148">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="58c79-149">Политики и пакеты политик Teams для образования</span><span class="sxs-lookup"><span data-stu-id="58c79-149">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)
