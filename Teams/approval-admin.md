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
ms.openlocfilehash: c71f08840ffa9c41622d07376933c14a7ae6b493
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2021
ms.locfileid: "52129798"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="197c9-103">Доступность приложения "Утверждения" Teams</span><span class="sxs-lookup"><span data-stu-id="197c9-103">Teams Approvals app availability</span></span>

<span data-ttu-id="197c9-104">Приложение "Утверждения" доступно в качестве персонального приложения для всех пользователей Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="197c9-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="197c9-105">Приложение "Утверждения" обеспечивает простой способ обеспечения аудита, соответствия требованиям, подотчетности и рабочих процессов как для структурированных, так и для неструктурированных утверждений в Teams.</span><span class="sxs-lookup"><span data-stu-id="197c9-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![изображение приложения "Утверждения"](media/approvals-selection.png)

<span data-ttu-id="197c9-107">Пользователи могут закрепить приложение "Утверждения" в строке меню</span><span class="sxs-lookup"><span data-stu-id="197c9-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![изображение приложения "Утверждения" с функцией закрепления](media/approvalApp-pin.png)

<span data-ttu-id="197c9-109">Первое утверждение, созданное в приложении "Утверждения", станет сигналом к подготовке решения для утверждений в заданной по умолчанию среде Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="197c9-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="197c9-110">Утверждения, созданные в приложении "Утверждения", хранятся в заданной по умолчанию среде CDS.</span><span class="sxs-lookup"><span data-stu-id="197c9-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="197c9-111">В этой статье содержится информация о требованиях и ролях приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="197c9-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="197c9-112">Эта функция еще не выпущена для пользователей облако сообщества для государственных организаций (GCC), облако сообщества для государственных организаций high (GCCH) и Department of Defense (DOD).</span><span class="sxs-lookup"><span data-stu-id="197c9-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="197c9-113">Необходимые разрешения и лицензии</span><span class="sxs-lookup"><span data-stu-id="197c9-113">Required permissions and licenses</span></span>

