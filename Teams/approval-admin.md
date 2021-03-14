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
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909523"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="11d24-103">Доступность приложения "Утверждения" Teams</span><span class="sxs-lookup"><span data-stu-id="11d24-103">Teams Approvals app availability</span></span>

<span data-ttu-id="11d24-104">Приложение "Утверждения" доступно в качестве персонального приложения для всех пользователей Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="11d24-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="11d24-105">Приложение "Утверждения" обеспечивает простой способ обеспечения аудита, соответствия требованиям, подотчетности и рабочих процессов как для структурированных, так и для неструктурированных утверждений в Teams.</span><span class="sxs-lookup"><span data-stu-id="11d24-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![изображение приложения "Утверждения"](media/approvals-selection.png)

<span data-ttu-id="11d24-107">Пользователи могут закрепить приложение "Утверждения" в строке меню</span><span class="sxs-lookup"><span data-stu-id="11d24-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![изображение приложения "Утверждения" с функцией закрепления](media/approvalApp-pin.png)

<span data-ttu-id="11d24-109">Первое утверждение, созданное в приложении "Утверждения", станет сигналом к подготовке решения для утверждений в заданной по умолчанию среде Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="11d24-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="11d24-110">Утверждения, созданные в приложении "Утверждения", хранятся в заданной по умолчанию среде CDS.</span><span class="sxs-lookup"><span data-stu-id="11d24-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="11d24-111">В этой статье содержится информация о требованиях и ролях приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="11d24-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="11d24-112">Необходимые разрешения и лицензии</span><span class="sxs-lookup"><span data-stu-id="11d24-112">Required permissions and licenses</span></span>

