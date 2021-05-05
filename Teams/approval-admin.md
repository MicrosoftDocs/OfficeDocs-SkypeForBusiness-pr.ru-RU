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
ms.openlocfilehash: 127fc2831e58e7ddea152c7754015a9126390ecc
ms.sourcegitcommit: 5a738cbb96f09edd8c3779f9385bc9ed126e3001
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2021
ms.locfileid: "52212172"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="5da9d-103">Доступность приложения "Утверждения" Teams</span><span class="sxs-lookup"><span data-stu-id="5da9d-103">Teams Approvals app availability</span></span>

<span data-ttu-id="5da9d-104">Приложение "Утверждения" доступно в качестве персонального приложения для всех пользователей Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5da9d-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="5da9d-105">Приложение "Утверждения" обеспечивает простой способ обеспечения аудита, соответствия требованиям, подотчетности и рабочих процессов как для структурированных, так и для неструктурированных утверждений в Teams.</span><span class="sxs-lookup"><span data-stu-id="5da9d-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![изображение приложения "Утверждения"](media/approvals-selection.png)

<span data-ttu-id="5da9d-107">Пользователи могут закрепить приложение "Утверждения" в строке меню</span><span class="sxs-lookup"><span data-stu-id="5da9d-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![изображение приложения "Утверждения" с функцией закрепления](media/approvalApp-pin.png)

<span data-ttu-id="5da9d-109">Первое утверждение, созданное в приложении "Утверждения", станет сигналом к подготовке решения для утверждений в заданной по умолчанию среде Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="5da9d-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="5da9d-110">Утверждения, созданные в приложении "Утверждения", хранятся в заданной по умолчанию среде CDS.</span><span class="sxs-lookup"><span data-stu-id="5da9d-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="5da9d-111">В этой статье содержится информация о требованиях и ролях приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="5da9d-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="5da9d-112">Эта функция еще не выпущена для пользователей облако сообщества для государственных организаций (GCC), облако сообщества для государственных организаций high (GCCH) и Department of Defense (DOD).</span><span class="sxs-lookup"><span data-stu-id="5da9d-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="5da9d-113">Необходимые разрешения и лицензии</span><span class="sxs-lookup"><span data-stu-id="5da9d-113">Required permissions and licenses</span></span>

