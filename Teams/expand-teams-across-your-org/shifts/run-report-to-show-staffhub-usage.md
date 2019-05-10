---
title: Запуск отчета для отображения active StaffHub об использовании
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 05/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Узнайте, как создать отчет, чтобы получить список активных пользователей StaffHub в вашей организации.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e66e889fbc7fb26b8fda55beb889bc95b155666d
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "33868200"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="40fc9-103">Запуск отчета для отображения active StaffHub об использовании</span><span class="sxs-lookup"><span data-stu-id="40fc9-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40fc9-104">Начиная с 1 октября 2019, Microsoft StaffHub будет из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="40fc9-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="40fc9-105">Мы создаем StaffHub возможностей в группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="40fc9-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="40fc9-106">В настоящее время группы включает в себя приложение смены для управление планированием и дополнительные возможности будут развернуты со временем.</span><span class="sxs-lookup"><span data-stu-id="40fc9-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="40fc9-107">StaffHub перестанет работать для всех пользователей на 1 октября 2019.</span><span class="sxs-lookup"><span data-stu-id="40fc9-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="40fc9-108">Кто-то пытается открыть StaffHub отображается сообщение, предлагая загрузить групп.</span><span class="sxs-lookup"><span data-stu-id="40fc9-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="40fc9-109">Для получения дополнительных сведений см [Microsoft StaffHub из эксплуатации](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="40fc9-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="40fc9-110">Используйте действия, описанные в этой статье для запуска отчета, чтобы получить список активных пользователей StaffHub в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="40fc9-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="40fc9-111">Эти сведения могут пригодиться при подготовке к [Перемещение группам StaffHub группами Майкрософт](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="40fc9-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="40fc9-112">Из отчета вы узнаете, то необходимо включить в ваши сообщения при внесении группам параметр StaffHub.</span><span class="sxs-lookup"><span data-stu-id="40fc9-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="40fc9-113">Необходимо иметь Premium Azure AD для выполнения действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="40fc9-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="40fc9-114">Вход на портал Azure.</span><span class="sxs-lookup"><span data-stu-id="40fc9-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="40fc9-115">В левой области выберите ресурс **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="40fc9-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="40fc9-116">В разделе **мониторинг**щелкните **войти в систему**.</span><span class="sxs-lookup"><span data-stu-id="40fc9-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="40fc9-117">В разделе **приложения**введите **Microsoft StaffHub**.</span><span class="sxs-lookup"><span data-stu-id="40fc9-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="40fc9-118">Задайте диапазон дат, который необходимо использовать для отчета и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="40fc9-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Снимок экрана, отображение действия для выполнения отчета для отображения активного использования StaffHub на портале Azure](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="40fc9-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="40fc9-120">Related topics</span></span>

- [<span data-ttu-id="40fc9-121">Перемещение ваших команд Microsoft StaffHub смены в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="40fc9-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
