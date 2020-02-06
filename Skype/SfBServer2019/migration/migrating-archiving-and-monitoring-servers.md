---
title: Перенос серверов архивации и мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Если вы развернули сервер архивации и сервер мониторинга в устаревшей среде, вы можете развернуть эти серверы в среде Skype для бизнеса Server 2019 после миграции пулов интерфейсов. Тем не менее, если функции архивации и мониторинга важны для вашей организации, необходимо добавить архивирование и мониторинг для пула пилотных проектов Skype для бизнеса Server 2019 перед переходом, чтобы обеспечить доступность функций в процессе миграции.
ms.openlocfilehash: 5088f4b4f72ddc083cf2868df893946561eb2469
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813457"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="7af65-104">Перенос серверов архивации и мониторинга</span><span class="sxs-lookup"><span data-stu-id="7af65-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="7af65-105">Если вы развернули сервер архивации и сервер мониторинга в устаревшей среде, вы можете развернуть эти серверы в среде Skype для бизнеса Server 2019 после миграции пулов интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="7af65-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="7af65-106">Тем не менее, если функции архивации и мониторинга важны для вашей организации, необходимо добавить архивирование и мониторинг для пула пилотных проектов Skype для бизнеса Server 2019 перед переходом, чтобы обеспечить доступность функций в процессе миграции.</span><span class="sxs-lookup"><span data-stu-id="7af65-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="7af65-107">Если вы хотите использовать функции архивации и наблюдения в процессе миграции, имейте в виду следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="7af65-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="7af65-108">Архивация данных и данных мониторинга не переносятся на сервер развертывания Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7af65-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="7af65-109">Данные, которые вы заархивированы перед списанием устаревшей среды, будут храниться в устаревшей среде.</span><span class="sxs-lookup"><span data-stu-id="7af65-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="7af65-110">Устаревшая версия сервера архивирования и сервера мониторинга может быть связана только с устаревшим пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="7af65-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="7af65-111">В Skype для бизнеса Server 2019 Архивация и мониторинг больше не являются серверными ролями, но службы, интегрированные в пул переднего плана Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7af65-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="7af65-112">В течение времени существования устаревших развертываний и решений Skype для бизнеса Server 2019, устаревшая версия сервера архивирования и сервера мониторинга собирают данные для пользователей, которые хранятся в устаревших пулах.</span><span class="sxs-lookup"><span data-stu-id="7af65-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="7af65-113">Архивация и мониторинг в Skype для бизнеса Server 2019 сбор данных для пользователей, размещенных в группах "Skype для бизнеса Server 2019".</span><span class="sxs-lookup"><span data-stu-id="7af65-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7af65-114">На этапе миграции при использовании устаревшего пограничного сервера с новым корпоративным пулом для Skype для бизнеса Server 2019, устаревшая версия сервера архивации продолжает собирать данные для пользователей, использующих старые пулы и архивирования в Skype для бизнеса. Сервер 2019 собирает данные для пользователей, размещенных на серверах пула в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7af65-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="7af65-115">Если вы используете сторонние решения для архивации и мониторинга в сочетании с архивацией и мониторингом в Skype для бизнеса Server 2019, обратитесь к своему поставщику о том, когда и как следует интегрировать сторонние решения с помощью Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7af65-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

