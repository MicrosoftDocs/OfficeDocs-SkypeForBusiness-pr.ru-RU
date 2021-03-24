---
title: Доступность приложения "Утверждения" в Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Узнайте о доступности приложения "Утверждения" в Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4235232a9d74b4583ecaed19b68ff87de982085c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103015"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="60f9a-103">Доступность приложения "Утверждения" Teams</span><span class="sxs-lookup"><span data-stu-id="60f9a-103">Teams Approvals app availability</span></span>

<span data-ttu-id="60f9a-104">Приложение "Утверждения" доступно в качестве персонального приложения для всех пользователей Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="60f9a-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="60f9a-105">Приложение "Утверждения" обеспечивает простой способ обеспечения аудита, соответствия требованиям, подотчетности и рабочих процессов как для структурированных, так и для неструктурированных утверждений в Teams.</span><span class="sxs-lookup"><span data-stu-id="60f9a-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![изображение приложения "Утверждения"](media/approvals-selection.png)

<span data-ttu-id="60f9a-107">Пользователи могут закрепить приложение "Утверждения" в строке меню</span><span class="sxs-lookup"><span data-stu-id="60f9a-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![изображение приложения "Утверждения" с функцией закрепления](media/approvalApp-pin.png)

<span data-ttu-id="60f9a-109">Первое утверждение, созданное в приложении "Утверждения", станет сигналом к подготовке решения для утверждений в заданной по умолчанию среде Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="60f9a-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="60f9a-110">Утверждения, созданные в приложении "Утверждения", хранятся в заданной по умолчанию среде CDS.</span><span class="sxs-lookup"><span data-stu-id="60f9a-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="60f9a-111">В этой статье содержится информация о требованиях и ролях приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="60f9a-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="60f9a-112">Необходимые разрешения и лицензии</span><span class="sxs-lookup"><span data-stu-id="60f9a-112">Required permissions and licenses</span></span>

