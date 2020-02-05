---
title: Требования к безопасности и конфигурации для корпоративной голосовой связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Сводка: сведения о требованиях к безопасности и конфигурации для корпоративной голосовой связи в Skype для бизнеса Server.'
ms.openlocfilehash: 314c25429dbf346a5f62705afa4f19a5b518452a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767242"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="2f081-103">Требования к безопасности и конфигурации для корпоративной голосовой связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2f081-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="2f081-104">**Сводка:** Узнайте о требованиях к безопасности и конфигурации для корпоративной голосовой связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2f081-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="2f081-105">Перед развертыванием корпоративной голосовой связью убедитесь в том, что ваша инфраструктура соответствует следующим требованиям: безопасность, Конфигурация пользователя и требования к оборудованию, зависящие от сценария.</span><span class="sxs-lookup"><span data-stu-id="2f081-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="2f081-106">Административные права и инфраструктура сертификатов</span><span class="sxs-lookup"><span data-stu-id="2f081-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="2f081-107">Перед развертыванием проверьте выполнение описанных ниже условий.</span><span class="sxs-lookup"><span data-stu-id="2f081-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="2f081-108">Администраторы, развертывающие корпоративную голосовую почту, должны быть членами группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="2f081-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="2f081-109">Администраторы, выполняющие задачи конфигурирования, должны обладать достаточными правами:</span><span class="sxs-lookup"><span data-stu-id="2f081-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="2f081-110">**CsVoiceAdministrator:** администратор с этой ролью может выполнять задачи настройки голосовой связи, управлять голосовыми приложениями и назначать голосовые политики конечным пользователям.</span><span class="sxs-lookup"><span data-stu-id="2f081-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="2f081-p101">**CsUserAdministrator:** администратор с этой ролью может управлять свойствами пользователей, например активацией корпоративной голосовой связи для пользователя. Этот администратор может также назначать политики на уровне пользователя за исключением политики архивирования, переносить пользователей и управлять телефонами общего пользования и аналоговыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="2f081-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="2f081-113">**CsAdministrator:** администратор с этой ролью может выполнять все задачи ролей CsUserAdministrator и CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2f081-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="2f081-114">Развертывание и настройка управляемой ключевой инфраструктуры (MKI) осуществляются с помощью инфраструктуры Майкрософт или стороннего центра сертификации (CA).</span><span class="sxs-lookup"><span data-stu-id="2f081-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2f081-115">Сведения о требованиях к сертификатам в Skype для бизнеса Server можно найти в статьях [требования к окружающей среде для Skype для бизнеса server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) или [серверных требований для Skype для бизнеса Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f081-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="2f081-116">Пользовательская конфигурация</span><span class="sxs-lookup"><span data-stu-id="2f081-116">User configuration</span></span>

<span data-ttu-id="2f081-117">Если вы состроили сервер с помощью каждого пула переднего плана или сервера Standard Edition во время клиентского развертывания, параметры пользователя, необходимые для корпоративной голосовой связи, были настроены автоматически во время установки файлов для этих ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="2f081-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="2f081-118">Если вы впервые разворачиваете корпоративную рабочую нагрузку, прежде чем приступать к развертыванию, назначьте основной номер телефона для каждого пользователя, который планируется включить для корпоративного голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2f081-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="2f081-119">As the administrator, you are responsible for ensuring that this number is unique.</span><span class="sxs-lookup"><span data-stu-id="2f081-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="2f081-120">Прежде чем приступить к реализации, все основные номера телефонов должны быть нормализованы (правильно отформатированы) и скопированы в свойство **универсального кода ресурса (URI** ) для каждой из них с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2f081-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f081-121">Примеры основных номеров телефона, необходимых для развертывания корпоративной голосовой связи, см. в разделе [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="2f081-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="2f081-122">Дальнейшие действия: установка файлов или настройка связи с ТСОП</span><span class="sxs-lookup"><span data-stu-id="2f081-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="2f081-123">После того как вы проверите программное обеспечение и требования к среде для корпоративной голосовой связи, вы можете:</span><span class="sxs-lookup"><span data-stu-id="2f081-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="2f081-124">Установите сервер-посредник, как описано в разделе [развертывание сервера-посредника в построителе топологии в Skype для бизнеса Server](deploy-a-mediation-server.md), но только в том случае, если вы хотите развернуть изолированный сервер или пул, так как серверы-исправления устанавливаются как часть внешнего пула или процесс развертывания сервера стандартных выпусков.</span><span class="sxs-lookup"><span data-stu-id="2f081-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="2f081-125">Кроме того, начните настраивать параметры для маршрутизации звонков для пользователей корпоративной голосовой связи, как описано в разделе [Настройка каналов в Skype для бизнеса Server](configure-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="2f081-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

