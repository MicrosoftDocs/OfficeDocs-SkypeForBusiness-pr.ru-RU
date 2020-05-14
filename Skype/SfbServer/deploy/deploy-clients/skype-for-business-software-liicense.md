---
title: Лицензия на программное обеспечение Skype для бизнеса для системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: В этом разделе рассказывается, как проверить, есть ли у вас Корпоративная лицензия на программное обеспечение Skype для бизнеса.
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220929"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="3de1d-103">Система комнат Skype: лицензия на программное обеспечение Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3de1d-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="3de1d-104">В этом разделе рассказывается, как проверить, есть ли у вас Корпоративная лицензия на программное обеспечение Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3de1d-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="3de1d-105">Система комнат Skype использует установленный клиент Skype для бизнеса, для которого требуется программное обеспечение корпоративного лицензирования.</span><span class="sxs-lookup"><span data-stu-id="3de1d-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="3de1d-106">Перед развертыванием первой системы комнат Skype Узнайте состояние корпоративного лицензирования развертывания с помощью серверов управления ключами (KMS) или ключей многократной активации (MAK).</span><span class="sxs-lookup"><span data-stu-id="3de1d-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="3de1d-107">Серверы управления ключами (KMS)</span><span class="sxs-lookup"><span data-stu-id="3de1d-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="3de1d-108">Если служба KMS размещается и будет распространяться на активацию корпоративных лицензий на Skype для бизнеса, система комнат Skype автоматически активирует клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3de1d-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="3de1d-109">Чтобы узнать, есть ли у вас служба KMS, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3de1d-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="3de1d-110">В командной строки выполните следующую команду:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="3de1d-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="3de1d-111">Для получения дополнительных сведений Узнайте, [как обнаруживать серверы Office и Windows KMS в службе DNS и удалять неавторизованные экземпляры](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="3de1d-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="3de1d-112">Чтобы настроить KMS, ознакомьтесь со статьей [KMS Activation of office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLK for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="3de1d-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="3de1d-113">Универсальный ключ многократной установки Office 2013 для Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (этот ключ заставляет систему комнаты Skype искать KMS в сети.)</span><span class="sxs-lookup"><span data-stu-id="3de1d-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="3de1d-114">Ключи многократной активации (MAK) из центра поддержки корпоративных лицензий (VLSC)</span><span class="sxs-lookup"><span data-stu-id="3de1d-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="3de1d-115">Если клиент использует любое другое программное обеспечение корпоративного лицензирования, ИТ-отдел будет управлять активацией программного обеспечения и соглашением о корпоративном лицензировании (ВЛА) с помощью VLSC.</span><span class="sxs-lookup"><span data-stu-id="3de1d-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="3de1d-116">Это также позволит компании приобрести активацию корпоративной лицензии Skype для бизнеса, после чего компания сможет получить ключ MAK для входа в консоли администрирования системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="3de1d-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="3de1d-117">Клиент с ВЛА должен знать свои учетные данные VLSC, которые будут использоваться для управления соглашением и получения ключей MAK.</span><span class="sxs-lookup"><span data-stu-id="3de1d-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="3de1d-118">Если вы не уверены, в финансовом отделе клиента должна быть возможность подтвердить, оплачивается ли клиент для ВЛА.</span><span class="sxs-lookup"><span data-stu-id="3de1d-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="3de1d-119">Чтобы получить ключ MAK, обратитесь в центр обслуживания корпоративного лицензирования для просмотра соглашений и скачивания ключей продуктов (MAK).</span><span class="sxs-lookup"><span data-stu-id="3de1d-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="3de1d-120">Для получения дополнительных сведений перейдите в [центр обслуживания корпоративных лицензий](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="3de1d-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="3de1d-121">MAK для Microsoft 365 или Office 365 без доступа к VLSC</span><span class="sxs-lookup"><span data-stu-id="3de1d-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="3de1d-122">Если у клиента нет соглашения о корпоративном лицензировании, активация Skype для бизнеса будет сложнее управлять.</span><span class="sxs-lookup"><span data-stu-id="3de1d-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="3de1d-123">Тем не менее, пользователи Microsoft 365 и Office 365 без доступа к VLSC могут получить рекламный ключ MAK, предоставив следующие сведения для ПВТ, продающей систему комнат Skype:</span><span class="sxs-lookup"><span data-stu-id="3de1d-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="3de1d-124">Название компании</span><span class="sxs-lookup"><span data-stu-id="3de1d-124">Company name</span></span>
    
- <span data-ttu-id="3de1d-125">Имя контакта, адрес электронной почты и номер телефона развертывания</span><span class="sxs-lookup"><span data-stu-id="3de1d-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="3de1d-126">Количество развернутых систем</span><span class="sxs-lookup"><span data-stu-id="3de1d-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="3de1d-127">Дата развертывания</span><span class="sxs-lookup"><span data-stu-id="3de1d-127">Deployment date</span></span>
    
- <span data-ttu-id="3de1d-128">Если у пользователя есть диспетчер технического учета Майкрософт, имя и контактные данные КОНСУЛЬТАНТа</span><span class="sxs-lookup"><span data-stu-id="3de1d-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