<span data-ttu-id="60f9a-113">Для использования приложения "Утверждения" вам необходимы перечисленные ниже разрешения.</span><span class="sxs-lookup"><span data-stu-id="60f9a-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="60f9a-114">Разрешения на создание базы данных Microsoft CDS.</span><span class="sxs-lookup"><span data-stu-id="60f9a-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="60f9a-115">Учетная запись [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="60f9a-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="60f9a-116">Роль администратора в целевой среде</span><span class="sxs-lookup"><span data-stu-id="60f9a-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="60f9a-117">Лицензия на [Power Automate](/power-automate/get-started-approvals), Office 365 или Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="60f9a-117">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="60f9a-118">Хранилище CDS</span><span class="sxs-lookup"><span data-stu-id="60f9a-118">Storage with CDS</span></span>

<span data-ttu-id="60f9a-119">Common Data Model (CDM) — это язык общих данных, используемый в приложениях для бизнеса и аналитики в CDS.</span><span class="sxs-lookup"><span data-stu-id="60f9a-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="60f9a-120">Он состоит из набора стандартизованных расширяемых схем данных, публикуемых корпорацией Майкрософт и ее партнерами, и позволяет поддерживать согласованность данных и их значение во всех приложениях и бизнес-процессах.</span><span class="sxs-lookup"><span data-stu-id="60f9a-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="60f9a-121">Подробнее о [языке Common Data Model Microsoft Power Platform](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="60f9a-121">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="60f9a-122">Подробнее о рабочем процессе [утверждений](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="60f9a-122">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="60f9a-123">Разрешения приложения "Утверждения" Teams</span><span class="sxs-lookup"><span data-stu-id="60f9a-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="60f9a-124">Приложение "Утверждения" Teams позволяет получать доступ к перечисленным ниже возможностям.</span><span class="sxs-lookup"><span data-stu-id="60f9a-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="60f9a-125">Получение сообщений и данных, которые вы ему предоставляете.</span><span class="sxs-lookup"><span data-stu-id="60f9a-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="60f9a-126">Отправка вам сообщений и уведомлений.</span><span class="sxs-lookup"><span data-stu-id="60f9a-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="60f9a-127">Отрисовка персональных приложений и диалогов без колонтитула Teams.</span><span class="sxs-lookup"><span data-stu-id="60f9a-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="60f9a-128">Получение доступа к информации вашего профиля, такой как ваше имя, адрес электронной почты, название компании и предпочтительный язык.</span><span class="sxs-lookup"><span data-stu-id="60f9a-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="60f9a-129">Получение сообщений и данных, которые участники команды предоставляют ему в канале.</span><span class="sxs-lookup"><span data-stu-id="60f9a-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="60f9a-130">Отправка сообщений и уведомлений в канале.</span><span class="sxs-lookup"><span data-stu-id="60f9a-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="60f9a-131">Получение доступа к следующей информации о вашей команде:</span><span class="sxs-lookup"><span data-stu-id="60f9a-131">Access your team's information:</span></span>
  - <span data-ttu-id="60f9a-132">название команды</span><span class="sxs-lookup"><span data-stu-id="60f9a-132">team name</span></span>
  - <span data-ttu-id="60f9a-133">список каналов</span><span class="sxs-lookup"><span data-stu-id="60f9a-133">channel list</span></span>
  - <span data-ttu-id="60f9a-134">состав (имена и адреса электронной почты участников команды).</span><span class="sxs-lookup"><span data-stu-id="60f9a-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="60f9a-135">Использование информации о команде для контакта с ней.</span><span class="sxs-lookup"><span data-stu-id="60f9a-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="60f9a-136">Отключение приложения "Утверждения" в Teams</span><span class="sxs-lookup"><span data-stu-id="60f9a-136">Disable the Approvals app</span></span>

<span data-ttu-id="60f9a-137">Приложение "Утверждения" доступно по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="60f9a-137">The Approvals app is available by default.</span></span> <span data-ttu-id="60f9a-138">Вы можете отключить его в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="60f9a-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="60f9a-139">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="60f9a-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="60f9a-140">Разверните раздел **Приложения Teams** и выберите **Управление приложениями**.</span><span class="sxs-lookup"><span data-stu-id="60f9a-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="60f9a-141">Выполните поиск приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="60f9a-141">Search for the Approvals app.</span></span>

![изображение навигации в Центре администрирования с выделенными элементами "Приложения Teams" > "Управление приложениями"](media/manage-approval-apps.png)

  4. <span data-ttu-id="60f9a-143">Выберите "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="60f9a-143">Select Approvals.</span></span>

  5. <span data-ttu-id="60f9a-144">Выберите положение переключателя, соответствующее отключению приложения для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="60f9a-144">Select the toggle to disable the app for your organization.</span></span>

![изображение сведений о приложении "Утверждения"](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="60f9a-146">Политика хранения</span><span class="sxs-lookup"><span data-stu-id="60f9a-146">Retention policy</span></span>

<span data-ttu-id="60f9a-147">Утверждения, созданные в приложении "Утверждения", хранятся в заданной по умолчанию среде CDS, которая пока не поддерживает создание резервных копий.</span><span class="sxs-lookup"><span data-stu-id="60f9a-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="60f9a-148">Подробнее на тему [Создание резервных копий и восстановление среды — Power Platform \| Документация Майкрософт](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="60f9a-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="60f9a-149">Аудит</span><span class="sxs-lookup"><span data-stu-id="60f9a-149">Auditing</span></span>

<span data-ttu-id="60f9a-150">Приложение "Утверждения" ведет журнал событий аудита в Центре безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60f9a-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="60f9a-151">Вы можете просмотреть этот журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="60f9a-151">You can view the audit log.</span></span>

1. <span data-ttu-id="60f9a-152">Перейдите в Центр соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60f9a-152">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="60f9a-153">Зайдите в раздел **Аудит**.</span><span class="sxs-lookup"><span data-stu-id="60f9a-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="60f9a-154">Выполните поиск в секции **Действия в Microsoft Teams, связанные с утверждениями**.</span><span class="sxs-lookup"><span data-stu-id="60f9a-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="60f9a-155">Вы можете выполнять поиск по перечисленным ниже действиям.</span><span class="sxs-lookup"><span data-stu-id="60f9a-155">You can search for the following activities:</span></span>

- <span data-ttu-id="60f9a-156">Создание запроса на утверждение</span><span class="sxs-lookup"><span data-stu-id="60f9a-156">Create new approval request</span></span>

- <span data-ttu-id="60f9a-157">Просмотр сведений о запросе на утверждение</span><span class="sxs-lookup"><span data-stu-id="60f9a-157">View approval request details</span></span>

- <span data-ttu-id="60f9a-158">Утвержденный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="60f9a-158">Approved approval request</span></span>

- <span data-ttu-id="60f9a-159">Отклоненный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="60f9a-159">Rejected approval request</span></span>

- <span data-ttu-id="60f9a-160">Отмененный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="60f9a-160">Canceled approval request</span></span>

- <span data-ttu-id="60f9a-161">Общий запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="60f9a-161">Shared approval request</span></span>

- <span data-ttu-id="60f9a-162">Файл, вложенный в запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="60f9a-162">File attached to approval request</span></span>

- <span data-ttu-id="60f9a-163">Повторно назначенный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="60f9a-163">Reassigned approval request</span></span>

- <span data-ttu-id="60f9a-164">Добавленная цифровая подпись к запросу на утверждение</span><span class="sxs-lookup"><span data-stu-id="60f9a-164">Added e-signature to approval request</span></span>

<span data-ttu-id="60f9a-165">Для доступа к другим данным аудита утверждений в рамках Flow включите и настройте аудит в заданной по умолчанию среде для главных элементов, связанных с утверждениями: "утверждение", "запрос на утверждение" и "ответ на запрос на утверждение".</span><span class="sxs-lookup"><span data-stu-id="60f9a-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="60f9a-166">Операции создания, обновления и удаления являются подлежащими аудиту событиями в записях приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="60f9a-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="60f9a-167">Подробнее на тему [Аудит данных и действий пользователей для обеспечения безопасности и соответствия требованиям — Power Platform \| Документация Майкрософт](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="60f9a-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="60f9a-168">Можно выполнить дополнительную настройку аудита в [Центре безопасности и соответствия требованиям Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="60f9a-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="60f9a-169">Чтобы воспользоваться предварительно настроенными отчетами, войдите в Центр безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60f9a-169">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="60f9a-170">Выберите **Поиск и исследование**.</span><span class="sxs-lookup"><span data-stu-id="60f9a-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="60f9a-171">Выполните поиск в журнале аудита и выберите вкладку **Действия в Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="60f9a-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="60f9a-172">Подробнее на тему [Microsoft Dataverse и ведение журнала действий в приложениях на основе моделей — Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="60f9a-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="60f9a-173">Безопасность</span><span class="sxs-lookup"><span data-stu-id="60f9a-173">Security</span></span>

<span data-ttu-id="60f9a-174">В приложении "Утверждения" Teams пользователи могут создавать утверждения, а также просматривать отправленные и полученные утверждения.</span><span class="sxs-lookup"><span data-stu-id="60f9a-174">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="60f9a-175">Пользователи не имеют доступа к утверждениям, созданным другими пользователями, если не указаны в качестве адресата или наблюдателя в соответствующем запросе.</span><span class="sxs-lookup"><span data-stu-id="60f9a-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="60f9a-176">Пользователю назначается роль наблюдателя запроса, если он является участником чата или канала, где было создано утверждение.</span><span class="sxs-lookup"><span data-stu-id="60f9a-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="60f9a-177">У него нет возможности совершать действия в отношении запроса, если при создании утверждения ему не была присвоена соответствующая роль.</span><span class="sxs-lookup"><span data-stu-id="60f9a-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>