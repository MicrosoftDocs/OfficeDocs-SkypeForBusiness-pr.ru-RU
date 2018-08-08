---
title: Обзор Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Сведения о продукте Microsoft Teams, его инфраструктуре и использовании вместе с Office 365.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86698a3bb7535a20b7fb1b6833062d118f2f9eae
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967131"
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="dfa15-103">Обзор Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dfa15-103">Overview of Microsoft Teams</span></span>
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


<span data-ttu-id="dfa15-104">Microsoft Teams наследует масштабность и охват Office 365, предоставляя основанный на чате центр для командной работы и позволяя клиентам сформировать более открытую, гибкую и цифровую среду.</span><span class="sxs-lookup"><span data-stu-id="dfa15-104">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment.</span></span> <span data-ttu-id="dfa15-105">Microsoft Teams реализован на базе существующих технологий, объединяемых Группами Office 365.</span><span class="sxs-lookup"><span data-stu-id="dfa15-105">Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="dfa15-106">Teams сразу же использует удостоверения, хранящиеся в Azure Active Directory (Azure AD), и интегрируется с другими службами в Office 365, чтобы предоставить сайт SharePoint Online и почтовый ящик группы Exchange Online для каждой создаваемой команды.</span><span class="sxs-lookup"><span data-stu-id="dfa15-106">Out of the box, Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="dfa15-107">Лица, имеющие business потребитель электронной почты учетной записи или, например, Outlook, Gmail или другим пользователям, могут участвовать в качестве гостя в группах.</span><span class="sxs-lookup"><span data-stu-id="dfa15-107">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span> <span data-ttu-id="dfa15-108">Все гости в группах охвачено же соответствие требованиям и аудита защиты, что остальную часть Office 365 и гости могут безопасное управление в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dfa15-108">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span> <span data-ttu-id="dfa15-109">«Администраторы» можно централизованно управлять как гости принимать участие в их среде Office 365 и легко просматривать, добавить или отменить гостевой доступ к клиенту узла.</span><span class="sxs-lookup"><span data-stu-id="dfa15-109">Admins can centrally manage how guests participate within their Office 365 environment and easily view, add, or revoke a guest’s access to the host tenant.</span></span>

<span data-ttu-id="dfa15-110">Teams предлагает возможности сохраняемого чата, звонков и собраний, простого доступа к другим компонентам Office 365, а также мощные возможности расширения.</span><span class="sxs-lookup"><span data-stu-id="dfa15-110">Teams provides a persistent chat capability, calling and meetings, easy access to other components of Office 365 as well as a robust extensibility story.</span></span>  <span data-ttu-id="dfa15-111">Все это позволяет создать комплексный центр для совместной работы в больших корпорациях, небольших компаниях и любых других организациях.</span><span class="sxs-lookup"><span data-stu-id="dfa15-111">This provides a hub for teamwork that is appropriate for enterprise companies, small organizations and everyone in between.</span></span>  

