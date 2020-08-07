---
title: Настройка средства аналитики звонков для Microsoft Teams
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
description: Настройка средства аналитики звонков для пользователей для выявления и устранения проблем с качеством связи в Microsoft Teams.
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581110"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="8f1da-103">Настройка средства аналитики звонков для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8f1da-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="8f1da-104">Как администратор Microsoft Teams, вы можете использовать аналитику звонков для каждого пользователя, чтобы устранять проблемы качества связи и подключения для **отдельных пользователей**.</span><span class="sxs-lookup"><span data-stu-id="8f1da-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="8f1da-105">Чтобы воспользоваться всеми преимуществами средства аналитики звонков, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="8f1da-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="8f1da-106">Назначьте пользователям специальные роли поддержки, например агенты службы поддержки, чтобы позволить им просматривать средства аналитики звонков для пользователей.</span><span class="sxs-lookup"><span data-stu-id="8f1da-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="8f1da-107">Эти роли поддержки не могут получить доступ к оставшейся части центра администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="8f1da-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="8f1da-108">Добавляйте данные о зданиях, сайтах и клиентах на аналитический запрос по каждому пользователю, загружая файл данных в формате TSV или CSV.</span><span class="sxs-lookup"><span data-stu-id="8f1da-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="8f1da-109">Когда вы будете готовы приступить к работе с аналитическими вызовами по каждому пользователю, читайте в статье [Использование аналитических вызовов для пользователей для устранения](use-call-analytics-to-troubleshoot-poor-call-quality.md)некачественных звонков.</span><span class="sxs-lookup"><span data-stu-id="8f1da-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="8f1da-110">Предоставление доступа к сотрудникам службы поддержки и поддержки</span><span class="sxs-lookup"><span data-stu-id="8f1da-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="8f1da-111">Администратор Teams имеет право полного доступа к сведениям об аналитических звонках для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="8f1da-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="8f1da-112">Мы создали некоторые специализированные роли Azure Active Directory, которые можно назначить специалистам службы поддержки персонала и поддержки, чтобы они также могли получать доступ к аналитическим вызовам по каждому пользователю (без доступа к остальной части центра администрирования Teams).</span><span class="sxs-lookup"><span data-stu-id="8f1da-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="8f1da-113">Назначьте роль **специалиста по поддержке взаимодействия Teams** пользователям, которые должны иметь ограниченный вид аналитических вызовов для каждого пользователя (поддержка уровня 1).</span><span class="sxs-lookup"><span data-stu-id="8f1da-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="8f1da-114">Назначьте роль **инженера поддержки взаимодействия Teams** пользователям, которым необходим полный доступ к аналитическим вызовам пользователей (поддержка уровня 2).</span><span class="sxs-lookup"><span data-stu-id="8f1da-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="8f1da-115">Ни одна роль не имеет доступа к оставшейся части центра администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="8f1da-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="8f1da-116">Чтобы узнать, что делает каждая из этих ролей, ознакомьтесь со статьей [о том, какие функции поддерживаются в каждой из групп](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do).</span><span class="sxs-lookup"><span data-stu-id="8f1da-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="8f1da-117">Дополнительные сведения о ролях администраторов Teams можно найти [в разделе Использование ролей администратора Teams для управления группами](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8f1da-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="8f1da-118">Сведения о назначении ролей администратора в Azure Active Directory можно найти [в статье Просмотр и назначение ролей в Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="8f1da-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="8f1da-119">Сведения о назначении административных ролей в Azure Active Directory можно найти в статье [Просмотр и назначение ролей в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="8f1da-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="8f1da-120">Добавление файлов в формате TSV или CSV для добавления сведений о сборке, сайте и клиенте</span><span class="sxs-lookup"><span data-stu-id="8f1da-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="8f1da-121">Вы можете добавлять данные о зданиях, сайтах и клиентах на аналитический запрос по каждому пользователю, загружая CSV-или. tsv.</span><span class="sxs-lookup"><span data-stu-id="8f1da-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="8f1da-122">С помощью этой информации средство аналитики звонков может сопоставлять IP-адреса с физическими адресами.</span><span class="sxs-lookup"><span data-stu-id="8f1da-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="8f1da-123">Агенты администратора и службы поддержки могут использовать эту информацию для выявления проблем с вызовами.</span><span class="sxs-lookup"><span data-stu-id="8f1da-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="8f1da-124">Например, почему пользователи в той же сборке имеют аналогичные проблемы с качеством связи?</span><span class="sxs-lookup"><span data-stu-id="8f1da-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="8f1da-125">Если вы являетесь администратором Teams или Skype для бизнеса, вы можете использовать существующий клиент и создать файл данных на панели мониторинга качества звонков для Teams или Skype для бизнеса (CQD).</span><span class="sxs-lookup"><span data-stu-id="8f1da-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="8f1da-126">Сначала вы загрузили файл из CQD, а затем выгрузите его для анализа звонков.</span><span class="sxs-lookup"><span data-stu-id="8f1da-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="8f1da-127">Чтобы загрузить существующий файл данных, перейдите на **Microsoft Teams admin center**  >  **панель мониторинга качества звонков**в центре администрирования Microsoft Teams  >  **Upload now**.</span><span class="sxs-lookup"><span data-stu-id="8f1da-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="8f1da-128">В списке **Мои отправки** выберите пункт **загрузить** рядом с нужным файлом.</span><span class="sxs-lookup"><span data-stu-id="8f1da-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="8f1da-129">Чтобы добавить новый файл, перейдите в раздел **Расположение центра администрирования Microsoft Teams**  >  **Locations**, а затем выберите команду **отправить данные о местоположении** или **заменить данные о местоположении**.</span><span class="sxs-lookup"><span data-stu-id="8f1da-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="8f1da-130">Если вы создаете файл в формате TSV или CSV с нуля, ознакомьтесь со статьей [Отправка клиента и создание данных](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="8f1da-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8f1da-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8f1da-131">Related topics</span></span>

[<span data-ttu-id="8f1da-132">Использование аналитики звонков для пользователей для устранения слабого качества связи</span><span class="sxs-lookup"><span data-stu-id="8f1da-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="8f1da-133">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="8f1da-133">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
