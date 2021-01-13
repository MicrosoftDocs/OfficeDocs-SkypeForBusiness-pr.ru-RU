---
title: Лицензия на программное обеспечение skype room System Skype для бизнеса
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
description: В этом разделе вы узнаете, как проверить, есть ли у вас лицензия на программное обеспечение Skype для бизнеса.
ms.openlocfilehash: 20e04f69ba5a931bae6ac8598567165a7a6043a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833929"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="a6933-103">Система комнат Skype: лицензия на программное обеспечение Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a6933-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="a6933-104">В этом разделе вы узнаете, как проверить, есть ли у вас лицензия на программное обеспечение Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a6933-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="a6933-105">Система комнат Skype использует установленный клиент Skype для бизнеса, для которого требуется лицензия на программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="a6933-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="a6933-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span><span class="sxs-lookup"><span data-stu-id="a6933-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="a6933-107">Серверы управления ключами (KMS)</span><span class="sxs-lookup"><span data-stu-id="a6933-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="a6933-108">Если kmS на месте и будет распространять активации с много лицензиями skype для бизнеса, система комнат Skype автоматически активирует клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a6933-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="a6933-109">Чтобы узнать, есть ли KMS:</span><span class="sxs-lookup"><span data-stu-id="a6933-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="a6933-110">В командной командной области запустите 3:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="a6933-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="a6933-111">Дополнительные сведения см. в сведениях о том, как обнаружить точки KMS Office и Windows через DNS и удалить [несанкционированные экземпляры.](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6933-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="a6933-112">Чтобы настроить KMS, см. [kms activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6933-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="a6933-113">Универсальный ключ volume License Key для Lync в Office 2013: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (этот ключ заставляет систему комнат Skype искать KMS в сети).)</span><span class="sxs-lookup"><span data-stu-id="a6933-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="a6933-114">Ключи многократной активации (MAK) из Volume License Service Center (VLSC)</span><span class="sxs-lookup"><span data-stu-id="a6933-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="a6933-115">Если клиент использует любое другое программное обеспечение с много лицензиями, ИТ-отдел будет управлять активацией программного обеспечения и соглашением о программе volume License Agreement (VLA) с помощью VLSC.</span><span class="sxs-lookup"><span data-stu-id="a6933-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="a6933-116">Это также позволит компании приобрести VL-активации Skype для бизнеса, после чего компания может получить mak для ввода в консоли администрирования системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="a6933-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="a6933-117">Клиент с VLA должен знать свои учетные данные VLSC, которые будут использоваться для администрирования соглашения и получения MAK.</span><span class="sxs-lookup"><span data-stu-id="a6933-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="a6933-118">Если это не так, финансовый отдел клиента должен иметь возможность подтвердить, что клиент оплатил VLA.</span><span class="sxs-lookup"><span data-stu-id="a6933-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="a6933-119">Чтобы получить mak, получите доступ к Центру обслуживания корпоративного лицензирования, чтобы просмотреть соглашения и скачать ключи продукта (MAK).</span><span class="sxs-lookup"><span data-stu-id="a6933-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="a6933-120">Дополнительные сведения можно найти в [Центре обслуживания корпоративного лицензирования.](https://www.microsoft.com/Licensing/servicecenter/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6933-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="a6933-121">MAK для Microsoft 365 или Office 365 без доступа к VLSC</span><span class="sxs-lookup"><span data-stu-id="a6933-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="a6933-122">Если у клиента нет соглашения о много лицензии, управлять активацией Skype для бизнеса будет намного сложнее.</span><span class="sxs-lookup"><span data-stu-id="a6933-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="a6933-123">Однако пользователи Microsoft 365 и Office 365 без доступа по VLSC могут получить рекламный MAK, предоставив следующие сведения OEM, продающий систему комнат Skype:</span><span class="sxs-lookup"><span data-stu-id="a6933-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="a6933-124">Имя компании</span><span class="sxs-lookup"><span data-stu-id="a6933-124">Company name</span></span>
    
- <span data-ttu-id="a6933-125">Имя контакта развертывания, электронная почта и номер телефона</span><span class="sxs-lookup"><span data-stu-id="a6933-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="a6933-126">Количество развернутых систем</span><span class="sxs-lookup"><span data-stu-id="a6933-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="a6933-127">Дата развертывания</span><span class="sxs-lookup"><span data-stu-id="a6933-127">Deployment date</span></span>
    
- <span data-ttu-id="a6933-128">Если у клиента есть диспетчер технических учетных записей Майкрософт, имя и контактные данные менеджера</span><span class="sxs-lookup"><span data-stu-id="a6933-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

