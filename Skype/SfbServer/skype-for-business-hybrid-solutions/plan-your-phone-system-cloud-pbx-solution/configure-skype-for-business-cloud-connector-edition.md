---
title: Настройка и управление Skype для бизнеса Cloud Connector Edition
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
description: Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.
ms.openlocfilehash: e30fcb4cad44bffed495f1191e5e5cae73bb18cc
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358795"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="6acbb-103">Настройка и управление Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="6acbb-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="6acbb-104">Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="6acbb-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="6acbb-105">После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="6acbb-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="6acbb-106">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="6acbb-106">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="6acbb-107">Перед началом работы необходимо просмотреть необходимые условия в [выпуске Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="6acbb-107">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6acbb-108">Действия в этом разделе применимы только к Cloud Connector Edition 1.4.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="6acbb-108">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="6acbb-109">Если вы еще не обновили версию Cloud Connector Edition 2.1, см. обновление до новой версии [Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="6acbb-109">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="6acbb-110">Файл установки можно скачать из [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="6acbb-110">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="6acbb-111">Действия по настройке Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="6acbb-111">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="6acbb-112">В следующей таблице перечислены действия, необходимые для установки и настройки Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="6acbb-112">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="6acbb-113">**Этап**</span><span class="sxs-lookup"><span data-stu-id="6acbb-113">**Step**</span></span>|<span data-ttu-id="6acbb-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6acbb-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6acbb-115">Подготовка устройства Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="6acbb-115">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="6acbb-116">Скачайте файл установки, подготовьте сертификаты, настройте Hyper-V и подготовьте среду к развертыванию Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6acbb-116">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="6acbb-117">Развертывание отдельного сайта в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="6acbb-117">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="6acbb-118">Создайте сайт в развертывании Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6acbb-118">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="6acbb-119">Развертывание нескольких сайтов в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="6acbb-119">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="6acbb-120">Добавьте сайты в развертывание и узнайте о различиях между развертываниями с одним и несколькими сайтами.</span><span class="sxs-lookup"><span data-stu-id="6acbb-120">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="6acbb-121">Настройка интеграции Cloud Connector с организацией Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="6acbb-121">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="6acbb-122">Добавление записей DNS, настройка гибридной конфигурации, настройка шлюзов STN и включить для пользователей голосовую почту телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="6acbb-122">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="6acbb-123">Проверка развертывания Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="6acbb-123">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="6acbb-124">Убедитесь, что развертывание работает правильно.</span><span class="sxs-lookup"><span data-stu-id="6acbb-124">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="6acbb-125">Обновление Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="6acbb-125">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="6acbb-126">Обновите существующее развертывание Cloud Connector до версии 2.1.</span><span class="sxs-lookup"><span data-stu-id="6acbb-126">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="6acbb-127">Изменение конфигурации существующего развертывания Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="6acbb-127">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="6acbb-128">Измените параметры в Cloud Connector после его развертывания.</span><span class="sxs-lookup"><span data-stu-id="6acbb-128">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="6acbb-129">Развертывание обхода мультимедиа в Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="6acbb-129">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="6acbb-130">Узнайте, как развернуть обход мультимедиа в Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6acbb-130">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="6acbb-131">Справочник по командлетам Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="6acbb-131">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="6acbb-132">Узнайте о cmdlets PowerShell, используемых в Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6acbb-132">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="6acbb-133">Устранение неполадок с развертыванием Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="6acbb-133">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="6acbb-134">Решения распространенных проблем, которые могут возникнуть при развертывании Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6acbb-134">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

