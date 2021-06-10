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
description: Узнайте, как управлять заданиями в Центре администрирования Microsoft Teams в Teams для образования.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 410f5d32dd8af4775639a080725cd5680b6a70c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121377"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="224e9-103">Задания в Teams для образовательных учреждений</span><span class="sxs-lookup"><span data-stu-id="224e9-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="224e9-104">Функции "Задания" и "Оценки" в Teams для образовательных учреждений позволяют преподавателям назначать своим учащимся задачи, задания и тесты.</span><span class="sxs-lookup"><span data-stu-id="224e9-104">The Assignments and Grades features in Teams for Education allow educators to assign tasks, work, or quizzes to their students.</span></span> <span data-ttu-id="224e9-105">Преподаватели могут управлять временными шкалами заданий, инструкциями, добавлять ресурсы для списания заданий, оценки с помощью рубрик и т. д.</span><span class="sxs-lookup"><span data-stu-id="224e9-105">Educators can manage assignment timelines, instructions, add resources to turn in, grade with rubrics, and more.</span></span> <span data-ttu-id="224e9-106">Они также могут отслеживать ход выполнения занятий и отдельных учащихся на вкладке Оценки.</span><span class="sxs-lookup"><span data-stu-id="224e9-106">They can also track class and individual student progress in the Grades tab.</span></span>

