---
title: Запуск отчета для отображения активного использования StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Сведения о том, как запустить отчет, чтобы получить список активных пользователей StaffHub в вашей организации.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe7851e57cd6d812d0b8904668ca5fd67fd5999d
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826697"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="9ea28-103">Запуск отчета для отображения активного использования StaffHub</span><span class="sxs-lookup"><span data-stu-id="9ea28-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ea28-104">Вступление в силу 31 декабря 2019 г. Корпорация Microsoft StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="9ea28-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="9ea28-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9ea28-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="9ea28-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="9ea28-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="9ea28-107">StaffHub перестанет работать для всех пользователей 31 декабря 2019 г.</span><span class="sxs-lookup"><span data-stu-id="9ea28-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="9ea28-108">Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="9ea28-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="9ea28-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="9ea28-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="9ea28-110">Выполните действия, описанные в этой статье, чтобы запустить отчет, чтобы получить список активных пользователей StaffHub в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9ea28-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="9ea28-111">Эта информация может пригодиться, когда вы готовитесь к [перемещению StaffHubных групп в Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9ea28-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="9ea28-112">В отчете вы узнаете, какие пользователи должны быть включены в вашу связь при переходе с StaffHub на Teams.</span><span class="sxs-lookup"><span data-stu-id="9ea28-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="9ea28-113">Для выполнения действий, описанных в этой статье, необходимо иметь Azure AD Premium.</span><span class="sxs-lookup"><span data-stu-id="9ea28-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="9ea28-114">Войдите на портал Azure.</span><span class="sxs-lookup"><span data-stu-id="9ea28-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="9ea28-115">В левой области выберите ресурс **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="9ea28-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="9ea28-116">В разделе **мониторинг**щелкните элемент **Вход**.</span><span class="sxs-lookup"><span data-stu-id="9ea28-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="9ea28-117">В разделе **приложение**введите **Microsoft StaffHub**.</span><span class="sxs-lookup"><span data-stu-id="9ea28-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="9ea28-118">Укажите диапазон дат для отчета и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="9ea28-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Снимок экрана, показывающий, как показать использование активного StaffHub](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="9ea28-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9ea28-120">Related topics</span></span>

- [<span data-ttu-id="9ea28-121">Перемещайте Microsoft StaffHub Teams по сменам в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9ea28-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
