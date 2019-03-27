---
title: Предварительные требования безопасности и конфигурации для корпоративной голосовой связи в Скайп для Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Сводка: Сведения о безопасности и конфигурации необходимое программное обеспечение для корпоративной голосовой связи в Скайп для Business Server.'
ms.openlocfilehash: 522252119dd6e3699dc93e0191d50a3c09c023dc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896576"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="968af-103">Предварительные требования безопасности и конфигурации для корпоративной голосовой связи в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="968af-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="968af-104">**Сводка:** Сведения о безопасности и конфигурации необходимое программное обеспечение для корпоративной голосовой связи в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="968af-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="968af-105">Перед развертыванием корпоративной голосовой связи, убедитесь, что инфраструктура удовлетворяет следующие безопасности, конфигурации пользователя и необходимые компоненты оборудования для конкретного сценария.</span><span class="sxs-lookup"><span data-stu-id="968af-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="968af-106">Административные права и инфраструктура сертификатов</span><span class="sxs-lookup"><span data-stu-id="968af-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="968af-107">Перед развертыванием проверьте выполнение описанных ниже условий.</span><span class="sxs-lookup"><span data-stu-id="968af-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="968af-108">Администраторы развертывания корпоративной голосовой связи должны быть членами группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="968af-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="968af-109">Администраторы, выполняющие задачи конфигурирования, должны обладать достаточными правами:</span><span class="sxs-lookup"><span data-stu-id="968af-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="968af-110">**CsVoiceAdministrator:** администратор с этой ролью может выполнять задачи настройки голосовой связи, управлять голосовыми приложениями и назначать голосовые политики конечным пользователям.</span><span class="sxs-lookup"><span data-stu-id="968af-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="968af-p101">**CsUserAdministrator:** администратор с этой ролью может управлять свойствами пользователей, например активацией корпоративной голосовой связи для пользователя. Этот администратор может также назначать политики на уровне пользователя за исключением политики архивирования, переносить пользователей и управлять телефонами общего пользования и аналоговыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="968af-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="968af-113">**CsAdministrator:** администратор с этой ролью может выполнять все задачи ролей CsUserAdministrator и CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="968af-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="968af-114">Развертывание и настройка управляемой ключевой инфраструктуры (MKI) осуществляются с помощью инфраструктуры Майкрософт или стороннего центра сертификации (CA).</span><span class="sxs-lookup"><span data-stu-id="968af-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="968af-115">Для получения дополнительных сведений о требованиях к сертификатам в Скайп для Business Server см [окружающей среды требования к Скайп для Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) или [требования к серверу для Скайп для Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="968af-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="968af-116">Пользовательская конфигурация</span><span class="sxs-lookup"><span data-stu-id="968af-116">User configuration</span></span>

<span data-ttu-id="968af-117">Если сервер-посредник с каждого пула переднего плана или сервера Standard Edition, совмещенного во время развертывания переднего плана, пользовательские параметры, необходимые для корпоративной голосовой связи с проверкой автоматически во время установки файлов для этих ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="968af-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="968af-118">Если в настоящее время, прежде чем начать процесс развертывания вновь развертывание рабочей нагрузки корпоративной голосовой связи, определить основной номер телефона для каждого пользователя, который вы планируете включить для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="968af-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="968af-119">As the administrator, you are responsible for ensuring that this number is unique.</span><span class="sxs-lookup"><span data-stu-id="968af-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="968af-120">Перед реализацией всех основных телефонного номера, должны быть упорядочены (правильный формат) и скопирован в свойства **URI линии** каждого пользователя, с помощью Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="968af-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="968af-121">Примеры основных номеров телефона, необходимых для развертывания корпоративной голосовой связи, см. в разделе [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="968af-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="968af-122">Дальнейшие действия: установка файлов или настройка связи с ТСОП</span><span class="sxs-lookup"><span data-stu-id="968af-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="968af-123">После проверки окружающей среды необходимые условия для корпоративной голосовой связи, можно выполнить и программное обеспечение:</span><span class="sxs-lookup"><span data-stu-id="968af-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="968af-124">Установка сервера-посредника, как описано в статье [Deploy сервера-посредника в построителе топологий в Скайп для Business Server](deploy-a-mediation-server.md), но только в том случае, если вы хотите развернуть изолированный сервер-посредник или пул, так как серверы-посредники устанавливаются в составе переднего плана пул или процесс развертывания сервера Standard Edition, при котором с совместным размещением.</span><span class="sxs-lookup"><span data-stu-id="968af-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="968af-125">Или приступите к настройке параметров для маршрутизации вызовов для пользователей корпоративной голосовой связи, как описано в [Настройка магистрали в Скайп для Business Server](configure-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="968af-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

