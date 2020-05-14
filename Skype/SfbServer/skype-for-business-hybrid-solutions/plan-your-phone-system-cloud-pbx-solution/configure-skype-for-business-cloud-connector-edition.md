---
title: Настройка Skype для бизнеса Cloud Connector Edition и управление им
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Узнайте, как настроить Skype для бизнеса Cloud Connector Edition, минимальную локальную топологию для интеграции локальной инфраструктуры голосовой связи со службами голосовой связи телефонной системы (облачной УАТС) в Skype для бизнеса Online.
ms.openlocfilehash: a7c157836497383d89055f8ab986aa15f7e11870
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219519"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="829de-103">Настройка Skype для бизнеса Cloud Connector Edition и управление им</span><span class="sxs-lookup"><span data-stu-id="829de-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="829de-104">Узнайте, как настроить Skype для бизнеса Cloud Connector Edition, минимальную локальную топологию для интеграции локальной инфраструктуры голосовой связи со службами голосовой связи телефонной системы (облачной УАТС) в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="829de-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="829de-105">Прежде чем начать, ознакомьтесь с предварительными условиями, приведенными в разделе [Plan for Skype для бизнеса Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="829de-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="829de-106">Действия, описанные в этом разделе, применимы только к Cloud Connector Edition 1.4.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="829de-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="829de-107">Если вы еще не выполнили обновление до Cloud Connector Edition 2,1, ознакомьтесь со статьей " [обновление до новой версии Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md)".</span><span class="sxs-lookup"><span data-stu-id="829de-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="829de-108">Вы можете скачать установочный файл из [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="829de-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="829de-109">Действия по настройке Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="829de-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="829de-110">В следующей таблице перечислены действия, которые необходимо выполнить для установки и настройки Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="829de-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="829de-111">**Шаг**</span><span class="sxs-lookup"><span data-stu-id="829de-111">**Step**</span></span>|<span data-ttu-id="829de-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="829de-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="829de-113">Подготовка устройства Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="829de-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="829de-114">Скачайте файл установки, подготовьте сертификаты, настройте Hyper – V и приготовьте среду к развертыванию Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="829de-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="829de-115">Развертывание отдельного сайта в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="829de-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="829de-116">Создайте сайт в развертывании Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="829de-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="829de-117">Развертывание нескольких сайтов в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="829de-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="829de-118">Добавьте сайты в развертывание и изучите различия между развертываниями одного и нескольких сайтов.</span><span class="sxs-lookup"><span data-stu-id="829de-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="829de-119">Настройка интеграции Cloud Connector с вашей организацией Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="829de-119">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="829de-120">Добавить записи DNS, настроить гибридные шлюзы, настроить шлюзы PSTN и разрешить пользователям использовать голосовую почту телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="829de-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="829de-121">Проверка развертывания Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="829de-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="829de-122">Убедитесь, что развертывание работает правильно.</span><span class="sxs-lookup"><span data-stu-id="829de-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="829de-123">Обновление Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="829de-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="829de-124">Обновите существующее развертывание Cloud Connector до версии 2,1.</span><span class="sxs-lookup"><span data-stu-id="829de-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="829de-125">Изменение конфигурации существующего развертывания Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="829de-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="829de-126">Изменение параметров в Cloud Connector после развертывания.</span><span class="sxs-lookup"><span data-stu-id="829de-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="829de-127">Развертывание обхода сервера мультимедиа в Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="829de-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="829de-128">Узнайте, как развернуть обход сервера мультимедиа в Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="829de-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="829de-129">Справочник по командлетам Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="829de-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="829de-130">Сведения о командлетах PowerShell, используемых в Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="829de-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="829de-131">Устранение неполадок с развертыванием Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="829de-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="829de-132">Решения распространенных проблем, возникающих при развертывании Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="829de-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

