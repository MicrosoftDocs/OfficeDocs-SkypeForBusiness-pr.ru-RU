---
title: Доступность приложения "Утверждения" в Teams
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
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
ms.openlocfilehash: 1e03ad5c562f7fd31599bbb86f08e411dfa4b415
ms.sourcegitcommit: fb87d64c6f98041a1da50cf4ef6ff54cdc8d1d29
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902573"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="25580-103">Доступность приложения "Утверждения" Teams</span><span class="sxs-lookup"><span data-stu-id="25580-103">Teams Approvals app availability</span></span>

<span data-ttu-id="25580-104">Приложение "Утверждения" доступно в качестве персонального приложения для всех пользователей Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="25580-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="25580-105">Приложение "Утверждения" обеспечивает простой способ обеспечения аудита, соответствия требованиям, подотчетности и рабочих процессов как для структурированных, так и для неструктурированных утверждений в Teams.</span><span class="sxs-lookup"><span data-stu-id="25580-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![изображение приложения "Утверждения"](media/approvals-selection.png)

<span data-ttu-id="25580-107">Пользователи могут закрепить приложение "Утверждения" в строке меню</span><span class="sxs-lookup"><span data-stu-id="25580-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![изображение приложения "Утверждения" с функцией закрепления](media/approvalApp-pin.png)

<span data-ttu-id="25580-109">Первое утверждение, созданное в приложении "Утверждения", станет сигналом к подготовке решения для утверждений в заданной по умолчанию среде Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="25580-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="25580-110">Утверждения, созданные в приложении "Утверждения", хранятся в заданной по умолчанию среде CDS.</span><span class="sxs-lookup"><span data-stu-id="25580-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="25580-111">В этой статье содержится информация о требованиях и ролях приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="25580-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="25580-112">Эта функция еще не выпущена для пользователей Government Community Cloud (GCC), Government Community Cloud High (GCCH) и Department of Defense (DOD).</span><span class="sxs-lookup"><span data-stu-id="25580-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="25580-113">Необходимые разрешения и лицензии</span><span class="sxs-lookup"><span data-stu-id="25580-113">Required permissions and licenses</span></span>