<span data-ttu-id="dfa15-112">Для расширения возможностей Teams используйте соединители, вкладки и боты, доступные как [Приложения](https://go.microsoft.com/fwlink/?linkid=854629) и позволяющие взаимодействовать с внешней информацией, контентом и интеллектуальными ботами.</span><span class="sxs-lookup"><span data-stu-id="dfa15-112">To extend Teams capabilities, use Connectors, Tabs, and Bots - available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629), to bring external information, content, and intelligent bot interactions to Teams.</span></span>  

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="dfa15-113">Инфраструктура Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dfa15-113">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="dfa15-114">Teams реализован на базе существующих технологий, объединяемых Группами Office 365.</span><span class="sxs-lookup"><span data-stu-id="dfa15-114">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="dfa15-115">Благодаря возможностям Microsoft Cloud организации могут обеспечить превосходную производительность и надежность при использовании Teams для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="dfa15-115">Powered by the Microsoft cloud, organizations can expect excellent performance and reliability when leveraging Teams as part of their collaboration story.</span></span>

<span data-ttu-id="dfa15-116">Для созданной в Teams команды сразу же создается группа Office 365, сайт SharePoint Online (дополненный библиотекой документов) и почтовый ящик группы Exchange Online, который будет использоваться Teams для хранения такой информации, как приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="dfa15-116">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="dfa15-117">Команду можно создать с использованием существующих Групп Office 365, разрешив существующие членства в группах и перенеся контент из SharePoint Online и Exchange Online в Teams.</span><span class="sxs-lookup"><span data-stu-id="dfa15-117">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="dfa15-118">В дополнение возможность группам как плата persistent chat, где неофициальные, в режиме реального времени бесед происходят, групп также предоставляет звонков и возможности, созданные на основе инфраструктуры следующего поколения на основе облака, используемый также Скайп и Скайп для собраний Бизнеса.</span><span class="sxs-lookup"><span data-stu-id="dfa15-118">To complement the Teams capability as a persistent chat board where informal, real-time conversations take place, Teams also provides a calling and meeting experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="dfa15-119">К таким технологическим нововведениям относятся облачные службы для обработки мультимедиа и сигнализации на основе Azure, видеокодек H.264, аудиокодек SILK и Opus, устойчивость сети, телеметрия и диагностика качества связи.</span><span class="sxs-lookup"><span data-stu-id="dfa15-119">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="dfa15-120">Группы Office 365 используют удостоверения, хранящиеся в Azure Active Directory (Azure AD), поэтому все возможности проверки подлинности и авторизации в Azure AD, например поддержка многофакторной проверки подлинности (MFA), готовы к использованию в Teams.</span><span class="sxs-lookup"><span data-stu-id="dfa15-120">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), are readily available for use by Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="dfa15-121">На основании отзывов клиентов, новые группы Office 365, в результате создания группы в группах Microsoft больше не отображается в Outlook по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dfa15-121">Based on customer feedback, new Office 365 Groups generated as a result of creating a team in Microsoft Teams will no longer show in Outlook by default.</span></span> <span data-ttu-id="dfa15-122">Для клиентов, которые хотите продолжить поведение отображение этих групп в Outlook это командлет Exchange Online PowerShell будет предоставляться которого можно включить в группу по возможности Outlook.</span><span class="sxs-lookup"><span data-stu-id="dfa15-122">For customers that want to continue with the existing behavior of showing these groups in Outlook, an Exchange Online PowerShell cmdlet will be provided which can enable the group for the Outlook experience.</span></span> <span data-ttu-id="dfa15-123">Отображение в Outlook и рабочих групп будет предоставляться групп созданных с помощью Outlook и более поздних версий включен для групп.</span><span class="sxs-lookup"><span data-stu-id="dfa15-123">Groups created through Outlook and then later enabled for Teams will continue to show in both Outlook and Teams.</span></span> <span data-ttu-id="dfa15-124">Это обновление будет постепенно roll выход между Outlook и рабочих групп в ближайшее.</span><span class="sxs-lookup"><span data-stu-id="dfa15-124">This update will gradually roll out across Outlook and Teams in the coming months.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="dfa15-125">Microsoft Teams и Office 365</span><span class="sxs-lookup"><span data-stu-id="dfa15-125">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="dfa15-126">Разные группы имеют разные потребности, основанные на их функциональной роли и стиле работы.</span><span class="sxs-lookup"><span data-stu-id="dfa15-126">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="dfa15-127">Office 365 подходит для любого стиля работы и содержит специализированные интегрированные приложения, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="dfa15-127">Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, including:</span></span>

-   <span data-ttu-id="dfa15-128">Outlook для работы с электронной почтой на корпоративном уровне, сейчас также поддерживает работу с группами.</span><span class="sxs-lookup"><span data-stu-id="dfa15-128">Outlook for enterprise-grade email, now with groups functionality</span></span>

