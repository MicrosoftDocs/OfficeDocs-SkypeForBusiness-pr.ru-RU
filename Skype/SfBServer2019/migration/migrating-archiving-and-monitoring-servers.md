---
title: Перенос серверов архивации и мониторинга
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
description: Если вы развернули сервер архивации и сервер мониторинга в устаревшей среде, вы можете развернуть эти серверы в среде Skype для бизнеса Server 2019, после того как вы перенесете интерфейсные пулы. Если функции архивации и мониторинга критически важны для вашей организации, следует добавить архивацию и мониторинг в пилотный пул Skype для бизнеса Server 2019 до миграции, чтобы обеспечить доступность функций в процессе миграции.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752671"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="937f6-104">Перенос серверов архивации и мониторинга</span><span class="sxs-lookup"><span data-stu-id="937f6-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="937f6-105">Если вы развернули сервер архивации и сервер мониторинга в устаревшей среде, вы можете развернуть эти серверы в среде Skype для бизнеса Server 2019, после того как вы перенесете интерфейсные пулы.</span><span class="sxs-lookup"><span data-stu-id="937f6-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="937f6-106">Если функции архивации и мониторинга критически важны для вашей организации, следует добавить архивацию и мониторинг в пилотный пул Skype для бизнеса Server 2019 до миграции, чтобы обеспечить доступность функций в процессе миграции.</span><span class="sxs-lookup"><span data-stu-id="937f6-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="937f6-107">Если функции архивации и мониторинга должны быть доступны во время миграции, помните о следующем.</span><span class="sxs-lookup"><span data-stu-id="937f6-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="937f6-108">Архивирование данных и данных мониторинга не переносятся в развертывание Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="937f6-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="937f6-109">Данные, которые вы создаете перед списанием устаревшей среды, будут журналом активности в устаревшей среде.</span><span class="sxs-lookup"><span data-stu-id="937f6-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="937f6-110">Устаревшая версия сервера архивирования и сервера мониторинга может быть связана только с устаревшим интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="937f6-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="937f6-111">В Skype для бизнеса Server 2019 Архивация и мониторинг больше не являются ролями серверов, но службы, интегрированные в интерфейсный пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="937f6-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="937f6-112">Во время совместного использования устаревших развертываний и развертываний Skype для бизнеса Server 2019 устаревшие версии сервера архивации и сервера мониторинга собирают данные для пользователей, размещенных в устаревших пулах.</span><span class="sxs-lookup"><span data-stu-id="937f6-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="937f6-113">Архивация и мониторинг в Skype для бизнеса Server 2019 сбор данных для пользователей, размещенных в пулах Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="937f6-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="937f6-114">На этапе миграции, когда вы по-прежнему используете старый пограничный сервер с новым пулом "пилотный сервер Skype для бизнеса 2019", устаревшая версия сервера архивации продолжает собирать данные для пользователей, размещенных в устаревших пулах и архивация в Skype для бизнеса Server 2019 собирает данные для пользователей, размещенных в пулах Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="937f6-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="937f6-115">Если вы используете решение для архивации и мониторинга стороннего производителя в сочетании с архивацией и мониторингом в Skype для бизнеса Server 2019, обратитесь к поставщику за сведениями о том, когда и как следует интегрировать стороннее решение со Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="937f6-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

