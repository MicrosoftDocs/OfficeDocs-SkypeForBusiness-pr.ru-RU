---
title: Настройка и управление Skype для бизнеса Cloud Connector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: Сведения о настройке Скайп для облачных соединитель Business Edition, топологии минимальной локальных Чтобы включить интеграцию инфраструктуры голосовой связи в локальной с телефонной системой в службах Office 365 (облако УАТС) голосовой связи в Скайп для бизнеса в Интернет.
ms.openlocfilehash: 6cbf01b5b155fd3e234ef2a1827eb52580d22d2f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="831c6-103">Настройка и управление Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="831c6-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="831c6-104">Сведения о настройке Скайп для облачных соединитель Business Edition, топологии минимальной локальных Чтобы включить интеграцию инфраструктуры голосовой связи в локальной с телефонной системой в службах Office 365 (облако УАТС) голосовой связи в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="831c6-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="831c6-105">Прежде чем начать, необходимо проверить необходимого программного обеспечения в [Plan for Скайп облаке соединитель для выпуска для бизнеса](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="831c6-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="831c6-106">Шаги, описываемые в этом разделе, относятся только к выпускам Cloud Connector Edition 1.4.1 и более поздним.</span><span class="sxs-lookup"><span data-stu-id="831c6-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="831c6-107">Если вы еще не был обновлен для облачных соединителя версии 2.1, видеть [обновление до новой версии облачных соединителя](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="831c6-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="831c6-108">Можно загрузить файл установки из [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="831c6-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="831c6-109">Шаги по настройке Skype для бизнеса Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="831c6-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="831c6-110">В следующей таблице приводятся шаги по установке и настройке выпуска Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="831c6-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="831c6-111">**Действие**</span><span class="sxs-lookup"><span data-stu-id="831c6-111">**Step**</span></span>|<span data-ttu-id="831c6-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="831c6-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="831c6-113">Подготовка устройства облачных соединителя</span><span class="sxs-lookup"><span data-stu-id="831c6-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="831c6-114">Загрузить файл установки, Подготовка сертификаты, настроить Hyper-V и подготовки среды для развертывания облака соединителя.</span><span class="sxs-lookup"><span data-stu-id="831c6-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="831c6-115">Развертывание одного сайта в облаке соединителя</span><span class="sxs-lookup"><span data-stu-id="831c6-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="831c6-116">Создайте сайт в развертывании Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="831c6-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="831c6-117">Развертывание нескольких сайтах в облаке соединителя</span><span class="sxs-lookup"><span data-stu-id="831c6-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="831c6-118">Добавьте сайты в развертывание и изучите различия между развертываниями с одним и с несколькими сайтами.</span><span class="sxs-lookup"><span data-stu-id="831c6-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="831c6-119">Настройка интеграции облачных соединителя с помощью клиента Office 365</span><span class="sxs-lookup"><span data-stu-id="831c6-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="831c6-120">Добавьте записи DNS, настройте гибридную среду, настройте шлюзы ТСОП и включите для пользователей поддержку голосовой почты телефонной системы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="831c6-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="831c6-121">Проверка развертывания облака соединителя</span><span class="sxs-lookup"><span data-stu-id="831c6-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="831c6-122">Проверьте работоспособность развертывания.</span><span class="sxs-lookup"><span data-stu-id="831c6-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="831c6-123">Обновление до новой версии облачных соединителя</span><span class="sxs-lookup"><span data-stu-id="831c6-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="831c6-124">Обновите существующее развертывание Cloud Connector до версии 2.1.</span><span class="sxs-lookup"><span data-stu-id="831c6-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="831c6-125">Изменить конфигурацию существующего развертывания облака соединителя</span><span class="sxs-lookup"><span data-stu-id="831c6-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="831c6-126">Изменение параметров в облаке соединителя после уже развернута.</span><span class="sxs-lookup"><span data-stu-id="831c6-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="831c6-127">Развертывание сервера-посредника в облаке соединителя Edition</span><span class="sxs-lookup"><span data-stu-id="831c6-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="831c6-128">Ознакомьтесь с развертыванием обхода сервера-посредника в Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="831c6-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="831c6-129">Справочник командлетов соединителя в облаке</span><span class="sxs-lookup"><span data-stu-id="831c6-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="831c6-130">Ознакомьтесь с командлетами PowerShell, используемыми в Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="831c6-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="831c6-131">Устранение неполадок развертывания облака соединителя</span><span class="sxs-lookup"><span data-stu-id="831c6-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="831c6-132">Решения для распространенных проблем, возникающих в случае развертывания облака соединителя.</span><span class="sxs-lookup"><span data-stu-id="831c6-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