-   <span data-ttu-id="dfa15-129">SharePoint для сайтов и порталов, служб интеллектуальной работы с контентом, автоматизации бизнес-процессов и поиска в корпоративной среде.</span><span class="sxs-lookup"><span data-stu-id="dfa15-129">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search</span></span>

-   <span data-ttu-id="dfa15-130">Yammer для взаимодействия внутри организации.</span><span class="sxs-lookup"><span data-stu-id="dfa15-130">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="dfa15-131">Skype для бизнеса в качестве основы корпоративной голосовой и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="dfa15-131">Skype for Business as the backbone for enterprise voice and video</span></span>

-   <span data-ttu-id="dfa15-132">А теперь и Microsoft Teams — новую рабочую область на основе чата в Office 365.</span><span class="sxs-lookup"><span data-stu-id="dfa15-132">And now, Microsoft Teams, the new chat-based workspace in Office 365</span></span>

<span data-ttu-id="dfa15-133">Ниже приведены распространенные варианты использования каждого из приложений в Office 365.</span><span class="sxs-lookup"><span data-stu-id="dfa15-133">Here are common use cases for each application in Office 365.</span></span> <span data-ttu-id="dfa15-134">Подробные сведения об использовании см. в [библиотеке производительности FastTrack](https://go.microsoft.com/fwlink/?linkid=854630).</span><span class="sxs-lookup"><span data-stu-id="dfa15-134">For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![Значок Microsoft Teams.](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="dfa15-136">Используется сотрудниками и командами, которым требуется в реальном времени осуществлять совместную работу внутри одной группы лиц.</span><span class="sxs-lookup"><span data-stu-id="dfa15-136">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="dfa15-137">Помогает командам ускорить реализацию проекта за счет общего доступа к файлам и совместной работы над результатами.</span><span class="sxs-lookup"><span data-stu-id="dfa15-137">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="dfa15-138">Позволяет пользователям подключаться широкий спектр средств в своей рабочей области (например, планировщик работы Power BI, репозиториев, и т.д.).</span><span class="sxs-lookup"><span data-stu-id="dfa15-138">Allows users to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![Значок Microsoft Outlook.](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="dfa15-140">Используется сотрудниками, предпочитающими совместно работать в привычной среде посредством электронной почты и (или) более формальным и упорядоченным образом.</span><span class="sxs-lookup"><span data-stu-id="dfa15-140">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="dfa15-141">Предоставляет определенные бизнес-процессы, требующие использования электронной почты для передачи информации и документов через границы корпоративной среды.</span><span class="sxs-lookup"><span data-stu-id="dfa15-141">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="dfa15-142">Позволяет общаться и взаимодействовать с пользователями, находящимися за пределами рабочих групп или организаций.</span><span class="sxs-lookup"><span data-stu-id="dfa15-142">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![Значок Yammer.](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="dfa15-144">Помогает пользователям взаимодействовать друг с другом внутри организации для формирования сообществ и обмена рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="dfa15-144">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="dfa15-145">Улучшает функциональные рабочие процессы за счет открытой и прозрачной платформы на основе веб-каналов.</span><span class="sxs-lookup"><span data-stu-id="dfa15-145">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="dfa15-146">Активизирует взаимодействие между начальством и сотрудниками в формате двусторонних бесед.</span><span class="sxs-lookup"><span data-stu-id="dfa15-146">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="dfa15-147">Помогает рядовым сотрудникам обмениваться знаниями и опытом.</span><span class="sxs-lookup"><span data-stu-id="dfa15-147">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![Значок Skype для бизнеса.](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="dfa15-149">Используется для взаимодействия и совместной работы в реальном времени как внутри организации, так и за ее пределами (с клиентами или партнерами).</span><span class="sxs-lookup"><span data-stu-id="dfa15-149">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="dfa15-150">Позволяет проводить собрания с функциями голосовой и видеосвязи, а также работы с контентом для небольших или крупных команд (включая муниципалитеты с числом участников до 10 000 человек).</span><span class="sxs-lookup"><span data-stu-id="dfa15-150">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="dfa15-151">Предоставляет функции корпоративной телефонии.</span><span class="sxs-lookup"><span data-stu-id="dfa15-151">Offers enterprise telephony functionality.</span></span>


![Значок Microsoft SharePoint.](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="dfa15-153">Используется для сайтов и порталов (например, для публикации новостей и объявлений, поиска и совместного использования документов).</span><span class="sxs-lookup"><span data-stu-id="dfa15-153">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="dfa15-154">Обеспечивает автоматизацию бизнес-процессов для библиотек документов и списков сведений за счет интеграции с Microsoft Flow и PowerApps.</span><span class="sxs-lookup"><span data-stu-id="dfa15-154">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="dfa15-155">Для каждой команды автоматически подготавливается полнофункциональный сайт группы SharePoint для хранения файлов, новостей, страниц, списков и т. п.</span><span class="sxs-lookup"><span data-stu-id="dfa15-155">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="dfa15-156">См. статью [Взаимодействие SharePoint Online и OneDrive для бизнеса с Teams](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="dfa15-156">See [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md)</span></span>

## <a name="teams-known-issuesknown-issuesmd"></a>[<span data-ttu-id="dfa15-157">Известные проблемы Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dfa15-157">Teams known issues</span></span>](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[<span data-ttu-id="dfa15-158">Заметки о выпуске клиента Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dfa15-158">Teams client release notes</span></span>](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)

## <a name="what-happened-to-the-teams-admin-faq"></a><span data-ttu-id="dfa15-159">Что случилось с вопросами и ответами для администраторов Teams?</span><span class="sxs-lookup"><span data-stu-id="dfa15-159">What happened to the Teams admin FAQ?</span></span>

<span data-ttu-id="dfa15-160">Хотя изначально статья с вопросами и ответами для администраторов Teams была довольно удобной, она быстро превратилась в нагромождение самых разных сведений, что затруднило поиск нужной информации.</span><span class="sxs-lookup"><span data-stu-id="dfa15-160">While the Teams Admin FAQ was handy when we first released Teams, it quickly became a "junk drawer" that made it hard to find anything specific.</span></span> <span data-ttu-id="dfa15-161">Поэтому мы извлекли оттуда все самое ценное и внесли в документацию Teams, которую вы и просматриваете прямо сейчас.</span><span class="sxs-lookup"><span data-stu-id="dfa15-161">So we busted apart the FAQ and incorporated its valuable information into the Teams documentation that you're looking at right now.</span></span> <span data-ttu-id="dfa15-162">В ней вся информация из вопросов и ответов приведена с учетом контекста.</span><span class="sxs-lookup"><span data-stu-id="dfa15-162">You'll find all the information that was in the FAQ in this documentation, in context.</span></span>

<span data-ttu-id="dfa15-163">Если вы ищете то, что вы не можете найти здесь, сообщите о нем в представленном ниже разделе **свои отзывы и предложения** .</span><span class="sxs-lookup"><span data-stu-id="dfa15-163">If you're looking for something that you can't find here, please tell us about it in the **Feedback** section below.</span></span> <span data-ttu-id="dfa15-164">Мы попробуйте реагировать на ваш отзыв в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="dfa15-164">We try to respond to your feedback within 24 hours.</span></span>

<span data-ttu-id="dfa15-165">Следует отметить, что мы **все еще** используем вопросы и ответы по [переходу со Skype для бизнеса на Microsoft Teams](FAQ-journey.md).</span><span class="sxs-lookup"><span data-stu-id="dfa15-165">By the way, we **do** still have an FAQ for the [Journey from Skype for Business to Microsoft Teams](FAQ-journey.md).</span></span> 
