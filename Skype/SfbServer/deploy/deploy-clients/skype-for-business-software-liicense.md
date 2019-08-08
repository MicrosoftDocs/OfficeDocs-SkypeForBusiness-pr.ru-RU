---
title: Лицензия на программное обеспечение Skype для бизнеса на комнате Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: В этом разделе описывается проверка наличия корпоративной лицензии на программное обеспечение Skype для бизнеса.
ms.openlocfilehash: 731eefa49714fdced552c6cbedf4ecc288065d6b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234725"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="6a0fd-103">Система комнат Skype: лицензия на использование программного обеспечения Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6a0fd-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="6a0fd-104">В этом разделе описывается проверка наличия корпоративной лицензии на программное обеспечение Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6a0fd-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="6a0fd-105">Система комнат Skype использует установленный клиент Skype для бизнеса, для которого требуется программная лицензия.</span><span class="sxs-lookup"><span data-stu-id="6a0fd-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="6a0fd-106">Перед развертыванием первой системы комнаты Skype ознакомьтесь с корпоративным состоянием лицензии на развертывание (с помощью серверов управления ключами (KMS) или ключа многократной активации (MAK).</span><span class="sxs-lookup"><span data-stu-id="6a0fd-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="6a0fd-107">Серверы управления ключами (KMS)</span><span class="sxs-lookup"><span data-stu-id="6a0fd-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="6a0fd-108">Если на вашем компьютере установлены службы KMS и они будут распространяться на активацию корпоративного лицензирования в Skype для бизнеса, система помещения в Skype будет автоматически активировать клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6a0fd-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="6a0fd-109">Чтобы узнать, настроены ли серверы управления ключами, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6a0fd-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="6a0fd-110">В командной строке выполните:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="6a0fd-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="6a0fd-111">Дополнительные сведения [можно найти в разделе Обнаружение узлов Office и KMS в службе DNS и удаление неавторизованных экземпляров](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="6a0fd-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="6a0fd-112">Сведения о настройке KMS-активации можно найти в разделе [Активация KMS для office 2013](https://technet.microsoft.com/library/ee624357.aspx) и [гвлкс для KMS и Active Directory активация Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a0fd-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="6a0fd-113">Корпоративная лицензия Office 2013 для Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (этот ключ приводит к тому, что система комнаты Skype будет искать сервер службы KMS в сети).</span><span class="sxs-lookup"><span data-stu-id="6a0fd-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="6a0fd-114">Ключи многократной активации (MAK) из Volume Licensing Service Center (VLSC)</span><span class="sxs-lookup"><span data-stu-id="6a0fd-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="6a0fd-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span><span class="sxs-lookup"><span data-stu-id="6a0fd-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="6a0fd-116">Это также позволит компании приобрести активацию корпоративной лицензии Skype для бизнеса, после чего компания сможет получить MAK для ввода данных в консоли администрирования системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="6a0fd-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="6a0fd-117">Клиент с VLA должен знать свои учетные данные VLSC, которые будут использоваться для администрирования соглашения и получения MAK.</span><span class="sxs-lookup"><span data-stu-id="6a0fd-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="6a0fd-118">Если это не было уверенно, финансовый отдел клиента должен подтвердить, оплачивается ли клиент для ВЛА.</span><span class="sxs-lookup"><span data-stu-id="6a0fd-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="6a0fd-119">Для получения MAK необходимо перейти в Volume Licensing Service Center для просмотра соглашения и загрузки ключей продукта (MAK).</span><span class="sxs-lookup"><span data-stu-id="6a0fd-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="6a0fd-120">Дополнительные сведения можно найти в [центре обслуживания для корпоративного лицензирования](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="6a0fd-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="6a0fd-121">MAK для Office 365 без получения доступа к VLSC</span><span class="sxs-lookup"><span data-stu-id="6a0fd-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="6a0fd-122">Если у клиента нет соглашения о корпоративном лицензировании, активация Skype для бизнеса будет сложнее управлять.</span><span class="sxs-lookup"><span data-stu-id="6a0fd-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="6a0fd-123">Тем не менее, пользователи Office 365, у которых нет доступа к централизованному доступу, могут получить рекламный ключ MAK, предоставив следующие данные для OEM-компании, продающей систему комнаты Skype:</span><span class="sxs-lookup"><span data-stu-id="6a0fd-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="6a0fd-124">Название компании</span><span class="sxs-lookup"><span data-stu-id="6a0fd-124">Company name</span></span>
    
- <span data-ttu-id="6a0fd-125">Имя, адрес электронной почты и номер телефона контактного лица по вопросам развертывания</span><span class="sxs-lookup"><span data-stu-id="6a0fd-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="6a0fd-126">Количество развернутых систем</span><span class="sxs-lookup"><span data-stu-id="6a0fd-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="6a0fd-127">Дата развертывания</span><span class="sxs-lookup"><span data-stu-id="6a0fd-127">Deployment date</span></span>
    
- <span data-ttu-id="6a0fd-128">Если у клиента есть технический консультант Microsoft, имя и контактные данные у КОНСУЛЬТАНТа</span><span class="sxs-lookup"><span data-stu-id="6a0fd-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

