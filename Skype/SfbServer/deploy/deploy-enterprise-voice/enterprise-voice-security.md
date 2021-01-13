---
title: Необходимые условия для обеспечения безопасности и Корпоративная голосовая связь в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: Сводка. Сведения о предварительных условиях для обеспечения безопасности и Корпоративная голосовая связь в Skype для бизнеса Server.
ms.openlocfilehash: 77efbf231f83c6d3c31254c9ab742de7e2b226e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830849"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="7fe04-103">Необходимые условия для обеспечения безопасности и Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7fe04-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="7fe04-104">**Сводка:** Узнайте о предварительных условиях безопасности и конфигурации для Корпоративная голосовая связь Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7fe04-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="7fe04-105">Перед развертыванием Корпоративная голосовая связь убедитесь, что ваша инфраструктура соответствует следующим требованиям безопасности, конфигурации пользователя и оборудования для конкретного сценария.</span><span class="sxs-lookup"><span data-stu-id="7fe04-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="7fe04-106">Административные права и инфраструктура сертификатов</span><span class="sxs-lookup"><span data-stu-id="7fe04-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="7fe04-107">Перед развертыванием проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="7fe04-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="7fe04-108">Администраторы развертывания корпоративной голосовой связи должны быть членами группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7fe04-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="7fe04-109">Администраторы, выполняющие задачи конфигурирования, должны обладать достаточными правами:</span><span class="sxs-lookup"><span data-stu-id="7fe04-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="7fe04-110">**CsVoiceAdministrator:** администратор с этой ролью может выполнять задачи настройки голосовой связи, управлять голосовыми приложениями и назначать голосовые политики конечным пользователям.</span><span class="sxs-lookup"><span data-stu-id="7fe04-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="7fe04-p101">**CsUserAdministrator:** администратор с этой ролью может управлять свойствами пользователей, например активацией корпоративной голосовой связи для пользователя. Этот администратор может также назначать политики на уровне пользователя за исключением политики архивирования, переносить пользователей и управлять телефонами общего пользования и аналоговыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="7fe04-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="7fe04-113">**CsAdministrator:** администратор с этой ролью может выполнять все задачи ролей CsUserAdministrator и CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7fe04-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="7fe04-114">Развертывание и настройка управляемой ключевой инфраструктуры (MKI) осуществляются с помощью инфраструктуры Майкрософт или стороннего центра сертификации (CA).</span><span class="sxs-lookup"><span data-stu-id="7fe04-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7fe04-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="7fe04-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="7fe04-116">Конфигурация пользователя</span><span class="sxs-lookup"><span data-stu-id="7fe04-116">User configuration</span></span>

<span data-ttu-id="7fe04-117">При размещении сервера-посредника с каждым интерфейсным пулом или сервером Standard Edition во время развертывания переднего плана параметры пользователей, необходимые для Корпоративная голосовая связь, были настроены автоматически во время установки файлов для этих ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="7fe04-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="7fe04-118">Если на этот раз вы заново развертываете рабочую нагрузку корпоративной голосовой связи, перед началом процесса развертывания назначьте основной номер телефона каждому пользователю, для которого вы планируете активировать функцию корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7fe04-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="7fe04-119">Как администратор вы несете ответственность за то, чтобы данный номер был уникальным.</span><span class="sxs-lookup"><span data-stu-id="7fe04-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="7fe04-120">Перед реализацией все основные номера телефонов должны быть нормализованы (правильно отформатированы) и скопированы в свойство **Line URI** каждого пользователя с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7fe04-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7fe04-121">Примеры основных номеров телефонов, необходимых для Корпоративная голосовая связь развертывания, см. в [примере правил нормализации.](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)</span><span class="sxs-lookup"><span data-stu-id="7fe04-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="7fe04-122">Дальнейшие действия: установка файлов или настройка подключения к STN</span><span class="sxs-lookup"><span data-stu-id="7fe04-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="7fe04-123">После проверки необходимого программного обеспечения и среды для Корпоративная голосовая связь вы можете:</span><span class="sxs-lookup"><span data-stu-id="7fe04-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="7fe04-124">Установите сервер-посредник, как описано в описании развертывания сервера-посредника в построитель топологий в Skype для бизнеса [Server,](deploy-a-mediation-server.md)но только в том случае, если вы хотите развернуть автономный сервер-посредник или пул, так как серверы-посредники устанавливаются как часть процесса развертывания сервера переднего сервера или сервера Standard Edition при их размещении.</span><span class="sxs-lookup"><span data-stu-id="7fe04-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="7fe04-125">Или начните настройку параметров маршрутизируемых вызовов для Корпоративная голосовая связь пользователей, как описано в описании настройки магистральных магистральных путей [в Skype для бизнеса Server.](configure-trunks.md)</span><span class="sxs-lookup"><span data-stu-id="7fe04-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

