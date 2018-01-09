---
title: "Обзор Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о продукте Microsoft Teams, его инфраструктуре и использовании вместе с Office 365."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: c856e85ddd6ef824e7826c4b4752a3fbb15508e5
ms.sourcegitcommit: d5d9a9f9d7765cb615ab9fac88a7695c60210cfc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/02/2018
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="b5fc7-103">Обзор Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5fc7-103">Overview of Microsoft Teams</span></span>
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


<span data-ttu-id="b5fc7-104">Microsoft Teams наследует масштабность и охват Office 365, предоставляя основанный на чате центр для командной работы и позволяя клиентам сформировать более открытую, гибкую и цифровую среду.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-104">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment.</span></span> <span data-ttu-id="b5fc7-105">Microsoft Teams реализован на базе существующих технологий, объединяемых Группами Office 365.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-105">Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="b5fc7-106">Teams сразу же использует удостоверения, хранящиеся в Azure Active Directory (Azure AD), и интегрируется с другими службами в Office 365, чтобы предоставить сайт SharePoint Online и почтовый ящик группы Exchange Online для каждой создаваемой команды.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-106">Out of the box, Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="b5fc7-107">Функция сохраняемого чата Teams реализуется службой чатов, которая взаимодействует с базовым Office 365, и предоставляет множество встроенных возможностей Office 365, например архивацию и обнаружение электронных данных, для передаваемых внутри Teams данных.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-107">The Teams persistent chat capability is provided by a chat service that interacts with the Office 365 substrate, surfacing many of the built-in Office 365 capabilities, such as archiving and eDiscovery to the data being exchanged in Teams.</span></span>

