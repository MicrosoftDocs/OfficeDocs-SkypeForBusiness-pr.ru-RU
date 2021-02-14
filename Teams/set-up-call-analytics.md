---
title: Настройка аналитики вызовов для Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Настроив аналитические данные о звонках для каждого пользователя, вы сможете выявлять и устранять проблемы с качеством звонка в Microsoft Teams.
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581110"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="8c552-103">Настройка аналитики вызовов для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c552-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="8c552-104">Как администратор Microsoft Teams вы можете использовать аналитические данные по звонкам для отдельных пользователей для устранения неполадок с качеством звонка и соединением Teams для **отдельных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="8c552-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="8c552-105">Чтобы воспользоваться аналитическими данными о звонках, установите следующее:</span><span class="sxs-lookup"><span data-stu-id="8c552-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="8c552-106">Назначьте специализированные роли поддержки людям, например агентам службы технической поддержки, чтобы они просмотрели аналитику вызовов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="8c552-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="8c552-107">Эти роли поддержки не могут получить доступ к остальным центрам администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="8c552-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="8c552-108">Добавьте сведения о здании, участке и клиенте в аналитику вызовов для каждого пользователя, загрузив TSV- или CSV-файл данных.</span><span class="sxs-lookup"><span data-stu-id="8c552-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="8c552-109">Когда вы будете готовы приступить к использованию аналитических данных по звонкам для каждого пользователя, ознакомьтесь с этой статьей, чтобы узнать, как устранить неполадки с качеством [звонка.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="8c552-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="8c552-110">Предоставить разрешение на поддержку и сотрудников службы технической поддержки</span><span class="sxs-lookup"><span data-stu-id="8c552-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="8c552-111">Как администратор Teams вы можете получить полный доступ к аналитическим сведениям о звонках для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="8c552-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="8c552-112">Мы создали несколько специализированных ролей Azure Active Directory, которые можно назначать сотрудникам службы поддержки и агентам службы технической поддержки, чтобы они также могли получать доступ к аналитике вызовов для отдельных пользователей (без доступа к остальной части Центра администрирования Teams).</span><span class="sxs-lookup"><span data-stu-id="8c552-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="8c552-113">**Назначьте роль** специалиста по поддержке связи в Teams пользователям, которые должны иметь ограниченный доступ к аналитике вызовов для каждого пользователя (поддержка уровня 1).</span><span class="sxs-lookup"><span data-stu-id="8c552-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="8c552-114">**Назначьте роль** инженера службы поддержки связи Teams пользователям, которым необходим полный доступ к аналитике вызовов для каждого пользователя (поддержка уровня 2).</span><span class="sxs-lookup"><span data-stu-id="8c552-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="8c552-115">У обеих ролей нет доступа к остальным центрам администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="8c552-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="8c552-116">Чтобы узнать, что делает каждая из этих ролей, прочитайте статью "Что делает каждая роль службы поддержки [Teams"?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)</span><span class="sxs-lookup"><span data-stu-id="8c552-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="8c552-117">Дополнительные сведения о ролях администраторов Teams см. [в](using-admin-roles.md)этом случае.</span><span class="sxs-lookup"><span data-stu-id="8c552-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="8c552-118">Чтобы узнать, как назначать роли администраторов в Azure Active Directory, см. функции просмотра и назначения ролей [в Azure Active Directory.](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)</span><span class="sxs-lookup"><span data-stu-id="8c552-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="8c552-119">Чтобы узнать, как назначать административные роли в Azure Active Directory, см. функции просмотра и назначения ролей [в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)</span><span class="sxs-lookup"><span data-stu-id="8c552-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="8c552-120">Добавление TSV- или CSV-файла для добавления сведений о здании, участке и клиенте</span><span class="sxs-lookup"><span data-stu-id="8c552-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="8c552-121">Вы можете добавить сведения о здании, участке и клиенте в аналитику вызовов для каждого пользователя, загрузив CSV- или TSV-файл.</span><span class="sxs-lookup"><span data-stu-id="8c552-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="8c552-122">Благодаря этой информации средства аналитики вызовов могут соедистрять IP-адреса с физическими расположениями.</span><span class="sxs-lookup"><span data-stu-id="8c552-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="8c552-123">Администраторы и агенты службы справки могут использовать эти сведения для выявить тенденции проблем со звонками.</span><span class="sxs-lookup"><span data-stu-id="8c552-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="8c552-124">Например, почему у пользователей в одном здании похожие проблемы с качеством звонка?</span><span class="sxs-lookup"><span data-stu-id="8c552-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="8c552-125">Если вы администратор Teams или Skype для бизнеса, вы можете использовать существующий файл данных клиента и здания из панели мониторинга качества звонков Teams или Skype для бизнеса (CQD).</span><span class="sxs-lookup"><span data-stu-id="8c552-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="8c552-126">Сначала скачайте файл из CQD, а затем загрузите его в аналитику вызовов.</span><span class="sxs-lookup"><span data-stu-id="8c552-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="8c552-127">Чтобы скачать существующий файл данных, перейдите на панель мониторинга качества звонка в Центре администрирования **Microsoft Teams.**  >    >  </span><span class="sxs-lookup"><span data-stu-id="8c552-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="8c552-128">В **списке "Мои загрузки"** щелкните **ссылку** "Скачать" рядом с нужным файлом.</span><span class="sxs-lookup"><span data-stu-id="8c552-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="8c552-129">Чтобы отправить новый файл, перейдите в Центр администрирования **Microsoft Teams** и выберите "Отправить данные о расположении" или  >  "Заменить данные о **расположении".** </span><span class="sxs-lookup"><span data-stu-id="8c552-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="8c552-130">Если вы создаете TSV- или CSV-файл с нуля, см. сведения о загрузке клиента [и здания.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="8c552-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8c552-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8c552-131">Related topics</span></span>

[<span data-ttu-id="8c552-132">Использование аналитических данных по звонкам для каждого пользователя для устранения неполадок с качеством звонка</span><span class="sxs-lookup"><span data-stu-id="8c552-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="8c552-133">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="8c552-133">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