<span data-ttu-id="224e9-107">[Подробнее о заданиях и оценках можно узнать в Teams для образования](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span><span class="sxs-lookup"><span data-stu-id="224e9-107">[Learn more about Assignments and Grades in Teams for Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="224e9-108">Подробные сведения о Teams заданиях на разных платформах см. в Teams [по платформам.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="224e9-108">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="224e9-109">Интеграция заданий в Центре Microsoft Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="224e9-109">Assignments integrations in the Microsoft Teams admin center</span></span>

<span data-ttu-id="224e9-110">С помощью параметров администратора в Центре Microsoft Teams вы можете включить или отключить функции для преподавателей в организации и их учащихся.</span><span class="sxs-lookup"><span data-stu-id="224e9-110">Using the admin settings in the Microsoft Teams admin center, you can turn features on or off for educators within your organization and their students.</span></span> <span data-ttu-id="224e9-111">Ниже параметров, связанных с заданиями:</span><span class="sxs-lookup"><span data-stu-id="224e9-111">The following are settings related to Assignments:</span></span>

<span data-ttu-id="224e9-112"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="224e9-112"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="224e9-113">Еженедельный электронный дайджест для опекунов</span><span class="sxs-lookup"><span data-stu-id="224e9-113">Weekly guardian email digest</span></span>


<span data-ttu-id="224e9-114">Письма опекунов отправляются родителям или опекунам каждые выходные.</span><span class="sxs-lookup"><span data-stu-id="224e9-114">Guardian emails are sent each weekend to parents or guardians.</span></span> <span data-ttu-id="224e9-115">Сообщение электронной почты содержит сведения о заданиях за предыдущую и предстоящую неделю.</span><span class="sxs-lookup"><span data-stu-id="224e9-115">The email contains information about assignments from the previous week and for the upcoming week.</span></span> <span data-ttu-id="224e9-116">Синхронизацию для родителей и опекунов можно настроить с помощью [Синхронизация сведений о школе.](/schooldatasync/parent-contact-sync)</span><span class="sxs-lookup"><span data-stu-id="224e9-116">The Parent and Guardian Sync can be setup using [School Data Sync](/schooldatasync/parent-contact-sync).</span></span>

1. <span data-ttu-id="224e9-117">Импортируйте контактные данные родителей с помощью синхронизации для родителей и опекунов в SDS.</span><span class="sxs-lookup"><span data-stu-id="224e9-117">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="224e9-118">Инструкции по включению синхронизации для родителей и опекунов см. в этой [ссылке.](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)</span><span class="sxs-lookup"><span data-stu-id="224e9-118">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="224e9-119">Включите параметр Опекун в центре Microsoft Teams, так как этот параметр отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="224e9-119">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="224e9-120">Это позволит преподавателям отправлять еженедельный дайджест.</span><span class="sxs-lookup"><span data-stu-id="224e9-120">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="224e9-121">Преподаватели могут отказаться от дайджеста, отобрав этот параметр в собственной группе класса (в Параметры > для родителей и **опекунов).**</span><span class="sxs-lookup"><span data-stu-id="224e9-121">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="224e9-122">Чтобы убедиться, что родители получат письмо, должны быть истинными следующие три пункта:</span><span class="sxs-lookup"><span data-stu-id="224e9-122">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="224e9-123">Адрес электронной почты, вложенный в профиль учащегося в SDS и помечен как _родительский или_ _опекун._</span><span class="sxs-lookup"><span data-stu-id="224e9-123">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="224e9-124">Подробные сведения см. в теме Формат файлов синхронизации для родителей [и опекунов.](/schooldatasync/parent-contact-sync-file-format)</span><span class="sxs-lookup"><span data-stu-id="224e9-124">For details, see [Parent and Guardian Sync File Format](/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="224e9-125">Учащиеся относятся хотя бы к одному классу, в котором преподаватели не отключили электронную почту в [параметрах задания.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)</span><span class="sxs-lookup"><span data-stu-id="224e9-125">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="224e9-126">Сообщения электронной почты будут содержать сведения о заданиях, срок выполнения которых был за предыдущую неделю или предстоящую неделю.</span><span class="sxs-lookup"><span data-stu-id="224e9-126">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="224e9-127">По умолчанию для этой функции заданной функцией заданная **функция выключена.**</span><span class="sxs-lookup"><span data-stu-id="224e9-127">Default setting for this feature is - **Off**.</span></span>


<span data-ttu-id="224e9-128"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="224e9-128"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="224e9-129">MakeCode</span><span class="sxs-lookup"><span data-stu-id="224e9-129">MakeCode</span></span>
<span data-ttu-id="224e9-130">Microsoft MakeCode — это платформа программирования с блокировкой, которая позволяет информатиковать всех учащихся.</span><span class="sxs-lookup"><span data-stu-id="224e9-130">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="224e9-131">MakeCode — это продукт Корпорации [](https://go.microsoft.com/fwlink/?LinkID=206977) Майкрософт, на который налагаются условия использования и политики [конфиденциальности](https://go.microsoft.com/fwlink/?LinkId=521839) корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="224e9-131">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="224e9-132">По умолчанию для этой функции заданной функцией заданная **функция выключена.**</span><span class="sxs-lookup"><span data-stu-id="224e9-132">Default setting for this feature is - **Off**.</span></span>

<span data-ttu-id="224e9-133">Чтобы включить задания MakeCode в Teams, перейдите в Центр администрирования **Teams**, перейдите в раздел Задания и включите параметр MakeCode вкл. .  </span><span class="sxs-lookup"><span data-stu-id="224e9-133">To enable MakeCode assignments in Teams, go to the **Teams Admin Center**, navigate to the **Assignments** section, and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="224e9-134">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="224e9-134">Click **Save**.</span></span> <span data-ttu-id="224e9-135">Чтобы эти параметры вступили в силу, в течение нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="224e9-135">Allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="224e9-136">Дополнительные сведения о том, как работает эта функция, см. в этом [видеоролике.](https://makecode.com/blog/teams/teams-assignments)</span><span class="sxs-lookup"><span data-stu-id="224e9-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="224e9-137">[Подробнее о MakeCode.](https://aka.ms/makecode)</span><span class="sxs-lookup"><span data-stu-id="224e9-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="224e9-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="224e9-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="224e9-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="224e9-139">Turnitin</span></span>

<span data-ttu-id="224e9-140">[Turnitin](https://www.turnitin.com/) — это служба целостности знаний.</span><span class="sxs-lookup"><span data-stu-id="224e9-140">[Turnitin](https://www.turnitin.com/) is an academic integrity service.</span></span> <span data-ttu-id="224e9-141">Это сторонний продукт или служба, на которые лагаются собственные условия и политика конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="224e9-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="224e9-142">Вы несете ответственность за использование сторонних продуктов и служб.</span><span class="sxs-lookup"><span data-stu-id="224e9-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="224e9-143">Значение по умолчанию для этой функции — **Отключено**..</span><span class="sxs-lookup"><span data-stu-id="224e9-143">Default setting for this feature is - **Off**..</span></span>

<span data-ttu-id="224e9-144">Чтобы включить Turnitin для организации, вам потребуется подписка на Turnitin.</span><span class="sxs-lookup"><span data-stu-id="224e9-144">To enable Turnitin for your organization, you will need a Turnitin subscription.</span></span> <span data-ttu-id="224e9-145">Затем вы можете ввести следующие сведения, которые можно найти в консоли администратора Turnitin:</span><span class="sxs-lookup"><span data-stu-id="224e9-145">Then you can input the following information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="224e9-146">**TurnitinApiKey:** GUID, 32-символ, который находится в консоли администрирования в области Интеграции.</span><span class="sxs-lookup"><span data-stu-id="224e9-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="224e9-147">**TurnitinApiUrl:** URL-адрес HTTPS консоли администратора Turnitin.</span><span class="sxs-lookup"><span data-stu-id="224e9-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="224e9-148">Вот несколько инструкций, которые помогут вам получить эти сведения.</span><span class="sxs-lookup"><span data-stu-id="224e9-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="224e9-149">**TurnitinApiUrl —** это адрес хоста консоли администратора.</span><span class="sxs-lookup"><span data-stu-id="224e9-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="224e9-150">Пример: `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="224e9-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="224e9-151">В консоли администратора можно создать интеграцию и ключ API, связанный с ней.</span><span class="sxs-lookup"><span data-stu-id="224e9-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="224e9-152">Выберите **Интеграции** в боковом меню, а затем выберите **Добавить интеграцию** и придайте интеграции имя.</span><span class="sxs-lookup"><span data-stu-id="224e9-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![Снимок экрана: добавление новой интеграции](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="224e9-154">**TurnitinApiKey** будет предоставлен вам после того, как вы следуйте этим запросам.</span><span class="sxs-lookup"><span data-stu-id="224e9-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="224e9-155">Скопируйте ключ API и вкопируйте его в Microsoft Teams центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="224e9-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="224e9-156">Это единственный раз, когда можно просмотреть ключ.</span><span class="sxs-lookup"><span data-stu-id="224e9-156">This is the only time you can view the key.</span></span>

![Снимок экрана: копирование ключа API](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="224e9-158">Нажимая **кнопку Сохранить** в Центре администрирования для этого параметра, в течение нескольких часов эти параметры вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="224e9-158">Upon clicking the **Save** button in the admin center for this setting, allow a few hours for these settings to take effect.</span></span>