<span data-ttu-id="b5fc7-108">Кроме того, в Teams представлен интерфейс звонков и собраний, основанный на облачной инфраструктуре следующего поколения, которая также применяется в Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-108">Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="b5fc7-109">К таким технологическим нововведениям относятся облачные службы для обработки мультимедиа и сигнализации на основе Azure, видеокодек H.264, аудиокодек SILK и Opus, устойчивость сети, телеметрия и диагностика качества связи.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-109">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="b5fc7-110">Для расширения возможностей Teams используйте соединители, вкладки и боты, доступные как [Приложения](https://go.microsoft.com/fwlink/?linkid=854629) и позволяющие взаимодействовать с внешней информацией, контентом и интеллектуальными ботами.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-110">To extend Teams capabilities, use Connectors, Tabs, and Bots - available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629), to bring external information, content, and intelligent bot interactions to Teams.</span></span>

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="b5fc7-111">Инфраструктура Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5fc7-111">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="b5fc7-112">Teams реализован на базе существующих технологий, объединяемых Группами Office 365.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-112">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="b5fc7-113">Благодаря возможностям Microsoft Cloud организации могут обеспечить превосходную производительность и надежность при использовании Teams для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-113">Powered by the Microsoft cloud, organizations can expect excellent performance and reliability when leveraging Teams as part of their collaboration story.</span></span>

<span data-ttu-id="b5fc7-114">Для созданной в Teams команды сразу же создается группа Office 365, сайт SharePoint Online (дополненный библиотекой документов) и почтовый ящик группы Exchange Online, который будет использоваться Teams для хранения такой информации, как приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-114">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="b5fc7-115">Команду можно создать с использованием существующих Групп Office 365, разрешив существующие членства в группах и перенеся контент из SharePoint Online и Exchange Online в Teams.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-115">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="b5fc7-116">Функция сохраняемого чата Teams реализуется службой чатов, которая взаимодействует с Office 365, и предоставляет множество встроенных возможностей Office 365, например архивацию и обнаружение электронных данных, для передаваемых внутри Teams данных.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-116">Teams persistent chat is provided by a chat service that interacts with Office 365, surfacing many of the built-in Office 365 capabilities such as archiving and eDiscovery to the data being exchanged in Teams.</span></span>

<span data-ttu-id="b5fc7-117">Чтобы дополнить возможности по использованию Teams в качестве доски сохраняемого чата, где проходят неформальные беседы в режиме реального времени, в Teams также представлен интерфейс звонков и собраний, основанный на облачной инфраструктуре следующего поколения, которая также применяется в Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-117">To complement the Teams capability as a persistent chat board where informal, real-time conversations take place, Teams also provides a meeting experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="b5fc7-118">К таким технологическим нововведениям относятся облачные службы для обработки мультимедиа и сигнализации на основе Azure, видеокодек H.264, аудиокодек SILK и Opus, устойчивость сети, телеметрия и диагностика качества связи.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-118">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="b5fc7-119">Группы Office 365 используют удостоверения, хранящиеся в Azure Active Directory (Azure AD), поэтому все возможности проверки подлинности и авторизации в Azure AD, например поддержка многофакторной проверки подлинности (MFA), готовы к использованию в Teams.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-119">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), are readily available for use by Teams.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="b5fc7-120">Microsoft Teams и Office 365</span><span class="sxs-lookup"><span data-stu-id="b5fc7-120">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="b5fc7-121">Разные группы имеют разные потребности, основанные на их функциональной роли и стиле работы.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-121">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="b5fc7-122">Office 365 подходит для любого стиля работы и содержит специализированные интегрированные приложения, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="b5fc7-122">Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, including:</span></span>

-   <span data-ttu-id="b5fc7-123">Outlook для работы с электронной почтой на корпоративном уровне, сейчас также поддерживает работу с группами.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-123">Outlook for enterprise-grade email, now with groups functionality</span></span>

-   <span data-ttu-id="b5fc7-124">SharePoint для сайтов и порталов, служб интеллектуальной работы с контентом, автоматизации бизнес-процессов и поиска в корпоративной среде.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-124">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search</span></span>

-   <span data-ttu-id="b5fc7-125">Yammer для взаимодействия внутри организации.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-125">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="b5fc7-126">Skype для бизнеса в качестве основы корпоративной голосовой и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-126">Skype for Business as the backbone for enterprise voice and video</span></span>

-   <span data-ttu-id="b5fc7-127">А теперь и Microsoft Teams — новую рабочую область на основе чата в Office 365.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-127">And now, Microsoft Teams, the new chat-based workspace in Office 365</span></span>

<span data-ttu-id="b5fc7-128">Ниже приведены распространенные варианты использования каждого из приложений в Office 365.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-128">Here are common use cases for each application in Office 365.</span></span> <span data-ttu-id="b5fc7-129">Подробные сведения об использовании см. в [библиотеке производительности FastTrack](https://go.microsoft.com/fwlink/?linkid=854630).</span><span class="sxs-lookup"><span data-stu-id="b5fc7-129">For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![Значок Microsoft Teams.](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="b5fc7-131">Используется сотрудниками и командами, которым требуется в реальном времени осуществлять совместную работу внутри одной группы лиц.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-131">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="b5fc7-132">Помогает командам ускорить реализацию проекта за счет общего доступа к файлам и совместной работы над результатами.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-132">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="b5fc7-133">Подходит для пользователей, стремящихся подключить к своей рабочей области большое количество разнообразных средств (например, Планировщик, Power BI, GitHub и т. д.).</span><span class="sxs-lookup"><span data-stu-id="b5fc7-133">Allows Users looking to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![Значок Microsoft Outlook.](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="b5fc7-135">Используется сотрудниками, предпочитающими совместно работать в привычной среде посредством электронной почты и (или) более формальным и упорядоченным образом.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-135">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="b5fc7-136">Предоставляет определенные бизнес-процессы, требующие использования электронной почты для передачи информации и документов через границы корпоративной среды.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-136">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="b5fc7-137">Позволяет общаться и взаимодействовать с пользователями, находящимися за пределами рабочих групп или организаций.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-137">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![Значок Yammer.](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="b5fc7-139">Помогает пользователям взаимодействовать друг с другом внутри организации для формирования сообществ и обмена рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-139">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="b5fc7-140">Улучшает функциональные рабочие процессы за счет открытой и прозрачной платформы на основе веб-каналов.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-140">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="b5fc7-141">Активизирует взаимодействие между начальством и сотрудниками в формате двусторонних бесед.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-141">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="b5fc7-142">Помогает рядовым сотрудникам обмениваться знаниями и опытом.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-142">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![Значок Skype для бизнеса.](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="b5fc7-144">Используется для взаимодействия и совместной работы в реальном времени как внутри организации, так и за ее пределами (с клиентами или партнерами).</span><span class="sxs-lookup"><span data-stu-id="b5fc7-144">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="b5fc7-145">Позволяет проводить собрания с функциями голосовой и видеосвязи, а также работы с контентом для небольших или крупных команд (включая муниципалитеты с числом участников до 10 000 человек).</span><span class="sxs-lookup"><span data-stu-id="b5fc7-145">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="b5fc7-146">Предоставляет функции корпоративной телефонии.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-146">Offers enterprise telephony functionality.</span></span>


![Значок Microsoft SharePoint.](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="b5fc7-148">Используется для сайтов и порталов (например, для публикации новостей и объявлений, поиска и совместного использования документов).</span><span class="sxs-lookup"><span data-stu-id="b5fc7-148">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="b5fc7-149">Обеспечивает автоматизацию бизнес-процессов для библиотек документов и списков сведений за счет интеграции с Microsoft Flow и PowerApps.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-149">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="b5fc7-150">Для каждой команды автоматически подготавливается полнофункциональный сайт группы SharePoint для хранения файлов, новостей, страниц, списков и т. п.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-150">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="b5fc7-151">См. статью [Взаимодействие SharePoint Online и OneDrive для бизнеса с Teams](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="b5fc7-151">See [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md)</span></span>

## <a name="what-happened-to-the-teams-admin-faq"></a><span data-ttu-id="b5fc7-152">Что случилось с вопросами и ответами для администраторов Teams?</span><span class="sxs-lookup"><span data-stu-id="b5fc7-152">What happened to the Teams admin FAQ?</span></span>

<span data-ttu-id="b5fc7-153">Хотя изначально статья с вопросами и ответами для администраторов Teams была довольно удобной, она быстро превратилась в нагромождение самых разных сведений, что затруднило поиск нужной информации.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-153">While the Teams Admin FAQ was handy when we first released Teams, it quickly became a "junk drawer" that made it hard to find anything specific.</span></span> <span data-ttu-id="b5fc7-154">Поэтому мы извлекли оттуда все самое ценное и внесли в документацию Teams, которую вы и просматриваете прямо сейчас.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-154">So we busted apart the FAQ and incorporated its valuable information into the Teams documentation that you're looking at right now.</span></span> <span data-ttu-id="b5fc7-155">В ней вся информация из вопросов и ответов приведена с учетом контекста.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-155">You'll find all the information that was in the FAQ in this documentation, in context.</span></span>

<span data-ttu-id="b5fc7-156">Если вам не удается найти здесь какие-либо сведения, сообщите нам об этом в разделе **комментариев** ниже.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-156">If you're looking for something that you can't find here, please tell us about it in the **Comments** section below.</span></span> <span data-ttu-id="b5fc7-157">Мы стараемся отвечать на комментарии в течение 24 часов.</span><span class="sxs-lookup"><span data-stu-id="b5fc7-157">We try to respond to your comments within 24 hours.</span></span>

<span data-ttu-id="b5fc7-158">Следует отметить, что мы **все еще** используем вопросы и ответы по [переходу со Skype для бизнеса на Microsoft Teams](FAQ-journey.md).</span><span class="sxs-lookup"><span data-stu-id="b5fc7-158">By the way, we **do** still have an FAQ for the [Journey from Skype for Business to Microsoft Teams](FAQ-journey.md).</span></span> 