---
title: Задания в Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Сведения о том, как управлять заданиями в центре администрирования Microsoft Teams в Teams для образовательных учреждений.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3a0bf0dd0141679dc89ed1d5ecc0cfc542854c8
ms.sourcegitcommit: 3eb5820b279fc904f34ac4259deeb419e02d832a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561055"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="c879c-103">Задания в Teams для образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="c879c-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="c879c-104">Назначения — это задачи или единицы работы, назначенные студенту или участнику команды в классе в рамках изучения.</span><span class="sxs-lookup"><span data-stu-id="c879c-104">Assignments are tasks or units of work assigned to a student or team member in a class as part of their study.</span></span> <span data-ttu-id="c879c-105">Вы можете создавать задания в рамках класса Teams.</span><span class="sxs-lookup"><span data-stu-id="c879c-105">You can create assignments within your Teams class.</span></span>

<span data-ttu-id="c879c-106">Дополнительные [сведения о назначениях](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span><span class="sxs-lookup"><span data-stu-id="c879c-106">[Learn more about Assignments](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="c879c-107">Подробные сведения о назначениях групп на разных платформах можно найти в разделе [функции групп на платформе](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="c879c-107">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c879c-108">Назначения в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c879c-108">Assignments in the Microsoft Teams admin center</span></span>

<span data-ttu-id="c879c-109">С помощью параметров администратора в центре администрирования Microsoft Teams вы можете включать и отключать указанные ниже функции для учащихся и преподавателей в Организации.</span><span class="sxs-lookup"><span data-stu-id="c879c-109">With the admin settings in Microsoft Teams admin center, you can turn the following features on or off to be available for students and teachers within your organization.</span></span> <span data-ttu-id="c879c-110">Ниже указаны параметры, связанные с назначениями.</span><span class="sxs-lookup"><span data-stu-id="c879c-110">The following are settings related to Assignments:</span></span>

<span data-ttu-id="c879c-111"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="c879c-111"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="c879c-112">Еженедельная сводка по электронной почте опекунов</span><span class="sxs-lookup"><span data-stu-id="c879c-112">Weekly guardian email digest</span></span>

<span data-ttu-id="c879c-113">В сообщениях электронной почты будут содержаться сведения о назначениях за предыдущую неделю и за неделю, и они будут отправлены по выходным.</span><span class="sxs-lookup"><span data-stu-id="c879c-113">The emails will contain information about assignments from the previous week and for the upcoming week, and will be sent over the weekend.</span></span> <span data-ttu-id="c879c-114">Сведения о содержимом электронной почты можно найти здесь.</span><span class="sxs-lookup"><span data-stu-id="c879c-114">Information about the email content can be found here.</span></span> <span data-ttu-id="c879c-115">Администраторы должны настроить и обновить эти сообщения с помощью [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/).</span><span class="sxs-lookup"><span data-stu-id="c879c-115">The emails need to be set up and updated by the admins by using [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/).</span></span> <span data-ttu-id="c879c-116">Эта функция автоматически заполняет классы для Teams с помощью раскрывающемся списка учащихся в системе данных учащихся (SIS) учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="c879c-116">This feature automatically populates classes for Teams with student rosters from the school's student information system (SIS).</span></span> <span data-ttu-id="c879c-117">Чтобы включить эту функцию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c879c-117">The steps to enable this feature are:</span></span>

1. <span data-ttu-id="c879c-118">Импорт родительских контактных данных через родительские и Опекунную синхронизацию в SDS.</span><span class="sxs-lookup"><span data-stu-id="c879c-118">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="c879c-119">Инструкции по включению родительских и Опекунных синхронизаций содержатся в разделе [Включение синхронизации родительских и опекунов](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span><span class="sxs-lookup"><span data-stu-id="c879c-119">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="c879c-120">Включите параметр опекуна в центре администрирования Microsoft Teams, так как этот параметр отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c879c-120">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="c879c-121">Это позволит преподавателям отправлять еженедельные дайджесты.</span><span class="sxs-lookup"><span data-stu-id="c879c-121">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c879c-122">Преподаватели могут отказаться от дайджеста, отменив выбор параметра в собственной группе личного класса (**Параметры назначения > родительских и опекунных сообщений**).</span><span class="sxs-lookup"><span data-stu-id="c879c-122">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="c879c-123">Чтобы убедиться в том, что родительские элементы получат сообщение электронной почты, должны быть истинными три следующих элемента:</span><span class="sxs-lookup"><span data-stu-id="c879c-123">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="c879c-124">Адрес электронной почты, прикрепленный к профилю учащихся в SDS и пометил его как _родительский элемент_ или _опекун_.</span><span class="sxs-lookup"><span data-stu-id="c879c-124">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="c879c-125">Дополнительные сведения можно найти в разделе [Формат файла синхронизации родительских и опекунов](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span><span class="sxs-lookup"><span data-stu-id="c879c-125">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="c879c-126">Учащиеся принадлежат по крайней мере одному классу, в котором в [параметрах назначений](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)не отключены преподаватели по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="c879c-126">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="c879c-127">В сообщениях электронной почты будут содержаться сведения о назначениях, у которых Дата выполнения указана на предыдущей неделе или на предстоящей неделе.</span><span class="sxs-lookup"><span data-stu-id="c879c-127">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="c879c-128">Этот параметр по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="c879c-128">This setting is off by default.</span></span>


<span data-ttu-id="c879c-129"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="c879c-129"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="c879c-130">MakeCode</span><span class="sxs-lookup"><span data-stu-id="c879c-130">MakeCode</span></span>
<span data-ttu-id="c879c-131">Microsoft MakeCode — это основанная на блоках платформа кодирования, благодаря которой компьютерному науку выдается жизнь для всех учащихся.</span><span class="sxs-lookup"><span data-stu-id="c879c-131">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="c879c-132">MakeCode — это продукт Microsoft, в соответствии с [условиями использования](https://go.microsoft.com/fwlink/?LinkID=206977) и политикой [конфиденциальности](https://go.microsoft.com/fwlink/?LinkId=521839) корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c879c-132">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="c879c-133">Этот параметр по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="c879c-133">This setting is off by default.</span></span> <span data-ttu-id="c879c-134">Чтобы включить назначение MakeCode в Teams, в **центре администрирования Teams** перейдите в раздел **задания** и установите переключатель MakeCode в положение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="c879c-134">To enable MakeCode assignments in Teams, in the **Teams Admin Center**, navigate to the **Assignments** section and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="c879c-135">Нажмите кнопку **сохранить** и подождите, пока эти параметры не вступят в силу.</span><span class="sxs-lookup"><span data-stu-id="c879c-135">Click **Save** and allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="c879c-136">Дополнительные сведения о том, как работает эта функция, можно найти в этом [видеоролике](https://makecode.com/blog/teams/teams-assignments).</span><span class="sxs-lookup"><span data-stu-id="c879c-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="c879c-137">Дополнительные [сведения о MakeCode](https://aka.ms/makecode).</span><span class="sxs-lookup"><span data-stu-id="c879c-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="c879c-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="c879c-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="c879c-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="c879c-139">Turnitin</span></span>

<span data-ttu-id="c879c-140">Turnitin — это служба обнаружения plagiarism.</span><span class="sxs-lookup"><span data-stu-id="c879c-140">Turnitin is a plagiarism detection service.</span></span> <span data-ttu-id="c879c-141">Это сторонний продукт или услуга, которым подпадают свои условия и правила конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="c879c-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="c879c-142">Вы несете ответственность за использование каких-либо продуктов и услуг сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="c879c-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="c879c-143">Этот параметр по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="c879c-143">This setting is off by default.</span></span>

<span data-ttu-id="c879c-144">Чтобы успешно включить Turnitin для вашей организации, у вас должна быть уже подписка на Turnitin.</span><span class="sxs-lookup"><span data-stu-id="c879c-144">In order to successfully enable Turnitin for your organization, you will need to already have a Turnitin subscription.</span></span> <span data-ttu-id="c879c-145">Вам потребуется ввести следующие дополнительные сведения, которые можно найти на консоли администрирования Turnitin:</span><span class="sxs-lookup"><span data-stu-id="c879c-145">You will need to enter the following additional information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="c879c-146">**TurnitinApiKey**: идентификатор GUID 32, который находится на консоли администрирования в разделе Интеграция.</span><span class="sxs-lookup"><span data-stu-id="c879c-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="c879c-147">**TurnitinApiUrl**: URL-адрес вашей консоли администратора Turnitin.</span><span class="sxs-lookup"><span data-stu-id="c879c-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="c879c-148">Вот несколько инструкций, которые помогут вам получить эти сведения.</span><span class="sxs-lookup"><span data-stu-id="c879c-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="c879c-149">**TurnitinApiUrl** — адрес узла консоли администрирования.</span><span class="sxs-lookup"><span data-stu-id="c879c-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="c879c-150">Образом `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="c879c-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="c879c-151">На консоли администрирования вы можете создать интеграцию и ключ API, связанный с интеграцией.</span><span class="sxs-lookup"><span data-stu-id="c879c-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="c879c-152">В меню сбоку выберите пункт **Интеграция** , а затем — пункт **добавить интеграцию** и присвойте имя интеграции.</span><span class="sxs-lookup"><span data-stu-id="c879c-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![Снимок экрана, демонстрирующий Добавление новой интеграции](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="c879c-154">**TurnitinApiKey** будет предоставлен вам после того, как вы подпишитесь на запросы.</span><span class="sxs-lookup"><span data-stu-id="c879c-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="c879c-155">Скопируйте ключ API и вставьте его в центр администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c879c-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="c879c-156">Это единственный момент, когда вы можете просмотреть ключ.</span><span class="sxs-lookup"><span data-stu-id="c879c-156">This is the only time you can view the key.</span></span>

![Снимок экрана, на котором показано, как копировать ключ API](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="c879c-158">При нажатии кнопки " **сохранить** " в центре администрирования для этого параметра подождите, пока эти параметры не вступят в силу.</span><span class="sxs-lookup"><span data-stu-id="c879c-158">Upon clicking the **Save** button in the admin center for this setting, please allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="c879c-159">Готовы приступить к работе с интеграцией Turnitin в Teams?</span><span class="sxs-lookup"><span data-stu-id="c879c-159">Ready to start using the Turnitin integration in Teams?</span></span> <span data-ttu-id="c879c-160">Подпишитесь на [программу раннего доступа](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).</span><span class="sxs-lookup"><span data-stu-id="c879c-160">Sign up for the [early access program](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).</span></span>
