---
title: Запуск отчета для отображения активного использования StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 05/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как запустить отчет, чтобы получить список активных пользователей StaffHub в вашей организации.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59931183cadec09b2fc26a55cf7e284f51198efc
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548209"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="bf1cc-103">Запуск отчета для отображения активного использования StaffHub</span><span class="sxs-lookup"><span data-stu-id="bf1cc-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf1cc-104">Начиная с 1 октября 2019 г. Корпорация Microsoft StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="bf1cc-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="bf1cc-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bf1cc-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="bf1cc-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="bf1cc-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="bf1cc-107">StaffHub перестанет работать для всех пользователей 1 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="bf1cc-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="bf1cc-108">Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="bf1cc-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="bf1cc-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="bf1cc-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="bf1cc-110">Выполните действия, описанные в этой статье, чтобы запустить отчет, чтобы получить список активных пользователей StaffHub в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bf1cc-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="bf1cc-111">Эта информация может пригодиться, когда вы готовитесь к [перемещению StaffHubных групп в Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bf1cc-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="bf1cc-112">В отчете вы узнаете, какие пользователи должны быть включены в вашу связь при переходе с StaffHub на Teams.</span><span class="sxs-lookup"><span data-stu-id="bf1cc-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="bf1cc-113">Для выполнения действий, описанных в этой статье, необходимо иметь Azure AD Premium.</span><span class="sxs-lookup"><span data-stu-id="bf1cc-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="bf1cc-114">Войдите на портал Azure.</span><span class="sxs-lookup"><span data-stu-id="bf1cc-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="bf1cc-115">В левой области выберите ресурс **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="bf1cc-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="bf1cc-116">В разделе **мониторинг**щелкните элемент **Вход**.</span><span class="sxs-lookup"><span data-stu-id="bf1cc-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="bf1cc-117">В разделе **приложение**введите **Microsoft StaffHub**.</span><span class="sxs-lookup"><span data-stu-id="bf1cc-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="bf1cc-118">Укажите диапазон дат для отчета и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="bf1cc-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Снимок экрана, показывающий, как показать использование активного StaffHub](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="bf1cc-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bf1cc-120">Related topics</span></span>

- [<span data-ttu-id="bf1cc-121">Перемещайте Microsoft StaffHub Teams по сменам в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bf1cc-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
