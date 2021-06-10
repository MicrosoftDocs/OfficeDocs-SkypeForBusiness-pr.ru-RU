---
title: Управление Teams политиками
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: В этой Teams политики.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77afc1cbb71fff9cb54decbbf6e5cfd10d6c4e59
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574188"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="5d0a8-103">Управление Teams политиками</span><span class="sxs-lookup"><span data-stu-id="5d0a8-103">Manage Teams with policies</span></span>

<span data-ttu-id="5d0a8-104">Политики являются важной частью управления Teams.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-104">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="5d0a8-105">В этой статье вы можете найти, как использовать политики на пользу вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-105">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="5d0a8-106">Для чего используются политики</span><span class="sxs-lookup"><span data-stu-id="5d0a8-106">What you use policies for</span></span>

<span data-ttu-id="5d0a8-107">Политики используются для выполнения многих задач в организации в различных областях, таких как обмен сообщениями, собрания и приложения.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-107">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="5d0a8-108">Вы можете разрешить пользователям планировать собрания в канале teams, разрешить пользователям изменять отправленные сообщения и управлять возможностью закрепления приложений на панели Teams приложений.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-108">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="5d0a8-109">Назначение политик</span><span class="sxs-lookup"><span data-stu-id="5d0a8-109">How to assign policies</span></span>

<span data-ttu-id="5d0a8-110">Политики могут быть назначены несколькими способами в зависимости от того, какие задачи выполняет ваша организация.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-110">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="5d0a8-111">Вы можете делать и просматривать задания в Центре Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-111">You can make and view assignments in the Teams admin center.</span></span>

![Снимок экрана: назначение групповой политики.](media/group-policy-assignment.png)

<span data-ttu-id="5d0a8-113">Подробнее о назначении политик можно узнать [здесь.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5d0a8-113">Learn more about assigning policies [here](policy-assignment-overview.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="5d0a8-114">Управление политиками</span><span class="sxs-lookup"><span data-stu-id="5d0a8-114">How to manage policies</span></span>

<span data-ttu-id="5d0a8-115">Управление политиками можно управлять с Microsoft Teams администрирования или [с помощью PowerShell.](./teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="5d0a8-115">Policies are managed with the Microsoft Teams admin center or [using PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

<span data-ttu-id="5d0a8-116">Например, с помощью политики настройки приложения можно разрешить пользователям загружать пользовательские приложения, устанавливать приложения от их имени и закрепить приложения на Teams панели приложений.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-116">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="5d0a8-117">Эти политики настраиваются в Центре администрирования Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-117">These policies are configured in the Teams admin center.</span></span>

![Снимок экрана: политика настройки приложений.](media/app-setup-policy.png)

<span data-ttu-id="5d0a8-119">Кроме того, политика собраний может использоваться для управления настройками звука и видео в собраниях Teams, такими как транскрибция, записи в облаке, ip audio/video.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-119">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![Снимок экрана: политика собрания.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="5d0a8-121">Teams для образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="5d0a8-121">Teams for Education</span></span>

<span data-ttu-id="5d0a8-122">Вы также можете использовать мастер политики Teams для [образования,](easy-policy-setup-edu.md) чтобы легко настроить политики для среды обучения и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-122">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Снимок экрана: Teams политики для образования.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="5d0a8-124">Типы политик</span><span class="sxs-lookup"><span data-stu-id="5d0a8-124">Types of policies</span></span>

<span data-ttu-id="5d0a8-125">С помощью этих политик можно управлять Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-125">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="5d0a8-126">Тип политики</span><span class="sxs-lookup"><span data-stu-id="5d0a8-126">Policy type</span></span> | <span data-ttu-id="5d0a8-127">Описание</span><span class="sxs-lookup"><span data-stu-id="5d0a8-127">Description</span></span>
------------|------------
[<span data-ttu-id="5d0a8-128">Пакеты политик</span><span class="sxs-lookup"><span data-stu-id="5d0a8-128">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="5d0a8-129">Пакет политики в Microsoft Teams — это набор предопределевших политик и параметров, которые можно назначить пользователям с похожими ролями в организации.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-129">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="5d0a8-130">Политики собраний</span><span class="sxs-lookup"><span data-stu-id="5d0a8-130">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="5d0a8-131">Политика собраний используется для управления функциями, доступными участникам собрания для собраний, запланированных пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-131">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="5d0a8-132">Политики собраний включают следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="5d0a8-132">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="5d0a8-133">Политики аудио- и видеосвязи</span><span class="sxs-lookup"><span data-stu-id="5d0a8-133">- Audio and video policies</span></span><br> <span data-ttu-id="5d0a8-134">Политики общего доступа к содержимому и экрану</span><span class="sxs-lookup"><span data-stu-id="5d0a8-134">- Content and screen sharing policies</span></span><br> <span data-ttu-id="5d0a8-135">- Участники, гости и политики доступа</span><span class="sxs-lookup"><span data-stu-id="5d0a8-135">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="5d0a8-136">Общие политики</span><span class="sxs-lookup"><span data-stu-id="5d0a8-136">- General policies</span></span>
[<span data-ttu-id="5d0a8-137">Политики голосовой и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="5d0a8-137">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="5d0a8-138">Политики голосовой и голосовой почты управляют этими настройками с помощью таких команд, как экстренные вызовы, маршруты звонков и ИД звоня.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-138">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="5d0a8-139">Политики приложений</span><span class="sxs-lookup"><span data-stu-id="5d0a8-139">App policies</span></span>](app-policies.md)| <span data-ttu-id="5d0a8-140">Политики приложений используются для управления приложениями в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-140">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="5d0a8-141">Администраторы могут разрешить или заблокировать приложения, которые пользователи могут устанавливать, закрепить приложения на панели Teams и установить приложение от имени пользователей.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-141">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="5d0a8-142">Политики обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="5d0a8-142">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="5d0a8-143">Политики обмена сообщениями контролируют доступность функций чата и каналов.</span><span class="sxs-lookup"><span data-stu-id="5d0a8-143">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5d0a8-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5d0a8-144">Related topics</span></span>

* [<span data-ttu-id="5d0a8-145">Назначение политик в Teams — начало работы</span><span class="sxs-lookup"><span data-stu-id="5d0a8-145">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
* [<span data-ttu-id="5d0a8-146">Управление политиками отзывов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d0a8-146">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="5d0a8-147">Управление политиками команд в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d0a8-147">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="5d0a8-148">Подготовка к трансляциям в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d0a8-148">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="5d0a8-149">Teams политики и пакеты политик для образования</span><span class="sxs-lookup"><span data-stu-id="5d0a8-149">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)