<span data-ttu-id="197c9-114">Для использования приложения "Утверждения" вам необходимы перечисленные ниже разрешения.</span><span class="sxs-lookup"><span data-stu-id="197c9-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="197c9-115">Разрешения на создание базы данных Microsoft CDS.</span><span class="sxs-lookup"><span data-stu-id="197c9-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="197c9-116">Учетная запись [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="197c9-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="197c9-117">Роль администратора в целевой среде</span><span class="sxs-lookup"><span data-stu-id="197c9-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="197c9-118">Лицензия на [Power Automate](/power-automate/get-started-approvals), Office 365 или Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="197c9-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="197c9-119">Хранилище CDS</span><span class="sxs-lookup"><span data-stu-id="197c9-119">Storage with CDS</span></span>

<span data-ttu-id="197c9-120">Common Data Model (CDM) — это язык общих данных, используемый в приложениях для бизнеса и аналитики в CDS.</span><span class="sxs-lookup"><span data-stu-id="197c9-120">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="197c9-121">Он состоит из набора стандартизованных расширяемых схем данных, публикуемых корпорацией Майкрософт и ее партнерами, и позволяет поддерживать согласованность данных и их значение во всех приложениях и бизнес-процессах.</span><span class="sxs-lookup"><span data-stu-id="197c9-121">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="197c9-122">Подробнее о [языке Common Data Model Microsoft Power Platform](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="197c9-122">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="197c9-123">Подробнее о рабочем процессе [утверждений](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="197c9-123">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="197c9-124">Разрешения приложения "Утверждения" Teams</span><span class="sxs-lookup"><span data-stu-id="197c9-124">Approvals Teams app permissions</span></span>

<span data-ttu-id="197c9-125">Приложение "Утверждения" Teams позволяет получать доступ к перечисленным ниже возможностям.</span><span class="sxs-lookup"><span data-stu-id="197c9-125">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="197c9-126">Получение сообщений и данных, которые вы ему предоставляете.</span><span class="sxs-lookup"><span data-stu-id="197c9-126">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="197c9-127">Отправка вам сообщений и уведомлений.</span><span class="sxs-lookup"><span data-stu-id="197c9-127">Send you messages and notifications.</span></span>

- <span data-ttu-id="197c9-128">Отрисовка персональных приложений и диалогов без колонтитула Teams.</span><span class="sxs-lookup"><span data-stu-id="197c9-128">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="197c9-129">Получение доступа к информации вашего профиля, такой как ваше имя, адрес электронной почты, название компании и предпочтительный язык.</span><span class="sxs-lookup"><span data-stu-id="197c9-129">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="197c9-130">Получение сообщений и данных, которые участники команды предоставляют ему в канале.</span><span class="sxs-lookup"><span data-stu-id="197c9-130">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="197c9-131">Отправка сообщений и уведомлений в канале.</span><span class="sxs-lookup"><span data-stu-id="197c9-131">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="197c9-132">Получение доступа к следующей информации о вашей команде:</span><span class="sxs-lookup"><span data-stu-id="197c9-132">Access your team's information:</span></span>
  - <span data-ttu-id="197c9-133">название команды</span><span class="sxs-lookup"><span data-stu-id="197c9-133">team name</span></span>
  - <span data-ttu-id="197c9-134">список каналов</span><span class="sxs-lookup"><span data-stu-id="197c9-134">channel list</span></span>
  - <span data-ttu-id="197c9-135">состав (имена и адреса электронной почты участников команды).</span><span class="sxs-lookup"><span data-stu-id="197c9-135">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="197c9-136">Использование информации о команде для контакта с ней.</span><span class="sxs-lookup"><span data-stu-id="197c9-136">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="197c9-137">Отключение приложения "Утверждения" в Teams</span><span class="sxs-lookup"><span data-stu-id="197c9-137">Disable the Approvals app</span></span>

<span data-ttu-id="197c9-138">Приложение "Утверждения" доступно по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="197c9-138">The Approvals app is available by default.</span></span> <span data-ttu-id="197c9-139">Вы можете отключить его в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="197c9-139">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="197c9-140">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="197c9-140">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="197c9-141">Разверните раздел **Приложения Teams** и выберите **Управление приложениями**.</span><span class="sxs-lookup"><span data-stu-id="197c9-141">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="197c9-142">Выполните поиск приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="197c9-142">Search for the Approvals app.</span></span>

     ![изображение навигации в Центре администрирования с выделенными элементами "Приложения Teams" > "Управление приложениями"](media/manage-approval-apps.png)

  4. <span data-ttu-id="197c9-144">Выберите "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="197c9-144">Select Approvals.</span></span>

  5. <span data-ttu-id="197c9-145">Выберите положение переключателя, соответствующее отключению приложения для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="197c9-145">Select the toggle to disable the app for your organization.</span></span>

     ![изображение сведений о приложении "Утверждения"](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="197c9-147">Политика хранения</span><span class="sxs-lookup"><span data-stu-id="197c9-147">Retention policy</span></span>

<span data-ttu-id="197c9-148">Утверждения, созданные в приложении "Утверждения", хранятся в заданной по умолчанию среде CDS, которая пока не поддерживает создание резервных копий.</span><span class="sxs-lookup"><span data-stu-id="197c9-148">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="197c9-149">Подробнее на тему [Создание резервных копий и восстановление среды — Power Platform \| Документация Майкрософт](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="197c9-149">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="197c9-150">Аудит</span><span class="sxs-lookup"><span data-stu-id="197c9-150">Auditing</span></span>

<span data-ttu-id="197c9-151">Приложение "Утверждения" ведет журнал событий аудита в Центре безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="197c9-151">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="197c9-152">Вы можете просмотреть этот журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="197c9-152">You can view the audit log.</span></span>

1. <span data-ttu-id="197c9-153">Перейдите в Центр соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="197c9-153">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="197c9-154">Зайдите в раздел **Аудит**.</span><span class="sxs-lookup"><span data-stu-id="197c9-154">Select the **Audit** section.</span></span>

3. <span data-ttu-id="197c9-155">Выполните поиск в секции **Действия в Microsoft Teams, связанные с утверждениями**.</span><span class="sxs-lookup"><span data-stu-id="197c9-155">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="197c9-156">Вы можете выполнять поиск по перечисленным ниже действиям.</span><span class="sxs-lookup"><span data-stu-id="197c9-156">You can search for the following activities:</span></span>

- <span data-ttu-id="197c9-157">Создание запроса на утверждение</span><span class="sxs-lookup"><span data-stu-id="197c9-157">Create new approval request</span></span>

- <span data-ttu-id="197c9-158">Просмотр сведений о запросе на утверждение</span><span class="sxs-lookup"><span data-stu-id="197c9-158">View approval request details</span></span>

- <span data-ttu-id="197c9-159">Утвержденный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="197c9-159">Approved approval request</span></span>

- <span data-ttu-id="197c9-160">Отклоненный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="197c9-160">Rejected approval request</span></span>

- <span data-ttu-id="197c9-161">Отмененный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="197c9-161">Canceled approval request</span></span>

- <span data-ttu-id="197c9-162">Общий запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="197c9-162">Shared approval request</span></span>

- <span data-ttu-id="197c9-163">Файл, вложенный в запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="197c9-163">File attached to approval request</span></span>

- <span data-ttu-id="197c9-164">Повторно назначенный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="197c9-164">Reassigned approval request</span></span>

- <span data-ttu-id="197c9-165">Добавленная цифровая подпись к запросу на утверждение</span><span class="sxs-lookup"><span data-stu-id="197c9-165">Added e-signature to approval request</span></span>

- <span data-ttu-id="197c9-166">Просмотр сведений о запросе электронной подписи</span><span class="sxs-lookup"><span data-stu-id="197c9-166">Viewed e-signature request details</span></span>

- <span data-ttu-id="197c9-167">Просмотренное запрос на электронную подпись</span><span class="sxs-lookup"><span data-stu-id="197c9-167">Reviewed e-signature request</span></span>

- <span data-ttu-id="197c9-168">Отменен запрос на электронную подпись</span><span class="sxs-lookup"><span data-stu-id="197c9-168">Canceled e-signature request</span></span>

<span data-ttu-id="197c9-169">Для доступа к другим данным аудита утверждений в рамках Flow включите и настройте аудит в заданной по умолчанию среде для главных элементов, связанных с утверждениями: "утверждение", "запрос на утверждение" и "ответ на запрос на утверждение".</span><span class="sxs-lookup"><span data-stu-id="197c9-169">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="197c9-170">Операции создания, обновления и удаления являются подлежащими аудиту событиями в записях приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="197c9-170">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="197c9-171">Подробнее на тему [Аудит данных и действий пользователей для обеспечения безопасности и соответствия требованиям — Power Platform \| Документация Майкрософт](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="197c9-171">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="197c9-172">Можно выполнить дополнительную настройку аудита в [Центре безопасности и соответствия требованиям Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="197c9-172">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="197c9-173">Чтобы воспользоваться предварительно настроенными отчетами, войдите в Центр безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="197c9-173">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="197c9-174">Выберите **Поиск и исследование**.</span><span class="sxs-lookup"><span data-stu-id="197c9-174">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="197c9-175">Выполните поиск в журнале аудита и выберите вкладку **Действия в Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="197c9-175">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="197c9-176">Подробнее на тему [Microsoft Dataverse и ведение журнала действий в приложениях на основе моделей — Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="197c9-176">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="197c9-177">Безопасность</span><span class="sxs-lookup"><span data-stu-id="197c9-177">Security</span></span>

<span data-ttu-id="197c9-178">В приложении "Утверждения" Teams пользователи могут создавать утверждения, а также просматривать отправленные и полученные утверждения.</span><span class="sxs-lookup"><span data-stu-id="197c9-178">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="197c9-179">Пользователи не имеют доступа к утверждениям, созданным другими пользователями, если не указаны в качестве адресата или наблюдателя в соответствующем запросе.</span><span class="sxs-lookup"><span data-stu-id="197c9-179">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="197c9-180">Пользователю назначается роль наблюдателя запроса, если он является участником чата или канала, где было создано утверждение.</span><span class="sxs-lookup"><span data-stu-id="197c9-180">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="197c9-181">У него нет возможности совершать действия в отношении запроса, если при создании утверждения ему не была присвоена соответствующая роль.</span><span class="sxs-lookup"><span data-stu-id="197c9-181">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="197c9-182">Интеграция с электронной подписью "Утверждения"</span><span class="sxs-lookup"><span data-stu-id="197c9-182">Approvals e-signature integration</span></span>

<span data-ttu-id="197c9-183">Утверждения электронной подписи, созданные в приложении "Утверждения", хранятся в облачной среде выбранного поставщика.</span><span class="sxs-lookup"><span data-stu-id="197c9-183">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="197c9-184">Дополнительные сведения о хранилище в рамках соглашения с электронной подписью можно получить в документации выбранного поставщика.</span><span class="sxs-lookup"><span data-stu-id="197c9-184">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="197c9-185">Чтобы использовать функцию электронной подписи в приложении "Утверждения", вам нужны следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="197c9-185">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="197c9-186">Лицензия для конкретного поставщика электронной подписи, который вы выбираете.</span><span class="sxs-lookup"><span data-stu-id="197c9-186">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="197c9-187">Чтобы получить лицензию для своей организации, необходимо перейти на сайт поставщика.</span><span class="sxs-lookup"><span data-stu-id="197c9-187">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="197c9-188">Для функций работы с электронной подписью "Утверждения" партнеры по подписи сторонних разработчиков по умолчанию отображаются в Teams "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="197c9-188">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="197c9-189">Вы можете отключить определенные поставщики электронной подписи, задав параметры приложения в Teams центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="197c9-189">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="197c9-190">В центре Teams администрирования в **области** Управление приложениями выберите приложение **"Утверждения"** и Параметры . </span><span class="sxs-lookup"><span data-stu-id="197c9-190">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="197c9-191">Каждый поставщик электронной подписи по умолчанию имеет для него значение в положении "вкл." (справа).</span><span class="sxs-lookup"><span data-stu-id="197c9-191">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="197c9-192">Чтобы отключить определенного поставщика электронной подписи, перевиньте его влево.</span><span class="sxs-lookup"><span data-stu-id="197c9-192">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="197c9-193">Если администратор Teams отключает поставщика, конечные пользователи не будут видеть его при создании утверждения.</span><span class="sxs-lookup"><span data-stu-id="197c9-193">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="197c9-194">Кроме того, конечные пользователи не смогут просматривать запросы на электронную подпись, сделанные с этим поставщиком.</span><span class="sxs-lookup"><span data-stu-id="197c9-194">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="197c9-195">Утверждения электронной подписи, созданные в приложении "Утверждения", хранятся в облаке выбранного поставщика.</span><span class="sxs-lookup"><span data-stu-id="197c9-195">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="197c9-196">Поэтому для экспорта данных об электронных подписях необходимо перейти на сайт поставщика.</span><span class="sxs-lookup"><span data-stu-id="197c9-196">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="197c9-197">Обратитесь к документации поставщика об экспорте и хранении этих соглашений.</span><span class="sxs-lookup"><span data-stu-id="197c9-197">Refer to the provider's documentation about export and retention of these agreements.</span></span>
