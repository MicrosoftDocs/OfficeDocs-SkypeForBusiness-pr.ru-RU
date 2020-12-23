---
title: Доступность приложения утверждения в Teams
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
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675197"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="5739f-103">Доступность приложения "Утверждения Teams"</span><span class="sxs-lookup"><span data-stu-id="5739f-103">Teams Approvals app availability</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="5739f-104">Приложение "Утверждения" доступно как личное приложение для всех пользователей Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5739f-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="5739f-105">Приложение "Утверждения" представляет собой простой способ обеспечить аудит, соответствие требованиям, ответственность и рабочий процесс для структурированных и неструктурированных утверждений в Teams.</span><span class="sxs-lookup"><span data-stu-id="5739f-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![приложение "Утверждения"](media/approvals-selection.png)

<span data-ttu-id="5739f-107">Пользователи могут закрепить приложение "Утверждения", чтобы сохранить его в меню.</span><span class="sxs-lookup"><span data-stu-id="5739f-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![приложение "Утверждения" с параметром закрепления](media/approvalApp-pin.png)

<span data-ttu-id="5739f-109">Первое утверждение, созданное с помощью приложения "Утверждения", активирует его подготовка в среде cdS по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5739f-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="5739f-110">Утверждения, созданные с помощью приложения "Утверждения", будут храниться в среде CDS по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5739f-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="5739f-111">В этой статье описаны требования и роли приложений "Утверждение".</span><span class="sxs-lookup"><span data-stu-id="5739f-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="5739f-112">Необходимые разрешения и лицензии</span><span class="sxs-lookup"><span data-stu-id="5739f-112">Required permissions and licenses</span></span>

