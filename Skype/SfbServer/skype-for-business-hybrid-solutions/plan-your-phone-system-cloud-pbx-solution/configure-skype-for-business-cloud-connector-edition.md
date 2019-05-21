---
title: Настройка и управление Skype для бизнеса Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Здесь вы узнаете, как настроить Skype для бизнеса Cloud Connector Edition, минимальную локальную топологию для поддержки интеграции локальной голосовой инфраструктуры с телефонной системой в Office 365 (облачная УАТС) в Skype для бизнеса Online.
ms.openlocfilehash: 49c0ce1a67b579a566e2dd22b9b345c1d6a4afdd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287400"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="1b269-103">Настройка и управление Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="1b269-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="1b269-104">Здесь вы узнаете, как настроить Skype для бизнеса Cloud Connector Edition, минимальную локальную топологию для поддержки интеграции локальной голосовой инфраструктуры с телефонной системой в Office 365 (облачная УАТС) в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="1b269-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="1b269-105">Прежде чем начать, ознакомьтесь с требованиями, описанными в разделе [планирование для облачной версии Skype для бизнеса Cloud Connector](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="1b269-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1b269-106">Шаги, описываемые в этом разделе, относятся только к выпускам Cloud Connector Edition 1.4.1 и более поздним.</span><span class="sxs-lookup"><span data-stu-id="1b269-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="1b269-107">Если вы еще не обновили версию Cloud Connector Edition 2,1, ознакомьтесь со сведениями [о переходе к новой версии облачного соединителя](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1b269-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="1b269-108">Вы можете скачать установочный файл с [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)сайта.</span><span class="sxs-lookup"><span data-stu-id="1b269-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="1b269-109">Шаги по настройке Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="1b269-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="1b269-110">В следующей таблице приводятся шаги по установке и настройке выпуска Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="1b269-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="1b269-111">**Шаг**</span><span class="sxs-lookup"><span data-stu-id="1b269-111">**Step**</span></span>|<span data-ttu-id="1b269-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1b269-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="1b269-113">Подготовка устройства Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b269-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="1b269-114">Скачайте установочный файл, подготовьте сертификаты, настройте Hyper-V и Загрузите среду для развертывания облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="1b269-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="1b269-115">Deploy a single site in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b269-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="1b269-116">Создайте сайт в развертывании Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1b269-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="1b269-117">Развертывание нескольких сайтов в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b269-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="1b269-118">Добавьте сайты в развертывание и изучите различия между развертываниями с одним и с несколькими сайтами.</span><span class="sxs-lookup"><span data-stu-id="1b269-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="1b269-119">Configure Cloud Connector integration with your Office 365 tenant</span><span class="sxs-lookup"><span data-stu-id="1b269-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="1b269-120">Добавьте записи DNS, настройте гибридную среду, настройте шлюзы ТСОП и включите для пользователей поддержку голосовой почты телефонной системы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="1b269-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="1b269-121">Validate your Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="1b269-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="1b269-122">Проверьте работоспособность развертывания.</span><span class="sxs-lookup"><span data-stu-id="1b269-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="1b269-123">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b269-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="1b269-124">Обновите существующее развертывание Cloud Connector до версии 2.1.</span><span class="sxs-lookup"><span data-stu-id="1b269-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="1b269-125">Modify the configuration of an existing Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="1b269-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="1b269-126">Изменение параметров в облачном соединителе после развертывания.</span><span class="sxs-lookup"><span data-stu-id="1b269-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="1b269-127">Развертывание обхода сервера-посредника в Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="1b269-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="1b269-128">Ознакомьтесь с развертыванием обхода сервера-посредника в Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1b269-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="1b269-129">Cloud Connector cmdlet reference</span><span class="sxs-lookup"><span data-stu-id="1b269-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="1b269-130">Ознакомьтесь с командлетами PowerShell, используемыми в Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1b269-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="1b269-131">Устранение неполадок с развертыванием Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1b269-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="1b269-132">Решения распространенных проблем, возникающих при развертывании облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="1b269-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

