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
description: Настройка аналитики вызовов для каждого пользователя для выявления и устранения Microsoft Teams проблем с качеством звонка.
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117137"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="a56ed-103">Настройка аналитики вызовов для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a56ed-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="a56ed-104">Как администратор Microsoft Teams вы можете использовать аналитические данные о звонках для отдельных пользователей для устранения Teams качества звонка и проблем с подключением для **отдельных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="a56ed-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="a56ed-105">Чтобы использовать все возможности аналитики вызовов, необходимо настроить следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="a56ed-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="a56ed-106">Назначайте специализированные роли поддержки людям, например агентам службы технической поддержки, чтобы они просматривали аналитику вызовов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a56ed-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="a56ed-107">Эти роли поддержки не могут получить доступ к остальным Teams центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="a56ed-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="a56ed-108">Добавьте сведения о здании, сайте и клиенте в аналитические данные о звонках для каждого пользователя, загрузив TSV- или .csv данных.</span><span class="sxs-lookup"><span data-stu-id="a56ed-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="a56ed-109">Когда вы будете готовы приступить к анализу вызовов для каждого пользователя, ознакомьтесь со статьей Использование аналитики вызовов для каждого пользователя для устранения неполадок [с качеством звонка.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="a56ed-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="a56ed-110">Предоставить разрешение на поддержку и поддержку сотрудников службы технической поддержки</span><span class="sxs-lookup"><span data-stu-id="a56ed-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="a56ed-111">Как администратор Teams, вы имеете полный доступ к аналитике вызовов для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="a56ed-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="a56ed-112">Мы создали несколько специализированных ролей Azure Active Directory, которые можно назначать сотрудникам службы поддержки и агентам службы технической поддержки, чтобы они также могли получать доступ к аналитике вызовов для отдельных пользователей (без доступа к остальной части центра администрирования Teams службы поддержки).</span><span class="sxs-lookup"><span data-stu-id="a56ed-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="a56ed-113">**Назначьте Teams** связи со службой поддержки связи пользователям, у которых должно быть ограниченное представление аналитики вызовов для каждого пользователя (поддержка уровня 1).</span><span class="sxs-lookup"><span data-stu-id="a56ed-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="a56ed-114">**Назначьте Teams службе** поддержки связи пользователям, которым нужен полный доступ к аналитике вызовов для каждого пользователя (поддержка уровня 2).</span><span class="sxs-lookup"><span data-stu-id="a56ed-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="a56ed-115">У обеих ролей нет доступа к остальной части Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="a56ed-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="a56ed-116">Чтобы узнать, что делает каждая из этих ролей, ознакомьтесь со Teams [должности службы поддержки?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)</span><span class="sxs-lookup"><span data-stu-id="a56ed-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="a56ed-117">Дополнительные сведения о ролях Teams администраторов см. в Teams роли администратора [для Teams.](using-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="a56ed-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="a56ed-118">Чтобы узнать, как назначать роли администраторов в Azure Active Directory, см. просмотр и назначение ролей [в](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a56ed-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="a56ed-119">Чтобы узнать, как назначать административные роли в Azure Active Directory, см. просмотр и назначение ролей [в Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)</span><span class="sxs-lookup"><span data-stu-id="a56ed-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="a56ed-120">Upload файл tsv или .csv для добавления сведений о здании, сайте и клиенте</span><span class="sxs-lookup"><span data-stu-id="a56ed-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="a56ed-121">Вы можете добавить сведения о здании, сайте и клиенте в аналитические данные о звонках для каждого пользователя, загрузив .csv или TSV-файл.</span><span class="sxs-lookup"><span data-stu-id="a56ed-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="a56ed-122">Вся эта информация позволяет средству аналитики вызовов соединать IP-адреса с физическими расположениями.</span><span class="sxs-lookup"><span data-stu-id="a56ed-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="a56ed-123">Администраторы и агенты службы справки могут использовать эти сведения, чтобы выявить тенденции проблем со звонками.</span><span class="sxs-lookup"><span data-stu-id="a56ed-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="a56ed-124">Например, почему у пользователей в одном здании похожие проблемы с качеством звонка?</span><span class="sxs-lookup"><span data-stu-id="a56ed-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="a56ed-125">Если вы администратор Teams или Skype для бизнеса, вы можете использовать существующий файл данных клиента и здания из панели мониторинга качества Teams или Skype для бизнеса (CQD).</span><span class="sxs-lookup"><span data-stu-id="a56ed-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="a56ed-126">Сначала скачайте файл из CQD, а затем загрузите его в аналитику вызовов.</span><span class="sxs-lookup"><span data-stu-id="a56ed-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="a56ed-127">Чтобы скачать существующий файл данных, перейдите в центр **администрирования** Microsoft Teams  >  **панели**  >  **Upload.**</span><span class="sxs-lookup"><span data-stu-id="a56ed-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="a56ed-128">В **списке Мои загрузки** щелкните **Скачать** рядом с нужным файлом.</span><span class="sxs-lookup"><span data-stu-id="a56ed-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="a56ed-129">Чтобы добавить новый файл, перейдите в Microsoft Teams **в** Центре администрирования , а затем выберите Upload или  >   **Заменить данные о расположении**. </span><span class="sxs-lookup"><span data-stu-id="a56ed-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="a56ed-130">Если вы создаете TSV- или .csv с нуля, см. Upload [клиента и данных о здании.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="a56ed-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a56ed-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a56ed-131">Related topics</span></span>

[<span data-ttu-id="a56ed-132">Использование аналитических данных о звонках для каждого пользователя для устранения неполадок с качеством звонка</span><span class="sxs-lookup"><span data-stu-id="a56ed-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="a56ed-133">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="a56ed-133">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)