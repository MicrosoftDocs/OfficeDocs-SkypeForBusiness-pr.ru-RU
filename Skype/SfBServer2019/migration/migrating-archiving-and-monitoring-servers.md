---
title: Перенос серверов архивирования и мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Если развертывание сервера архивации и мониторинга сервера в старой среды, вы можете развернуть эти серверы в вашей Скайп среды Business Server 2019 после миграции пулов переднего плана. Если архивации и мониторинга функциональные возможности важны для вашей организации, тем не менее, следует добавить архивации и мониторинга для вашей Скайп для пилотного пула Business Server 2019 перед миграцией, чтобы функциональность доступна во время миграции.
ms.openlocfilehash: 24dc3e3007fd9a58c23f9c15a31cccc766d45e83
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896094"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="04e72-104">Перенос серверов архивирования и мониторинга</span><span class="sxs-lookup"><span data-stu-id="04e72-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="04e72-105">Если развертывание сервера архивации и мониторинга сервера в старой среды, вы можете развернуть эти серверы в вашей Скайп среды Business Server 2019 после миграции пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="04e72-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="04e72-106">Если архивации и мониторинга функциональные возможности важны для вашей организации, тем не менее, следует добавить архивации и мониторинга для вашей Скайп для пилотного пула Business Server 2019 перед миграцией, чтобы функциональность доступна во время миграции.</span><span class="sxs-lookup"><span data-stu-id="04e72-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="04e72-107">Если требуется использовать возможности архивации и мониторинга во время миграции, помните о следующем.</span><span class="sxs-lookup"><span data-stu-id="04e72-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="04e72-108">Архивация данных и отслеживание данных не перемещаются Скайп для развертывания Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="04e72-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="04e72-109">Данные, которые резервного копирования до ликвидации старой среды будет то журнал активности в старой среды.</span><span class="sxs-lookup"><span data-stu-id="04e72-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="04e72-110">Устаревшая версия сервера архивации и мониторинга сервера можно сопоставить только с устаревшим пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="04e72-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="04e72-111">В Скайп для Business Server 2019 архивации и мониторинга больше не ролей сервера, но служб, встроенные в Скайп для пула переднего плана Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="04e72-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="04e72-112">Во время, созданного в прежней версии и Скайп для развертываний Business Server 2019 сосуществования, устаревшая версия сервера архивации и мониторинга сервера сбора данных для пользователей, размещенных на старых пулов.</span><span class="sxs-lookup"><span data-stu-id="04e72-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="04e72-113">Архивирование и мониторинг в Скайп для Business Server 2019 собрать данные для пользователей, размещенных на Скайп для пулов Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="04e72-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="04e72-114">Во время миграции, когда будет по-прежнему, выбрав устаревшего пограничного сервера с новой Скайп для Business Server 2019 пилотного пула, устаревшая версия сервера архивации по-прежнему производится для сбора данных для пользователей, размещенных на старых пулов и архивация в Скайп для бизнеса Сервер 2019 собирает информацию о данных для пользователей, размещенных на Скайп для пулов Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="04e72-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="04e72-115">Если вы используете сторонний архивации и мониторинга решения в сочетании с архивации и мониторинга в Скайп для Business Server 2019, обратитесь к поставщику о когда и как необходимо интегрировать решений сторонних производителей с Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="04e72-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

