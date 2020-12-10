---
title: Задания в Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: f283a4fb2d49778f4b0e8b31f46dada46f900e6f
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616913"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="b882d-103">Задания в Teams для образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="b882d-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="b882d-104">В Teams для образовательных учреждений функции назначений и оценки позволяют преподавателям назначать задачи, трудозатраты и тесты для учащихся.</span><span class="sxs-lookup"><span data-stu-id="b882d-104">The Assignments and Grades features in Teams for Education allow educators to assign tasks, work, or quizzes to their students.</span></span> <span data-ttu-id="b882d-105">Преподаватели могут управлять временными шкалами назначения, инструкциями, добавить ресурсы для включения, оценить с раздел и многое другое.</span><span class="sxs-lookup"><span data-stu-id="b882d-105">Educators can manage assignment timelines, instructions, add resources to turn in, grade with rubrics, and more.</span></span> <span data-ttu-id="b882d-106">Кроме того, они могут отслеживать ход выполнения занятий и отдельных учащихся на вкладке оценки.</span><span class="sxs-lookup"><span data-stu-id="b882d-106">They can also track class and individual student progress in the Grades tab.</span></span>

<span data-ttu-id="b882d-107">[Ознакомьтесь с дополнительными сведениями о назначениях и оценках в Teams для образовательных учреждений](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span><span class="sxs-lookup"><span data-stu-id="b882d-107">[Learn more about Assignments and Grades in Teams for Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="b882d-108">Подробные сведения о назначениях групп на разных платформах можно найти в разделе [функции групп на платформе](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="b882d-108">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b882d-109">Интеграция назначений в центре администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b882d-109">Assignments integrations in the Microsoft Teams admin center</span></span>

<span data-ttu-id="b882d-110">С помощью параметров администратора в центре администрирования Microsoft Teams вы можете включать и отключать функции преподавателей в Организации и их учащихся.</span><span class="sxs-lookup"><span data-stu-id="b882d-110">Using the admin settings in the Microsoft Teams admin center, you can turn features on or off for educators within your organization and their students.</span></span> <span data-ttu-id="b882d-111">Ниже указаны параметры, связанные с назначениями.</span><span class="sxs-lookup"><span data-stu-id="b882d-111">The following are settings related to Assignments:</span></span>

<span data-ttu-id="b882d-112"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="b882d-112"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="b882d-113">Еженедельная сводка по электронной почте опекунов</span><span class="sxs-lookup"><span data-stu-id="b882d-113">Weekly guardian email digest</span></span>


<span data-ttu-id="b882d-114">Сообщения в опекунах отправляются каждому из выходных в родительский или опекун.</span><span class="sxs-lookup"><span data-stu-id="b882d-114">Guardian emails are sent each weekend to parents or guardians.</span></span> <span data-ttu-id="b882d-115">В сообщении электронной почты содержатся сведения о назначениях за предыдущие недели и на предстоящую неделю.</span><span class="sxs-lookup"><span data-stu-id="b882d-115">The email contains information about assignments from the previous week and for the upcoming week.</span></span> <span data-ttu-id="b882d-116">Родительский элемент и синхронизация с опекуном можно настроить с помощью [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync).</span><span class="sxs-lookup"><span data-stu-id="b882d-116">The Parent and Guardian Sync can be setup using [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync).</span></span>

1. <span data-ttu-id="b882d-117">Импорт родительских контактных данных через родительские и Опекунную синхронизацию в SDS.</span><span class="sxs-lookup"><span data-stu-id="b882d-117">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="b882d-118">Инструкции по включению родительских и Опекунных синхронизаций содержатся в разделе [Включение синхронизации родительских и опекунов](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span><span class="sxs-lookup"><span data-stu-id="b882d-118">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="b882d-119">Включите параметр опекуна в центре администрирования Microsoft Teams, так как этот параметр отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b882d-119">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="b882d-120">Это позволит преподавателям отправлять еженедельные дайджесты.</span><span class="sxs-lookup"><span data-stu-id="b882d-120">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b882d-121">Преподаватели могут отказаться от дайджеста, отменив выбор параметра в собственной группе личного класса (**Параметры назначения > родительских и опекунных сообщений**).</span><span class="sxs-lookup"><span data-stu-id="b882d-121">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="b882d-122">Чтобы убедиться в том, что родительские элементы получат сообщение электронной почты, должны быть истинными три следующих элемента:</span><span class="sxs-lookup"><span data-stu-id="b882d-122">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="b882d-123">Адрес электронной почты, прикрепленный к профилю учащихся в SDS и пометил его как _родительский элемент_ или _опекун_.</span><span class="sxs-lookup"><span data-stu-id="b882d-123">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="b882d-124">Дополнительные сведения можно найти в разделе [Формат файла синхронизации родительских и опекунов](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span><span class="sxs-lookup"><span data-stu-id="b882d-124">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="b882d-125">Учащиеся принадлежат по крайней мере одному классу, в котором в [параметрах назначений](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)не отключены преподаватели по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="b882d-125">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="b882d-126">В сообщениях электронной почты будут содержаться сведения о назначениях, у которых Дата выполнения указана на предыдущей неделе или на предстоящей неделе.</span><span class="sxs-lookup"><span data-stu-id="b882d-126">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="b882d-127">Параметр по умолчанию для этой функции **выключен.**</span><span class="sxs-lookup"><span data-stu-id="b882d-127">Default setting for this feature is - **Off**.</span></span>


<span data-ttu-id="b882d-128"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="b882d-128"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="b882d-129">MakeCode</span><span class="sxs-lookup"><span data-stu-id="b882d-129">MakeCode</span></span>
<span data-ttu-id="b882d-130">Microsoft MakeCode — это основанная на блоках платформа кодирования, благодаря которой компьютерному науку выдается жизнь для всех учащихся.</span><span class="sxs-lookup"><span data-stu-id="b882d-130">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="b882d-131">MakeCode — это продукт Microsoft, в соответствии с [условиями использования](https://go.microsoft.com/fwlink/?LinkID=206977) и политикой [конфиденциальности](https://go.microsoft.com/fwlink/?LinkId=521839) корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b882d-131">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="b882d-132">Параметр по умолчанию для этой функции **выключен.**</span><span class="sxs-lookup"><span data-stu-id="b882d-132">Default setting for this feature is - **Off**.</span></span>

<span data-ttu-id="b882d-133">Чтобы включить назначение MakeCode в Teams, перейдите в **центр администрирования Teams**, перейдите в раздел " **назначения** " и установите переключатель MakeCode в положение **вкл**.</span><span class="sxs-lookup"><span data-stu-id="b882d-133">To enable MakeCode assignments in Teams, go to the **Teams Admin Center**, navigate to the **Assignments** section, and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="b882d-134">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b882d-134">Click **Save**.</span></span> <span data-ttu-id="b882d-135">Чтобы эти параметры вступили в силу, подождите несколько часов.</span><span class="sxs-lookup"><span data-stu-id="b882d-135">Allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="b882d-136">Дополнительные сведения о том, как работает эта функция, можно найти в этом [видеоролике](https://makecode.com/blog/teams/teams-assignments).</span><span class="sxs-lookup"><span data-stu-id="b882d-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="b882d-137">Дополнительные [сведения о MakeCode](https://aka.ms/makecode).</span><span class="sxs-lookup"><span data-stu-id="b882d-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="b882d-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="b882d-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="b882d-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="b882d-139">Turnitin</span></span>

<span data-ttu-id="b882d-140">[Turnitin](https://www.turnitin.com/) является службой проверки целостности академических учреждений.</span><span class="sxs-lookup"><span data-stu-id="b882d-140">[Turnitin](https://www.turnitin.com/) is an academic integrity service.</span></span> <span data-ttu-id="b882d-141">Это сторонний продукт или услуга, которым подпадают свои условия и правила конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="b882d-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="b882d-142">Вы несете ответственность за использование каких-либо продуктов и услуг сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="b882d-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="b882d-143">Параметр по умолчанию для этой функции **выключен...**</span><span class="sxs-lookup"><span data-stu-id="b882d-143">Default setting for this feature is - **Off**..</span></span>

<span data-ttu-id="b882d-144">Чтобы включить Turnitin для своей организации, вам понадобится подписка на Turnitin.</span><span class="sxs-lookup"><span data-stu-id="b882d-144">To enable Turnitin for your organization, you will need a Turnitin subscription.</span></span> <span data-ttu-id="b882d-145">Затем вы можете ввести следующие данные, которые можно найти в консоли администрирования Turnitin:</span><span class="sxs-lookup"><span data-stu-id="b882d-145">Then you can input the following information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="b882d-146">**TurnitinApiKey**: идентификатор GUID 32, который находится на консоли администрирования в разделе Интеграция.</span><span class="sxs-lookup"><span data-stu-id="b882d-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="b882d-147">**TurnitinApiUrl**: URL-адрес вашей консоли администратора Turnitin.</span><span class="sxs-lookup"><span data-stu-id="b882d-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="b882d-148">Вот несколько инструкций, которые помогут вам получить эти сведения.</span><span class="sxs-lookup"><span data-stu-id="b882d-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="b882d-149">**TurnitinApiUrl** — адрес узла консоли администрирования.</span><span class="sxs-lookup"><span data-stu-id="b882d-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="b882d-150">Образом `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="b882d-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="b882d-151">На консоли администрирования вы можете создать интеграцию и ключ API, связанный с интеграцией.</span><span class="sxs-lookup"><span data-stu-id="b882d-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="b882d-152">В меню сбоку выберите пункт **Интеграция** , а затем — пункт **добавить интеграцию** и присвойте имя интеграции.</span><span class="sxs-lookup"><span data-stu-id="b882d-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![Снимок экрана, демонстрирующий Добавление новой интеграции](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="b882d-154">**TurnitinApiKey** будет предоставлен вам после того, как вы подпишитесь на запросы.</span><span class="sxs-lookup"><span data-stu-id="b882d-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="b882d-155">Скопируйте ключ API и вставьте его в центр администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b882d-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="b882d-156">Это единственный момент, когда вы можете просмотреть ключ.</span><span class="sxs-lookup"><span data-stu-id="b882d-156">This is the only time you can view the key.</span></span>

![Снимок экрана, на котором показано, как копировать ключ API](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="b882d-158">При нажатии кнопки " **сохранить** " в центре администрирования для этого параметра подождите, пока эти параметры вступят в силу в течение нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="b882d-158">Upon clicking the **Save** button in the admin center for this setting, allow a few hours for these settings to take effect.</span></span>

