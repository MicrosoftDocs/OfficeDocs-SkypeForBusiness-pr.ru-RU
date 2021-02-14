---
title: Перенос серверов архива и мониторинга
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Если сервер архива и сервер мониторинга развернуты в устаревшей среде, эти серверы можно развернуть в среде Skype для бизнеса Server 2019 после переноса пулов переднего сервера. Однако если функции архивации и мониторинга критически важны для организации, перед миграцией следует добавить архивации и мониторинга в пилотный пул Skype для бизнеса Server 2019, чтобы эти функции были доступны во время миграции.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752671"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="60a31-104">Перенос серверов архива и мониторинга</span><span class="sxs-lookup"><span data-stu-id="60a31-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="60a31-105">Если сервер архива и сервер мониторинга развернуты в устаревшей среде, эти серверы можно развернуть в среде Skype для бизнеса Server 2019 после переноса пулов переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="60a31-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="60a31-106">Однако если функции архивации и мониторинга критически важны для организации, перед миграцией следует добавить архивации и мониторинга в пилотный пул Skype для бизнеса Server 2019, чтобы эти функции были доступны во время миграции.</span><span class="sxs-lookup"><span data-stu-id="60a31-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="60a31-107">Если функции архивации и мониторинга должны быть доступны во время миграции, помните о следующем.</span><span class="sxs-lookup"><span data-stu-id="60a31-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="60a31-108">Данные архивации и мониторинга не перемещаются в развертывание Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="60a31-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="60a31-109">Данные, которые вы back up перед списанием устаревшей среды будет ваш история действий в устаревшей среде.</span><span class="sxs-lookup"><span data-stu-id="60a31-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="60a31-110">Устаревшую версию сервера архива и сервера мониторинга можно связывать только с устаревшим пулом переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="60a31-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="60a31-111">В Skype для бизнеса Server 2019 архив и мониторинг больше не являются ролями сервера, а службами, интегрированными в пул переднего плана Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="60a31-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="60a31-112">Во время сосуществования устаревшей версии и развертывания Skype для бизнеса Server 2019 устаревшая версия сервера архивации и сервера мониторинга собирает данные для пользователей, которые размещены в устаревших пулах.</span><span class="sxs-lookup"><span data-stu-id="60a31-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="60a31-113">Архив и мониторинг в Skype для бизнеса Server 2019 собирают данные для пользователей, которые были в пулах Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="60a31-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="60a31-114">На этапе миграции при использовании устаревшего сервера edge с новым пилотным пулом Skype для бизнеса Server 2019 устаревшая версия сервера архивирования продолжает собирать данные для пользователей, которые находятся в устаревших пулах, а служба архивирования в Skype для бизнеса Server 2019 собирает данные для пользователей, которые находятся в пулах Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="60a31-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="60a31-115">Если в skype для бизнеса Server 2019 используется стороне решение для архива и мониторинга, обратитесь к поставщику по поводу того, когда и как интегрировать сторонное решение со Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="60a31-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