<span data-ttu-id="5da9d-114">Для использования приложения "Утверждения" вам необходимы перечисленные ниже разрешения.</span><span class="sxs-lookup"><span data-stu-id="5da9d-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="5da9d-115">Разрешения на создание базы данных Microsoft CDS.</span><span class="sxs-lookup"><span data-stu-id="5da9d-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="5da9d-116">Учетная запись [flow.microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="5da9d-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="5da9d-117">Роль администратора в целевой среде</span><span class="sxs-lookup"><span data-stu-id="5da9d-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="5da9d-118">Лицензия на [Power Automate](/power-automate/get-started-approvals), Office 365 или Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="5da9d-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

- <span data-ttu-id="5da9d-119">Для того чтобы пользователи настроили новые шаблоны утверждения, необходима лицензия на Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="5da9d-119">License for Microsoft Forms is required for users to set up new approval templates.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="5da9d-120">Хранилище CDS</span><span class="sxs-lookup"><span data-stu-id="5da9d-120">Storage with CDS</span></span>

<span data-ttu-id="5da9d-121">Common Data Model (CDM) — это язык общих данных, используемый в приложениях для бизнеса и аналитики в CDS.</span><span class="sxs-lookup"><span data-stu-id="5da9d-121">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="5da9d-122">Он состоит из набора стандартизованных расширяемых схем данных, публикуемых корпорацией Майкрософт и ее партнерами, и позволяет поддерживать согласованность данных и их значение во всех приложениях и бизнес-процессах.</span><span class="sxs-lookup"><span data-stu-id="5da9d-122">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="5da9d-123">Подробнее о [языке Common Data Model Microsoft Power Platform](/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="5da9d-123">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="5da9d-124">Подробнее о рабочем процессе [утверждений](/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="5da9d-124">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

<span data-ttu-id="5da9d-125">Утверждения, созданные на 2016 г., по-прежнему хранят данные в CDS, такие как название, сведения, ИД шаблона и другие.</span><span class="sxs-lookup"><span data-stu-id="5da9d-125">Approvals that are created from a template still store data in CDS, such as their title, details, template ID, and more.</span></span> <span data-ttu-id="5da9d-126">Ответы, отправленные по запросу на утверждение, хранятся в Forms.</span><span class="sxs-lookup"><span data-stu-id="5da9d-126">Responses that are submitted on the approval request are stored in Forms.</span></span> <span data-ttu-id="5da9d-127">Дополнительные сведения о  [хранении данных в Microsoft Forms.](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)</span><span class="sxs-lookup"><span data-stu-id="5da9d-127">Learn more about  [Data storage for Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).</span></span>

>[!Note]
><span data-ttu-id="5da9d-128">Если вы удалите шаблон формы на сайте Microsoft Forms, шаблон утверждения будет разорвано, и пользователи не смогут запустить запрос.</span><span class="sxs-lookup"><span data-stu-id="5da9d-128">If you delete the Form template on the Microsoft Forms site, it will break your Approval template and users will not be able to start the request.</span></span> <span data-ttu-id="5da9d-129">При попытке открыть шаблон утверждения, удаленный в Microsoft Forms, пользователи получают сообщение об ошибке "CDB TableNotFound".</span><span class="sxs-lookup"><span data-stu-id="5da9d-129">Users will get an error "CDB TableNotFound" when trying to open an Approval template that has been deleted on Microsoft Forms.</span></span>

<span data-ttu-id="5da9d-130">Шаблоны утверждения хранятся в SDS служба хранилища, которая соответствует требованиям для хранения данных внутри корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5da9d-130">The approval templates are stored in Substrate Data Storage (SDS), which is a compliant storage platform used internally only inside Microsoft.</span></span> <span data-ttu-id="5da9d-131">Шаблоны на масштабе организации хранятся в SDS-клиенте, а шаблоны для группы — в SDS.</span><span class="sxs-lookup"><span data-stu-id="5da9d-131">The organization-scoped templates are stored in “tenant shard” of SDS, and team-scoped templates are stored in “group shards” of SDS.</span></span> <span data-ttu-id="5da9d-132">Это означает, что шаблоны на уровне организации имеют одно и то же время существования шаблонов на уровне клиента и группы.</span><span class="sxs-lookup"><span data-stu-id="5da9d-132">This means that the org-scoped templates share the same lifetime of the tenant and team-scoped templates share the same lifetime of the team.</span></span> <span data-ttu-id="5da9d-133">Таким образом, при окончательном удалении группы связанные шаблоны удаляются.</span><span class="sxs-lookup"><span data-stu-id="5da9d-133">So, permanently deleting the team deletes the related templates.</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="5da9d-134">Разрешения приложения "Утверждения" Teams</span><span class="sxs-lookup"><span data-stu-id="5da9d-134">Approvals Teams app permissions</span></span>

<span data-ttu-id="5da9d-135">Приложение "Утверждения" Teams позволяет получать доступ к перечисленным ниже возможностям.</span><span class="sxs-lookup"><span data-stu-id="5da9d-135">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="5da9d-136">Получение сообщений и данных, которые вы ему предоставляете.</span><span class="sxs-lookup"><span data-stu-id="5da9d-136">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="5da9d-137">Отправка вам сообщений и уведомлений.</span><span class="sxs-lookup"><span data-stu-id="5da9d-137">Send you messages and notifications.</span></span>

- <span data-ttu-id="5da9d-138">Отрисовка персональных приложений и диалогов без колонтитула Teams.</span><span class="sxs-lookup"><span data-stu-id="5da9d-138">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="5da9d-139">Получение доступа к информации вашего профиля, такой как ваше имя, адрес электронной почты, название компании и предпочтительный язык.</span><span class="sxs-lookup"><span data-stu-id="5da9d-139">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="5da9d-140">Получение сообщений и данных, которые участники команды предоставляют ему в канале.</span><span class="sxs-lookup"><span data-stu-id="5da9d-140">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="5da9d-141">Отправка сообщений и уведомлений в канале.</span><span class="sxs-lookup"><span data-stu-id="5da9d-141">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="5da9d-142">Получение доступа к следующей информации о вашей команде:</span><span class="sxs-lookup"><span data-stu-id="5da9d-142">Access your team's information:</span></span>
  - <span data-ttu-id="5da9d-143">название команды</span><span class="sxs-lookup"><span data-stu-id="5da9d-143">team name</span></span>
  - <span data-ttu-id="5da9d-144">список каналов</span><span class="sxs-lookup"><span data-stu-id="5da9d-144">channel list</span></span>
  - <span data-ttu-id="5da9d-145">состав (имена и адреса электронной почты участников команды).</span><span class="sxs-lookup"><span data-stu-id="5da9d-145">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="5da9d-146">Использование информации о команде для контакта с ней.</span><span class="sxs-lookup"><span data-stu-id="5da9d-146">Use the team's information to contact them.</span></span>

<span data-ttu-id="5da9d-147">Разрешения шаблона утверждения</span><span class="sxs-lookup"><span data-stu-id="5da9d-147">Approval Template Permissions</span></span>

- <span data-ttu-id="5da9d-148">Все владельцы команд могут создать шаблон утверждения для своих команд.</span><span class="sxs-lookup"><span data-stu-id="5da9d-148">All team owners can create an approval template for teams that they own.</span></span>

- <span data-ttu-id="5da9d-149">Когда администратор впервые создает шаблон для всей организации, он автоматически создает группу Teams для всех администраторов клиента, включая глобальных администраторов и администраторов служб группы.</span><span class="sxs-lookup"><span data-stu-id="5da9d-149">When an Admin creates a template for their entire organization for the first time, it will automatically create a new Teams team for all admins of the tenant, including the global and Team’s service admins.</span></span> <span data-ttu-id="5da9d-150">Эти администраторы будут добавлены в качестве владельцев команды, чтобы они могли совместно управлять шаблонами организации.</span><span class="sxs-lookup"><span data-stu-id="5da9d-150">These admins will be added as owners of the team, so they can co-manage organizational templates.</span></span> <span data-ttu-id="5da9d-151">Администраторов, которые еще не были добавлены в организацию после создания команды, необходимо вручную добавить в качестве владельцев команд, чтобы они могли управлять шаблонами для всей организации.</span><span class="sxs-lookup"><span data-stu-id="5da9d-151">Admins that are new to the organization after the team has been created need to be manually added as team owners so they have the same permissions to manage organization-wide templates.</span></span>

> [!Note]
> <span data-ttu-id="5da9d-152">Если администратор удаляет группу, у вас есть месяц на ее восстановление на портале Azure Active Directory AAD, чтобы восстановить все связанные данные.</span><span class="sxs-lookup"><span data-stu-id="5da9d-152">If an admin deletes the team, you have one month to restore it within the Azure Active Directory (AAD) portal to restore all related data.</span></span> <span data-ttu-id="5da9d-153">Если администратор удалит эту группу из корзины через один месяц, вы потеряете все связанные данные.</span><span class="sxs-lookup"><span data-stu-id="5da9d-153">After one month, or if the admin deletes this team within the recycle bin, you will lose all the related data.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="5da9d-154">Отключение приложения "Утверждения" в Teams</span><span class="sxs-lookup"><span data-stu-id="5da9d-154">Disable the Approvals app</span></span>

<span data-ttu-id="5da9d-155">Приложение "Утверждения" доступно по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5da9d-155">The Approvals app is available by default.</span></span> <span data-ttu-id="5da9d-156">Вы можете отключить его в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="5da9d-156">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="5da9d-157">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="5da9d-157">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="5da9d-158">Разверните раздел **Приложения Teams** и выберите **Управление приложениями**.</span><span class="sxs-lookup"><span data-stu-id="5da9d-158">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="5da9d-159">Выполните поиск приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="5da9d-159">Search for the Approvals app.</span></span>

     ![изображение навигации в Центре администрирования с выделенными элементами "Приложения Teams" > "Управление приложениями"](media/manage-approval-apps.png)

  4. <span data-ttu-id="5da9d-161">Выберите "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="5da9d-161">Select Approvals.</span></span>

  5. <span data-ttu-id="5da9d-162">Выберите положение переключателя, соответствующее отключению приложения для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5da9d-162">Select the toggle to disable the app for your organization.</span></span>

     ![изображение сведений о приложении "Утверждения"](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="5da9d-164">Политика хранения</span><span class="sxs-lookup"><span data-stu-id="5da9d-164">Retention policy</span></span>

<span data-ttu-id="5da9d-165">Утверждения, созданные в приложении "Утверждения", хранятся в заданной по умолчанию среде CDS, которая пока не поддерживает создание резервных копий.</span><span class="sxs-lookup"><span data-stu-id="5da9d-165">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="5da9d-166">Подробнее на тему [Создание резервных копий и восстановление среды — Power Platform \| Документация Майкрософт](/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="5da9d-166">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

<span data-ttu-id="5da9d-167">Данные, хранимые в Forms, не будут удалены, пока владельцы команды не очистят их с вкладки "Удаленные формы" в веб-приложении Microsoft Forms. </span><span class="sxs-lookup"><span data-stu-id="5da9d-167">Data stored in Forms will not be deleted until the team owners clean it up from the **deleted forms** tab in the Microsoft Forms web app.</span></span>

## <a name="data-limitations"></a><span data-ttu-id="5da9d-168">Ограничения данных</span><span class="sxs-lookup"><span data-stu-id="5da9d-168">Data limitations</span></span>

<span data-ttu-id="5da9d-169">Каждая команда может содержать не более 400 шаблонов утверждения, а каждый шаблон может собрать не более 50 000 запросов с учетом текущих возможностей Microsoft Forms.</span><span class="sxs-lookup"><span data-stu-id="5da9d-169">Each team can contain at most 400 approvals templates, and each template can collect a maximum of 50,000 requests based on the current capability in Microsoft Forms.</span></span>

## <a name="auditing"></a><span data-ttu-id="5da9d-170">Аудит</span><span class="sxs-lookup"><span data-stu-id="5da9d-170">Auditing</span></span>

<span data-ttu-id="5da9d-171">Приложение "Утверждения" ведет журнал событий аудита в Центре безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5da9d-171">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="5da9d-172">Вы можете просмотреть этот журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="5da9d-172">You can view the audit log.</span></span>

1. <span data-ttu-id="5da9d-173">Перейдите в Центр соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5da9d-173">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="5da9d-174">Зайдите в раздел **Аудит**.</span><span class="sxs-lookup"><span data-stu-id="5da9d-174">Select the **Audit** section.</span></span>

3. <span data-ttu-id="5da9d-175">Выполните поиск в секции **Действия в Microsoft Teams, связанные с утверждениями**.</span><span class="sxs-lookup"><span data-stu-id="5da9d-175">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="5da9d-176">Вы можете выполнять поиск по перечисленным ниже действиям.</span><span class="sxs-lookup"><span data-stu-id="5da9d-176">You can search for the following activities:</span></span>

- <span data-ttu-id="5da9d-177">Создание запроса на утверждение</span><span class="sxs-lookup"><span data-stu-id="5da9d-177">Create new approval request</span></span>

- <span data-ttu-id="5da9d-178">Просмотр сведений о запросе на утверждение</span><span class="sxs-lookup"><span data-stu-id="5da9d-178">View approval request details</span></span>

- <span data-ttu-id="5da9d-179">Утвержденный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="5da9d-179">Approved approval request</span></span>

- <span data-ttu-id="5da9d-180">Отклоненный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="5da9d-180">Rejected approval request</span></span>

- <span data-ttu-id="5da9d-181">Отмененный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="5da9d-181">Canceled approval request</span></span>

- <span data-ttu-id="5da9d-182">Общий запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="5da9d-182">Shared approval request</span></span>

- <span data-ttu-id="5da9d-183">Файл, вложенный в запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="5da9d-183">File attached to approval request</span></span>

- <span data-ttu-id="5da9d-184">Повторно назначенный запрос на утверждение</span><span class="sxs-lookup"><span data-stu-id="5da9d-184">Reassigned approval request</span></span>

- <span data-ttu-id="5da9d-185">Добавленная цифровая подпись к запросу на утверждение</span><span class="sxs-lookup"><span data-stu-id="5da9d-185">Added e-signature to approval request</span></span>

- <span data-ttu-id="5da9d-186">Просмотр сведений о запросе электронной подписи</span><span class="sxs-lookup"><span data-stu-id="5da9d-186">Viewed e-signature request details</span></span>

- <span data-ttu-id="5da9d-187">Просмотренное запрос на электронную подпись</span><span class="sxs-lookup"><span data-stu-id="5da9d-187">Reviewed e-signature request</span></span>

- <span data-ttu-id="5da9d-188">Отменен запрос на электронную подпись</span><span class="sxs-lookup"><span data-stu-id="5da9d-188">Canceled e-signature request</span></span>

- <span data-ttu-id="5da9d-189">Создание шаблона</span><span class="sxs-lookup"><span data-stu-id="5da9d-189">Create a new template</span></span>

- <span data-ttu-id="5da9d-190">Изменение существующего шаблона</span><span class="sxs-lookup"><span data-stu-id="5da9d-190">Edit an existing template</span></span>

- <span data-ttu-id="5da9d-191">Включить и отключить шаблон</span><span class="sxs-lookup"><span data-stu-id="5da9d-191">Enable/disable a template</span></span>

- <span data-ttu-id="5da9d-192">Просмотримый шаблон</span><span class="sxs-lookup"><span data-stu-id="5da9d-192">Viewed template</span></span>

<span data-ttu-id="5da9d-193">Для доступа к другим данным аудита утверждений в рамках Flow включите и настройте аудит в заданной по умолчанию среде для главных элементов, связанных с утверждениями: "утверждение", "запрос на утверждение" и "ответ на запрос на утверждение".</span><span class="sxs-lookup"><span data-stu-id="5da9d-193">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="5da9d-194">Операции создания, обновления и удаления являются подлежащими аудиту событиями в записях приложения "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="5da9d-194">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="5da9d-195">Подробнее на тему [Аудит данных и действий пользователей для обеспечения безопасности и соответствия требованиям — Power Platform \| Документация Майкрософт](/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="5da9d-195">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="5da9d-196">Можно выполнить дополнительную настройку аудита в [Центре безопасности и соответствия требованиям Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="5da9d-196">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="5da9d-197">Чтобы воспользоваться предварительно настроенными отчетами, войдите в Центр безопасности и соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5da9d-197">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="5da9d-198">Выберите **Поиск и исследование**.</span><span class="sxs-lookup"><span data-stu-id="5da9d-198">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="5da9d-199">Выполните поиск в журнале аудита и выберите вкладку **Действия в Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="5da9d-199">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="5da9d-200">Подробнее на тему [Microsoft Dataverse и ведение журнала действий в приложениях на основе моделей — Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="5da9d-200">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="5da9d-201">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5da9d-201">Security</span></span>

<span data-ttu-id="5da9d-202">В приложении "Утверждения" Teams пользователи могут создавать утверждения, а также просматривать отправленные и полученные утверждения.</span><span class="sxs-lookup"><span data-stu-id="5da9d-202">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="5da9d-203">Пользователи не имеют доступа к утверждениям, созданным другими пользователями, если не указаны в качестве адресата или наблюдателя в соответствующем запросе.</span><span class="sxs-lookup"><span data-stu-id="5da9d-203">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="5da9d-204">Пользователю назначается роль наблюдателя запроса, если он является участником чата или канала, где было создано утверждение.</span><span class="sxs-lookup"><span data-stu-id="5da9d-204">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="5da9d-205">У него нет возможности совершать действия в отношении запроса, если при создании утверждения ему не была присвоена соответствующая роль.</span><span class="sxs-lookup"><span data-stu-id="5da9d-205">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="5da9d-206">Интеграция с электронной подписью "Утверждения"</span><span class="sxs-lookup"><span data-stu-id="5da9d-206">Approvals e-signature integration</span></span>

<span data-ttu-id="5da9d-207">Утверждения электронной подписи, созданные в приложении "Утверждения", хранятся в облачной среде выбранного поставщика.</span><span class="sxs-lookup"><span data-stu-id="5da9d-207">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="5da9d-208">Дополнительные сведения о хранилище в рамках соглашения с электронной подписью можно получить в документации выбранного поставщика.</span><span class="sxs-lookup"><span data-stu-id="5da9d-208">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="5da9d-209">Чтобы использовать функцию электронной подписи в приложении "Утверждения", вам нужны следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="5da9d-209">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="5da9d-210">Лицензия для конкретного поставщика электронной подписи, который вы выбираете.</span><span class="sxs-lookup"><span data-stu-id="5da9d-210">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="5da9d-211">Чтобы получить лицензию для своей организации, необходимо перейти на сайт поставщика.</span><span class="sxs-lookup"><span data-stu-id="5da9d-211">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="5da9d-212">Для функций работы с электронной подписью "Утверждения" партнеры по подписи сторонних разработчиков по умолчанию отображаются в Teams "Утверждения".</span><span class="sxs-lookup"><span data-stu-id="5da9d-212">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="5da9d-213">Вы можете отключить определенные поставщики электронной подписи, задав параметры приложения в Teams центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="5da9d-213">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="5da9d-214">В центре Teams администрирования в **области** Управление приложениями выберите приложение **"Утверждения"** и Параметры . </span><span class="sxs-lookup"><span data-stu-id="5da9d-214">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="5da9d-215">Каждый поставщик электронной подписи по умолчанию имеет для него значение в положении "вкл." (справа).</span><span class="sxs-lookup"><span data-stu-id="5da9d-215">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="5da9d-216">Чтобы отключить определенного поставщика электронной подписи, перевиньте его влево.</span><span class="sxs-lookup"><span data-stu-id="5da9d-216">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="5da9d-217">Если администратор Teams отключает поставщика, конечные пользователи не будут видеть его при создании утверждения.</span><span class="sxs-lookup"><span data-stu-id="5da9d-217">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="5da9d-218">Кроме того, конечные пользователи не смогут просматривать запросы на электронную подпись, сделанные с этим поставщиком.</span><span class="sxs-lookup"><span data-stu-id="5da9d-218">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="5da9d-219">Утверждения электронной подписи, созданные в приложении "Утверждения", хранятся в облаке выбранного поставщика.</span><span class="sxs-lookup"><span data-stu-id="5da9d-219">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="5da9d-220">Поэтому для экспорта данных об электронных подписях необходимо перейти на сайт поставщика.</span><span class="sxs-lookup"><span data-stu-id="5da9d-220">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="5da9d-221">Обратитесь к документации поставщика об экспорте и хранении этих соглашений.</span><span class="sxs-lookup"><span data-stu-id="5da9d-221">Refer to the provider's documentation about export and retention of these agreements.</span></span>