<span data-ttu-id="25580-114">Для использования приложения "Утверждения" вам необходимы перечисленные ниже разрешения.</span><span class="sxs-lookup"><span data-stu-id="25580-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="25580-115">Разрешения на создание базы данных Microsoft CDS.</span><span class="sxs-lookup"><span data-stu-id="25580-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="25580-116">Учетная запись [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="25580-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="25580-117">Роль администратора в целевой среде</span><span class="sxs-lookup"><span data-stu-id="25580-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="25580-118">Лицензия на [Power Automate](/power-automate/get-started-approvals), Office 365 или Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="25580-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="25580-119">Хранилище CDS</span><span class="sxs-lookup"><span data-stu-id="25580-119">Storage with CDS</span></span>

<span data-ttu-id="25580-120">Common Data Model (CDM) — это язык общих данных, используемый в приложениях для бизнеса и аналитики в CDS.</span><span class="sxs-lookup"><span data-stu-id="25580-120">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="25580-121">Он состоит из набора стандартизированных схем данных, опубликованных корпорацией Майкрософт и нашими партнерами, что обеспечивает согласованность данных и их значение в приложениях и бизнес-процессах.</span><span class="sxs-lookup"><span data-stu-id="25580-121">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners, that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="25580-122">Подробнее о [языке Common Data Model Microsoft Power Platform](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="25580-122">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="25580-123">Подробнее о рабочем процессе [утверждений](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="25580-123">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="25580-124">Разрешения приложения "Утверждения" Teams</span><span class="sxs-lookup"><span data-stu-id="25580-124">Approvals Teams app permissions</span></span>

<span data-ttu-id="25580-125">Приложение "Утверждения" Teams позволяет получать доступ к перечисленным ниже возможностям.</span><span class="sxs-lookup"><span data-stu-id="25580-125">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="25580-126">Получение сообщений и данных, которые вы ему предоставляете.</span><span class="sxs-lookup"><span data-stu-id="25580-126">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="25580-127">Отправка вам сообщений и уведомлений.</span><span class="sxs-lookup"><span data-stu-id="25580-127">Send you messages and notifications.</span></span>

- <span data-ttu-id="25580-128">Отрисовка персональных приложений и диалогов без колонтитула Teams.</span><span class="sxs-lookup"><span data-stu-id="25580-128">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="25580-129">Получение доступа к информации вашего профиля, такой как ваше имя, адрес электронной почты, название компании и предпочтительный язык.</span><span class="sxs-lookup"><span data-stu-id="25580-129">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="25580-130">Получение сообщений и данных, которые участники команды предоставляют ему в канале.</span><span class="sxs-lookup"><span data-stu-id="25580-130">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="25580-131">Отправка сообщений и уведомлений в канале.</span><span class="sxs-lookup"><span data-stu-id="25580-131">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="25580-132">Получение доступа к следующей информации о вашей команде:</span><span class="sxs-lookup"><span data-stu-id="25580-132">Access your team's information:</span></span>
  - <span data-ttu-id="25580-133">название команды</span><span class="sxs-lookup"><span data-stu-id="25580-133">team name</span></span>
  - <span data-ttu-id="25580-134">список каналов</span><span class="sxs-lookup"><span data-stu-id="25580-134">channel list</span></span>
  - <span data-ttu-id="25580-135">состав (имена и адреса электронной почты участников команды).</span><span class="sxs-lookup"><span data-stu-id="25580-135">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="25580-136">Использование информации о команде для контакта с ней.</span><span class="sxs-lookup"><span data-stu-id="25580-136">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="25580-137">Отключение приложения "Утверждения" в Teams</span><span class="sxs-lookup"><span data-stu-id="25580-137">Disable the Approvals app</span></span>

<span data-ttu-id="25580-138">Приложение "Утверждения" доступно по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="25580-138">The Approvals app is available by default.</span></span> <span data-ttu-id="25580-139">Вы можете отключить его в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="25580-139">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="25580-140">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="25580-140">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="25580-141">Разверните раздел **Приложения Teams** и выберите **Управление приложениями**.</span><span class="sxs-lookup"><span data-stu-id="25580-141">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="25580-142">Выполните поиск приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="25580-142">Search for the Approvals app.</span></span>

![изображение навигации в Центре администрирования с выделенными элементами "Приложения Teams" > "Управление приложениями"](media/manage-approval-apps.png)

  4. <span data-ttu-id="25580-144">Выберите "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="25580-144">Select Approvals.</span></span>

  5. <span data-ttu-id="25580-145">Выберите положение переключателя, соответствующее отключению приложения для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="25580-145">Select the toggle to disable the app for your organization.</span></span>

![изображение сведений о приложении "Утверждения"](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="25580-147">Политика хранения</span><span class="sxs-lookup"><span data-stu-id="25580-147">Retention policy</span></span>

<span data-ttu-id="25580-148">Утверждения, созданные в приложении "Утверждения", хранятся в заданной по умолчанию среде CDS, которая пока не поддерживает создание резервных копий.</span><span class="sxs-lookup"><span data-stu-id="25580-148">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="25580-149">Подробнее на тему [Создание резервных копий и восстановление среды — Power Platform \| Документация Майкрософт](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="25580-149">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="25580-150">Аудит</span><span class="sxs-lookup"><span data-stu-id="25580-150">Auditing</span></span>

<span data-ttu-id="25580-151">Приложение "Утверждения" ведет журнал событий аудита в Центре безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="25580-151">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="25580-152">Вы можете просмотреть этот журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="25580-152">You can view the audit log.</span></span>

1. <span data-ttu-id="25580-153">Перейдите в Центр соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="25580-153">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="25580-154">Зайдите в раздел **Аудит**.</span><span class="sxs-lookup"><span data-stu-id="25580-154">Select the **Audit** section.</span></span>

3. <span data-ttu-id="25580-155">Выполните поиск в секции **Действия в Microsoft Teams, связанные с утверждениями**.</span><span class="sxs-lookup"><span data-stu-id="25580-155">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="25580-156">Вы можете выполнять поиск по перечисленным ниже действиям.</span><span class="sxs-lookup"><span data-stu-id="25580-156">You can search for the following activities:</span></span>

- <span data-ttu-id="25580-157">Создание запроса на утверждение</span><span class="sxs-lookup"><span data-stu-id="25580-157">Create new approval request</span></span>

- <span data-ttu-id="25580-158">Просмотр сведений о запросе на утверждение</span><span class="sxs-lookup"><span data-stu-id="25580-158">View approval request details</span></span>

- <span data-ttu-id="25580-159">Утвержденный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="25580-159">Approved approval request</span></span>

- <span data-ttu-id="25580-160">Отклоненный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="25580-160">Rejected approval request</span></span>

- <span data-ttu-id="25580-161">Отмененный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="25580-161">Canceled approval request</span></span>

- <span data-ttu-id="25580-162">Общий запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="25580-162">Shared approval request</span></span>

- <span data-ttu-id="25580-163">Файл, вложенный в запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="25580-163">File attached to approval request</span></span>

- <span data-ttu-id="25580-164">Повторно назначенный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="25580-164">Reassigned approval request</span></span>

- <span data-ttu-id="25580-165">Добавленная цифровая подпись к запросу на утверждение</span><span class="sxs-lookup"><span data-stu-id="25580-165">Added e-signature to approval request</span></span>

<span data-ttu-id="25580-166">Для доступа к другим данным аудита утверждений в рамках Flow включите и настройте аудит в заданной по умолчанию среде для главных элементов, связанных с утверждениями: "утверждение", "запрос на утверждение" и "ответ на запрос на утверждение".</span><span class="sxs-lookup"><span data-stu-id="25580-166">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="25580-167">Операции создания, обновления и удаления являются подлежащими аудиту событиями в записях приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="25580-167">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="25580-168">Подробнее на тему [Аудит данных и действий пользователей для обеспечения безопасности и соответствия требованиям — Power Platform \| Документация Майкрософт](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="25580-168">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="25580-169">Можно выполнить дополнительную настройку аудита в [Центре безопасности и соответствия требованиям Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="25580-169">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="25580-170">Чтобы воспользоваться предварительно настроенными отчетами, войдите в Центр безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="25580-170">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="25580-171">Выберите **Поиск и исследование**.</span><span class="sxs-lookup"><span data-stu-id="25580-171">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="25580-172">Выполните поиск в журнале аудита и выберите вкладку **Действия в Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="25580-172">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="25580-173">Подробнее на тему [Microsoft Dataverse и ведение журнала действий в приложениях на основе моделей — Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="25580-173">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="25580-174">Безопасность</span><span class="sxs-lookup"><span data-stu-id="25580-174">Security</span></span>

<span data-ttu-id="25580-175">В приложении "Утверждения" Teams пользователи могут создавать утверждения, а также просматривать отправленные и полученные утверждения.</span><span class="sxs-lookup"><span data-stu-id="25580-175">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="25580-176">Пользователи не имеют доступа к утверждениям, созданным другими пользователями, если не указаны в качестве адресата или наблюдателя в соответствующем запросе.</span><span class="sxs-lookup"><span data-stu-id="25580-176">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="25580-177">Пользователю назначается роль наблюдателя запроса, если он является участником чата или канала, где было создано утверждение.</span><span class="sxs-lookup"><span data-stu-id="25580-177">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="25580-178">У него нет возможности совершать действия в отношении запроса, если при создании утверждения ему не была присвоена соответствующая роль.</span><span class="sxs-lookup"><span data-stu-id="25580-178">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>