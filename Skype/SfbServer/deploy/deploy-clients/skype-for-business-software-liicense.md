---
title: Лицензия на программное обеспечение Skype Room System Skype для бизнеса
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Ознакомьтесь с этой темой, чтобы узнать, есть ли у вас лицензия на объем программного обеспечения Skype для бизнеса.
ms.openlocfilehash: 40b72e39fc0edc23b4cc0d17f82ba633c2ac24af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113095"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="16cf2-103">Система номеров Skype: лицензия на программное обеспечение Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="16cf2-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="16cf2-104">Ознакомьтесь с этой темой, чтобы узнать, есть ли у вас лицензия на объем программного обеспечения Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="16cf2-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="16cf2-105">Система номеров Skype использует установленный клиент Skype для бизнеса, для которого требуется лицензия на объем программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="16cf2-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="16cf2-106">Перед развертыванием первой системы номеров Skype узнайте состояние лицензии на объем развертывания с помощью серверов управления ключами (KMS) или нескольких ключей активации (MAK).</span><span class="sxs-lookup"><span data-stu-id="16cf2-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="16cf2-107">Серверы управления ключами (KMS)</span><span class="sxs-lookup"><span data-stu-id="16cf2-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="16cf2-108">Если kmS на месте и будет распространять активации лицензии Skype для бизнеса, система номеров Skype автоматически активирует клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="16cf2-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="16cf2-109">Чтобы узнать, на месте ли KMS:</span><span class="sxs-lookup"><span data-stu-id="16cf2-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="16cf2-110">Из командной подсказки запустите:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="16cf2-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="16cf2-111">Дополнительные сведения см. в примере Обнаружение хостов Office и Windows KMS с помощью DNS и удаление [несанкционированных экземпляров.](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)</span><span class="sxs-lookup"><span data-stu-id="16cf2-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="16cf2-112">Чтобы создать KMS, см. в рублях [активация KMS Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) и GVLKs для KMS и активации [Active Directory Office 2013](/DeployOffice/vlactivation/gvlks)</span><span class="sxs-lookup"><span data-stu-id="16cf2-112">To set up a KMS, see [KMS activation of Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) and [GVLKs for KMS and Active Directory activation of Office 2013](/DeployOffice/vlactivation/gvlks)</span></span>
  
<span data-ttu-id="16cf2-113">Универсальный ключ лицензии на объем Office 2013 для Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (этот ключ заставляет систему номеров Skype искать KMS в сети.)</span><span class="sxs-lookup"><span data-stu-id="16cf2-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="16cf2-114">Несколько ключей активации (MAK) из Центра обслуживания лицензий на объем (VLSC)</span><span class="sxs-lookup"><span data-stu-id="16cf2-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="16cf2-115">Если клиент использует любое другое программное обеспечение лицензии на объем, ИТ-отдел будет управлять активациями программного обеспечения и соглашением о лицензиях на объем (VLA) с помощью VLSC.</span><span class="sxs-lookup"><span data-stu-id="16cf2-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="16cf2-116">Это также позволит компании приобрести активации Skype для бизнеса VL, после чего компания может получить MAK для ввода в консоли администрирования системы Skype Room.</span><span class="sxs-lookup"><span data-stu-id="16cf2-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="16cf2-117">Клиент с VLA должен знать свои учетные данные VLSC, которые будут использоваться для администрирования соглашения и получения MAK.</span><span class="sxs-lookup"><span data-stu-id="16cf2-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="16cf2-118">В случае неопределенности финансовый отдел клиента должен иметь возможность подтвердить, оплатил ли клиент VLA.</span><span class="sxs-lookup"><span data-stu-id="16cf2-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="16cf2-119">Чтобы получить MAK, вы можете получить доступ к Центру службы лицензирования томов для просмотра соглашений и скачивания ключей продукта (MAK).</span><span class="sxs-lookup"><span data-stu-id="16cf2-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="16cf2-120">Дополнительные сведения перейдите в [Центр обслуживания лицензирования томов.](https://www.microsoft.com/Licensing/servicecenter/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="16cf2-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="16cf2-121">MAK для Microsoft 365 или Office 365 без доступа к VLSC</span><span class="sxs-lookup"><span data-stu-id="16cf2-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="16cf2-122">Если у клиента нет соглашения о лицензии на объем, активации Skype для бизнеса будут намного сложнее управлять.</span><span class="sxs-lookup"><span data-stu-id="16cf2-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="16cf2-123">Однако клиенты Microsoft 365 и Office 365 без доступа к VLSC могут получить рекламный MAK, предоставив OEM-службе по продаже системы номеров Skype следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="16cf2-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="16cf2-124">Имя компании</span><span class="sxs-lookup"><span data-stu-id="16cf2-124">Company name</span></span>
    
- <span data-ttu-id="16cf2-125">Имя контакта развертывания, электронная почта и номер телефона</span><span class="sxs-lookup"><span data-stu-id="16cf2-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="16cf2-126">Количество развернутых систем</span><span class="sxs-lookup"><span data-stu-id="16cf2-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="16cf2-127">Дата развертывания</span><span class="sxs-lookup"><span data-stu-id="16cf2-127">Deployment date</span></span>
    
- <span data-ttu-id="16cf2-128">Если у клиента есть менеджер технической учетной записи Майкрософт, имя и контактные данные tam</span><span class="sxs-lookup"><span data-stu-id="16cf2-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