<span data-ttu-id="5739f-113">Для использования приложения "Утверждения" необходимо разрешение на следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="5739f-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="5739f-114">Разрешения на создание базы данных CDS (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="5739f-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="5739f-115">Учетная запись на [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="5739f-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="5739f-116">Роль администратора в целевой среде.</span><span class="sxs-lookup"><span data-stu-id="5739f-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="5739f-117">Лицензия на [Power Automate,](https://docs.microsoft.com/power-automate/get-started-approvals)Office 365 или Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="5739f-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="5739f-118">Хранилище с компакт-дисками</span><span class="sxs-lookup"><span data-stu-id="5739f-118">Storage with CDS</span></span>

<span data-ttu-id="5739f-119">Общая модель данных (CDM) — это язык общих данных, используемый в бизнес-приложениях и аналитических приложениях на cdS.</span><span class="sxs-lookup"><span data-stu-id="5739f-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="5739f-120">Он содержит набор стандартизированных, extensible data schemas, опубликованных корпорацией Майкрософт и нашими партнерами, которые обеспечивают согласованность данных и их значение в приложениях и бизнес-процессах.</span><span class="sxs-lookup"><span data-stu-id="5739f-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="5739f-121">Узнайте больше об общей [модели данных microsoft Power Platform.](https://docs.microsoft.com/power-automate/get-started-approvals)</span><span class="sxs-lookup"><span data-stu-id="5739f-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="5739f-122">Подробнее о рабочий [процессе "Утверждение".](https://docs.microsoft.com/power-automate/modern-approvals)</span><span class="sxs-lookup"><span data-stu-id="5739f-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="5739f-123">Разрешения приложений Teams утверждения</span><span class="sxs-lookup"><span data-stu-id="5739f-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="5739f-124">Приложение Approvals Teams позволяет получить доступ к следующим возможностям:</span><span class="sxs-lookup"><span data-stu-id="5739f-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="5739f-125">Получение сообщений и данных, которые вы предоставляете ему.</span><span class="sxs-lookup"><span data-stu-id="5739f-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="5739f-126">Отправка вам сообщений и уведомлений.</span><span class="sxs-lookup"><span data-stu-id="5739f-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="5739f-127">Отрисуйте личные приложения и диалоговое окно без заглавной области, предоставленной Teams.</span><span class="sxs-lookup"><span data-stu-id="5739f-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="5739f-128">Доступ к данным профиля, таким как ваше имя, адрес электронной почты, название компании и предпочтительный язык.</span><span class="sxs-lookup"><span data-stu-id="5739f-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="5739f-129">Получение сообщений и данных, которые участники группы предоставляют в канале.</span><span class="sxs-lookup"><span data-stu-id="5739f-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="5739f-130">Отправка сообщений и уведомлений в канале.</span><span class="sxs-lookup"><span data-stu-id="5739f-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="5739f-131">Доступ к сведениям о группе:</span><span class="sxs-lookup"><span data-stu-id="5739f-131">Access your team's information:</span></span>
  - <span data-ttu-id="5739f-132">название команды</span><span class="sxs-lookup"><span data-stu-id="5739f-132">team name</span></span>
  - <span data-ttu-id="5739f-133">список каналов</span><span class="sxs-lookup"><span data-stu-id="5739f-133">channel list</span></span>
  - <span data-ttu-id="5739f-134">список членов группы (имена и адреса электронной почты участника группы).</span><span class="sxs-lookup"><span data-stu-id="5739f-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="5739f-135">Используйте сведения группы, чтобы связаться с ним.</span><span class="sxs-lookup"><span data-stu-id="5739f-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="5739f-136">Отключение приложения "Утверждения"</span><span class="sxs-lookup"><span data-stu-id="5739f-136">Disable the Approvals app</span></span>

<span data-ttu-id="5739f-137">Приложение "Утверждения" доступно по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5739f-137">The Approvals app is available by default.</span></span> <span data-ttu-id="5739f-138">Вы можете отключить приложение в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="5739f-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="5739f-139">Во sign in to the Teams admin center.</span><span class="sxs-lookup"><span data-stu-id="5739f-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="5739f-140">Раз развернуть **приложения Teams** и выбрать **"Управление приложениями".**</span><span class="sxs-lookup"><span data-stu-id="5739f-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="5739f-141">Найди приложение "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="5739f-141">Search for the Approvals app.</span></span>

![Навигация в Центре администрирования с выделенной командой > "Управление приложениями"](media/manage-approval-apps.png)

  4. <span data-ttu-id="5739f-143">Выберите "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="5739f-143">Select Approvals.</span></span>

  5. <span data-ttu-id="5739f-144">Чтобы отключить приложение для организации, выберите его.</span><span class="sxs-lookup"><span data-stu-id="5739f-144">Select the toggle to disable the app for your organization.</span></span>

![подробные сведения о приложении "Утверждения"](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="5739f-146">Политика хранения</span><span class="sxs-lookup"><span data-stu-id="5739f-146">Retention policy</span></span>

<span data-ttu-id="5739f-147">Утверждения, созданные с помощью приложения "Утверждения", хранятся в среде CDS по умолчанию, которая в настоящее время не поддерживает резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="5739f-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="5739f-148">Узнайте больше о том, как восстанавливать и восстанавливать [среды — Microsoft \| Docs для Power Platform.](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)</span><span class="sxs-lookup"><span data-stu-id="5739f-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="5739f-149">Аудит</span><span class="sxs-lookup"><span data-stu-id="5739f-149">Auditing</span></span>

<span data-ttu-id="5739f-150">Приложение Approvals регистрет события аудита в Центре безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5739f-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="5739f-151">Вы можете просмотреть журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="5739f-151">You can view the audit log.</span></span>

1. <span data-ttu-id="5739f-152">Перейдите на сайт соответствия требованиям M365.</span><span class="sxs-lookup"><span data-stu-id="5739f-152">Go to the M365 Compliance Site.</span></span>

2. <span data-ttu-id="5739f-153">Выберите раздел **"Аудит".**</span><span class="sxs-lookup"><span data-stu-id="5739f-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="5739f-154">Поиск действий в **рамках действий утверждения в Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="5739f-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="5739f-155">Вы можете найти следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5739f-155">You can search for the following activities:</span></span>

- <span data-ttu-id="5739f-156">Создание нового запроса на утверждение</span><span class="sxs-lookup"><span data-stu-id="5739f-156">Create new approval request</span></span>

- <span data-ttu-id="5739f-157">Просмотр сведений о запросе утверждения</span><span class="sxs-lookup"><span data-stu-id="5739f-157">View approval request details</span></span>

- <span data-ttu-id="5739f-158">Утвержденный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="5739f-158">Approved approval request</span></span>

- <span data-ttu-id="5739f-159">Отклоненный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="5739f-159">Rejected approval request</span></span>

- <span data-ttu-id="5739f-160">Отменен запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="5739f-160">Canceled approval request</span></span>

- <span data-ttu-id="5739f-161">Общий запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="5739f-161">Shared approval request</span></span>

- <span data-ttu-id="5739f-162">Файл, вложенный в запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="5739f-162">File attached to approval request</span></span>

- <span data-ttu-id="5739f-163">Повторно назначен запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="5739f-163">Reassigned approval request</span></span>

- <span data-ttu-id="5739f-164">В запрос на утверждение добавлена электронная подпись</span><span class="sxs-lookup"><span data-stu-id="5739f-164">Added e-signature to approval request</span></span>

<span data-ttu-id="5739f-165">Чтобы получить доступ к дополнительным утверждениям аудита в потоке, встроите и настройте аудит в среде по умолчанию для основных запросов утверждения, запросов на утверждение и ответов на утверждение.</span><span class="sxs-lookup"><span data-stu-id="5739f-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="5739f-166">Операции создания, обновления и удаления являются событиями аудита для записей утверждения.</span><span class="sxs-lookup"><span data-stu-id="5739f-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="5739f-167">Дополнительные сведения о данных аудита и действиях пользователей для обеспечения безопасности и соответствия требованиям [— Microsoft \| Docs power Platform.](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)</span><span class="sxs-lookup"><span data-stu-id="5739f-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="5739f-168">Аудит можно дополнительно настроить в Центре безопасности и соответствия требованиям [Microsoft 365.](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)</span><span class="sxs-lookup"><span data-stu-id="5739f-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="5739f-169">Чтобы использовать предварительно заранее задав их, вопишите в службу безопасности и соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="5739f-169">To use the preconfigured reports, sign in to Office 365 Security and Compliance.</span></span>

2. <span data-ttu-id="5739f-170">Выберите **"Поиск & исследования".**</span><span class="sxs-lookup"><span data-stu-id="5739f-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="5739f-171">В журнале аудита выберите вкладку **действий Dynamics 365.**</span><span class="sxs-lookup"><span data-stu-id="5739f-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="5739f-172">Дополнительные сведения о регистрации действий в приложениях на основе модели и microsoft Dataverse — [Power Platform.](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)</span><span class="sxs-lookup"><span data-stu-id="5739f-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="5739f-173">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5739f-173">Security</span></span>

<span data-ttu-id="5739f-174">В приложении "Утверждение Teams" пользователи могут создавать новые утверждения и просматривать отправленные и полученные утверждения.</span><span class="sxs-lookup"><span data-stu-id="5739f-174">From the Teams Approval App, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="5739f-175">Пользователи не смогут получить доступ к утверждениям, созданным другими пользователями, если они не являются либо ответив, либо просматривают запрос.</span><span class="sxs-lookup"><span data-stu-id="5739f-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="5739f-176">Пользователю будет предоставлена роль просмотра запроса, если он является частью чата или канала, где было создано утверждение.</span><span class="sxs-lookup"><span data-stu-id="5739f-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="5739f-177">Они не могут выполнять действия с запросом, если им не была предоставлена эта роль при утверждении.</span><span class="sxs-lookup"><span data-stu-id="5739f-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