<span data-ttu-id="11d24-113">Для использования приложения "Утверждения" вам необходимы перечисленные ниже разрешения.</span><span class="sxs-lookup"><span data-stu-id="11d24-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="11d24-114">Разрешения на создание базы данных Microsoft CDS.</span><span class="sxs-lookup"><span data-stu-id="11d24-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="11d24-115">Учетная запись [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="11d24-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="11d24-116">Роль администратора в целевой среде</span><span class="sxs-lookup"><span data-stu-id="11d24-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="11d24-117">Лицензия на [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), Office 365 или Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="11d24-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="11d24-118">Хранилище CDS</span><span class="sxs-lookup"><span data-stu-id="11d24-118">Storage with CDS</span></span>

<span data-ttu-id="11d24-119">Common Data Model (CDM) — это язык общих данных, используемый в приложениях для бизнеса и аналитики в CDS.</span><span class="sxs-lookup"><span data-stu-id="11d24-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="11d24-120">Он состоит из набора стандартизованных расширяемых схем данных, публикуемых корпорацией Майкрософт и ее партнерами, и позволяет поддерживать согласованность данных и их значение во всех приложениях и бизнес-процессах.</span><span class="sxs-lookup"><span data-stu-id="11d24-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="11d24-121">Подробнее о [языке Common Data Model Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="11d24-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="11d24-122">Подробнее о рабочем процессе [утверждений](https://docs.microsoft.com/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="11d24-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="11d24-123">Разрешения приложения "Утверждения" Teams</span><span class="sxs-lookup"><span data-stu-id="11d24-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="11d24-124">Приложение "Утверждения" Teams позволяет получать доступ к перечисленным ниже возможностям.</span><span class="sxs-lookup"><span data-stu-id="11d24-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="11d24-125">Получение сообщений и данных, которые вы ему предоставляете.</span><span class="sxs-lookup"><span data-stu-id="11d24-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="11d24-126">Отправка вам сообщений и уведомлений.</span><span class="sxs-lookup"><span data-stu-id="11d24-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="11d24-127">Отрисовка персональных приложений и диалогов без колонтитула Teams.</span><span class="sxs-lookup"><span data-stu-id="11d24-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="11d24-128">Получение доступа к информации вашего профиля, такой как ваше имя, адрес электронной почты, название компании и предпочтительный язык.</span><span class="sxs-lookup"><span data-stu-id="11d24-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="11d24-129">Получение сообщений и данных, которые участники команды предоставляют ему в канале.</span><span class="sxs-lookup"><span data-stu-id="11d24-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="11d24-130">Отправка сообщений и уведомлений в канале.</span><span class="sxs-lookup"><span data-stu-id="11d24-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="11d24-131">Получение доступа к следующей информации о вашей команде:</span><span class="sxs-lookup"><span data-stu-id="11d24-131">Access your team's information:</span></span>
  - <span data-ttu-id="11d24-132">название команды</span><span class="sxs-lookup"><span data-stu-id="11d24-132">team name</span></span>
  - <span data-ttu-id="11d24-133">список каналов</span><span class="sxs-lookup"><span data-stu-id="11d24-133">channel list</span></span>
  - <span data-ttu-id="11d24-134">состав (имена и адреса электронной почты участников команды).</span><span class="sxs-lookup"><span data-stu-id="11d24-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="11d24-135">Использование информации о команде для контакта с ней.</span><span class="sxs-lookup"><span data-stu-id="11d24-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="11d24-136">Отключение приложения "Утверждения" в Teams</span><span class="sxs-lookup"><span data-stu-id="11d24-136">Disable the Approvals app</span></span>

<span data-ttu-id="11d24-137">Приложение "Утверждения" доступно по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="11d24-137">The Approvals app is available by default.</span></span> <span data-ttu-id="11d24-138">Вы можете отключить его в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="11d24-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="11d24-139">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="11d24-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="11d24-140">Разверните раздел **Приложения Teams** и выберите **Управление приложениями**.</span><span class="sxs-lookup"><span data-stu-id="11d24-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="11d24-141">Выполните поиск приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="11d24-141">Search for the Approvals app.</span></span>

![изображение навигации в Центре администрирования с выделенными элементами "Приложения Teams" > "Управление приложениями"](media/manage-approval-apps.png)

  4. <span data-ttu-id="11d24-143">Выберите "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="11d24-143">Select Approvals.</span></span>

  5. <span data-ttu-id="11d24-144">Выберите положение переключателя, соответствующее отключению приложения для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="11d24-144">Select the toggle to disable the app for your organization.</span></span>

![изображение сведений о приложении "Утверждения"](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="11d24-146">Политика хранения</span><span class="sxs-lookup"><span data-stu-id="11d24-146">Retention policy</span></span>

<span data-ttu-id="11d24-147">Утверждения, созданные в приложении "Утверждения", хранятся в заданной по умолчанию среде CDS, которая пока не поддерживает создание резервных копий.</span><span class="sxs-lookup"><span data-stu-id="11d24-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="11d24-148">Подробнее на тему [Создание резервных копий и восстановление среды — Power Platform \| Документация Майкрософт](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="11d24-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="11d24-149">Аудит</span><span class="sxs-lookup"><span data-stu-id="11d24-149">Auditing</span></span>

<span data-ttu-id="11d24-150">Приложение "Утверждения" ведет журнал событий аудита в Центре безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="11d24-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="11d24-151">Вы можете просмотреть этот журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="11d24-151">You can view the audit log.</span></span>

1. <span data-ttu-id="11d24-152">Перейдите в Центр соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="11d24-152">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="11d24-153">Зайдите в раздел **Аудит**.</span><span class="sxs-lookup"><span data-stu-id="11d24-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="11d24-154">Выполните поиск в секции **Действия в Microsoft Teams, связанные с утверждениями**.</span><span class="sxs-lookup"><span data-stu-id="11d24-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="11d24-155">Вы можете выполнять поиск по перечисленным ниже действиям.</span><span class="sxs-lookup"><span data-stu-id="11d24-155">You can search for the following activities:</span></span>

- <span data-ttu-id="11d24-156">Создание запроса на утверждение</span><span class="sxs-lookup"><span data-stu-id="11d24-156">Create new approval request</span></span>

- <span data-ttu-id="11d24-157">Просмотр сведений о запросе на утверждение</span><span class="sxs-lookup"><span data-stu-id="11d24-157">View approval request details</span></span>

- <span data-ttu-id="11d24-158">Утвержденный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="11d24-158">Approved approval request</span></span>

- <span data-ttu-id="11d24-159">Отклоненный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="11d24-159">Rejected approval request</span></span>

- <span data-ttu-id="11d24-160">Отмененный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="11d24-160">Canceled approval request</span></span>

- <span data-ttu-id="11d24-161">Общий запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="11d24-161">Shared approval request</span></span>

- <span data-ttu-id="11d24-162">Файл, вложенный в запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="11d24-162">File attached to approval request</span></span>

- <span data-ttu-id="11d24-163">Повторно назначенный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="11d24-163">Reassigned approval request</span></span>

- <span data-ttu-id="11d24-164">Добавленная цифровая подпись к запросу на утверждение</span><span class="sxs-lookup"><span data-stu-id="11d24-164">Added e-signature to approval request</span></span>

<span data-ttu-id="11d24-165">Для доступа к другим данным аудита утверждений в рамках Flow включите и настройте аудит в заданной по умолчанию среде для главных элементов, связанных с утверждениями: "утверждение", "запрос на утверждение" и "ответ на запрос на утверждение".</span><span class="sxs-lookup"><span data-stu-id="11d24-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="11d24-166">Операции создания, обновления и удаления являются подлежащими аудиту событиями в записях приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="11d24-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="11d24-167">Подробнее на тему [Аудит данных и действий пользователей для обеспечения безопасности и соответствия требованиям — Power Platform \| Документация Майкрософт](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="11d24-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="11d24-168">Можно выполнить дополнительную настройку аудита в [Центре безопасности и соответствия требованиям Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="11d24-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="11d24-169">Чтобы воспользоваться предварительно настроенными отчетами, войдите в Центр безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="11d24-169">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="11d24-170">Выберите **Поиск и исследование**.</span><span class="sxs-lookup"><span data-stu-id="11d24-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="11d24-171">Выполните поиск в журнале аудита и выберите вкладку **Действия в Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="11d24-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="11d24-172">Подробнее на тему [Microsoft Dataverse и ведение журнала действий в приложениях на основе моделей — Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="11d24-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="11d24-173">Безопасность</span><span class="sxs-lookup"><span data-stu-id="11d24-173">Security</span></span>

<span data-ttu-id="11d24-174">В приложении "Утверждения" Teams пользователи могут создавать утверждения, а также просматривать отправленные и полученные утверждения.</span><span class="sxs-lookup"><span data-stu-id="11d24-174">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="11d24-175">Пользователи не имеют доступа к утверждениям, созданным другими пользователями, если не указаны в качестве адресата или наблюдателя в соответствующем запросе.</span><span class="sxs-lookup"><span data-stu-id="11d24-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="11d24-176">Пользователю назначается роль наблюдателя запроса, если он является участником чата или канала, где было создано утверждение.</span><span class="sxs-lookup"><span data-stu-id="11d24-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="11d24-177">У него нет возможности совершать действия в отношении запроса, если при создании утверждения ему не была присвоена соответствующая роль.</span><span class="sxs-lookup"><span data-stu-id="11d24-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
