---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Схема основной высокой доступности для большинства ролей сервера в Скайп для Business Server основан на избыточности сервера с помощью пула. В случае сбоя сервера, на котором выполняется определенная роль сервера, другие серверы в пуле с той же ролью берут его нагрузку на себя.
ms.openlocfilehash: 8868b86d87adaa1e9da191ae9088775f786a8d0d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894102"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="ad372-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="ad372-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="ad372-105">Схема основной высокой доступности для большинства ролей сервера в Скайп для Business Server основан на избыточности сервера с помощью пула.</span><span class="sxs-lookup"><span data-stu-id="ad372-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="ad372-106">В случае сбоя сервера, на котором выполняется определенная роль сервера, другие серверы в пуле с той же ролью берут его нагрузку на себя.</span><span class="sxs-lookup"><span data-stu-id="ad372-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="ad372-107">Скайп для Business Server требуется по крайней мере два сервера переднего плана для поддержки высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="ad372-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="ad372-108">Средство планирования используются следующие критерии для определения, если будет добавлена дополнительных серверов для поддержки высокой доступности:</span><span class="sxs-lookup"><span data-stu-id="ad372-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="ad372-109">Если развертывание содержит два или более серверов переднего плана, средство планирования не добавляйте дополнительных серверов.</span><span class="sxs-lookup"><span data-stu-id="ad372-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="ad372-110">Если развертывание содержит пограничного сервера, добавляется дополнительный сервер.</span><span class="sxs-lookup"><span data-stu-id="ad372-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="ad372-111">Если развертывание содержит Persistent Chat, средство планирования будет добавить дополнительный сервер, но не увеличить число пула.</span><span class="sxs-lookup"><span data-stu-id="ad372-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="ad372-112">К примеру Если развертывание уже содержит четырех серверов, средство планирования предложит добавления второго сервера (для всего из пяти серверов), но будет поддерживать один пул.</span><span class="sxs-lookup"><span data-stu-id="ad372-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="ad372-113">Сохраняемый чат доступна в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ad372-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ad372-114">Те же функциональные возможности доступны в группах.</span><span class="sxs-lookup"><span data-stu-id="ad372-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="ad372-115">Дополнительные сведения содержатся в разделе [обновление Скайп для бизнеса для групп Майкрософт](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="ad372-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="ad372-116">Если необходимо использовать сохраняемого чата, возможны перенос пользователей, которым требуется эта функция группам или продолжить использование Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ad372-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="ad372-117">Средство планирования также добавляет зеркальной базы данных SQL для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="ad372-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="ad372-118">Например если базы данных SQL сервера переднего плана, средство планирования будет добавьте другие базы данных как зеркальной базы данных на этом и назовите его как «переднего плана зеркальной базы данных SQL.</span><span class="sxs-lookup"><span data-stu-id="ad372-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="ad372-119">Дополнительные сведения о подготовке среды для обеспечения высокой доступности в разделе [Планирование высокой доступности и аварийного восстановления в Скайп для Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ad372-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

