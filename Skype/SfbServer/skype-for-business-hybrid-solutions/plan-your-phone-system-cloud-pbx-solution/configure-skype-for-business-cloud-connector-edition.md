---
title: Настройка и управление выпуском облачных соединители Skype для бизнеса
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
description: Узнайте, как настроить Skype для бизнеса Cloud Connector Edition — минимальную топологию локального подключения, чтобы включить интеграцию локальной голосовой инфраструктуры с голосовой службой Phone System (Cloud PBX) в Skype для бизнеса Online.
ms.openlocfilehash: 4d24e5a312275158f276856aa78396ad63dff615
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094877"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="be887-103">Настройка и управление выпуском облачных соединители Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="be887-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="be887-104">Cloud Connector Edition завершит карьеру 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="be887-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="be887-105">После обновления организации до Teams узнайте, как подключить сеть локальной телефонии к Teams с помощью прямой [маршрутизации.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="be887-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="be887-106">Узнайте, как настроить Skype для бизнеса Cloud Connector Edition — минимальную топологию локального подключения, чтобы включить интеграцию локальной голосовой инфраструктуры с голосовой службой Phone System (Cloud PBX) в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="be887-106">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="be887-107">Перед началом работы необходимо просмотреть необходимые условия в [выпуске Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="be887-107">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="be887-108">Действия в этом разделе применяются только к cloud Connector Edition 1.4.1 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="be887-108">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="be887-109">Если вы еще не обновлены до cloud Connector Edition 2.1, см. в руб. Обновление до новой версии [облачного соединитетеля.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="be887-109">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="be887-110">Вы можете скачать файл установки из [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="be887-110">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="be887-111">Действия по настройке Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="be887-111">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="be887-112">В следующей таблице перечислены действия, необходимые для установки и настройки Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="be887-112">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="be887-113">**Этап**</span><span class="sxs-lookup"><span data-stu-id="be887-113">**Step**</span></span>|<span data-ttu-id="be887-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="be887-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="be887-115">Подготовка устройства Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be887-115">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="be887-116">Скачайте файл установки, подготовьте сертификаты, Hyper-V и подготовьте среду для развертывания облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="be887-116">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="be887-117">Развертывание отдельного сайта в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be887-117">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="be887-118">Создание сайта в развертывании облачного соединитела.</span><span class="sxs-lookup"><span data-stu-id="be887-118">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="be887-119">Развертывание нескольких сайтов в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be887-119">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="be887-120">Добавьте сайты в развертывание и узнайте о различиях между развертыванием одного и нескольких сайтов.</span><span class="sxs-lookup"><span data-stu-id="be887-120">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="be887-121">Настройка интеграции облачного соединители с организацией Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="be887-121">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="be887-122">Добавьте записи DNS, настройте гибридную систему, настройте шлюзы PSTN и устройте пользователям голосовую почту телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="be887-122">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="be887-123">Проверка развертывания Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be887-123">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="be887-124">Убедитесь, что развертывание работает правильно.</span><span class="sxs-lookup"><span data-stu-id="be887-124">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="be887-125">Обновление Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be887-125">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="be887-126">Обновление существующего развертывания облачного соединиттеля до версии 2.1.</span><span class="sxs-lookup"><span data-stu-id="be887-126">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="be887-127">Изменение конфигурации существующего развертывания Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be887-127">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="be887-128">Изменение параметров в облачном соединители после его развертывания.</span><span class="sxs-lookup"><span data-stu-id="be887-128">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="be887-129">Развертывание обхода мультимедиа в cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="be887-129">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="be887-130">Узнайте, как развернуть обход мультимедиа в cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="be887-130">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="be887-131">Справочник по командлетам Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be887-131">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="be887-132">Узнайте о cmdlets PowerShell, используемых в облачном соединителе.</span><span class="sxs-lookup"><span data-stu-id="be887-132">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="be887-133">Устранение неполадок с развертыванием Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="be887-133">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="be887-134">Решения распространенных проблем, с которыми сталкивается развертывание облачного соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="be887-134">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
