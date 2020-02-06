---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 'Командлет Renew-CcServerCertificate продлевает сертификаты Skype для бизнеса Cloud Connector Edition, срок действия которых истекает или уже истек. Эта команда была заменена на Update-CcServerCertificate в Cloud Connector 2.0 и более поздних выпусков. '
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824265"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="4dfdd-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="4dfdd-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="4dfdd-p102">Командлет Renew-CcServerCertificate продлевает сертификаты Skype для бизнеса Cloud Connector Edition, срок действия которых истекает или уже истек. Эта команда была заменена на Update-CcServerCertificate в Cloud Connector 2.0 и более поздних выпусков. </span><span class="sxs-lookup"><span data-stu-id="4dfdd-p102">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired. This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="4dfdd-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="4dfdd-107">Examples</span></span>
<span data-ttu-id="4dfdd-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4dfdd-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="4dfdd-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="4dfdd-109">Example 1</span></span>

<span data-ttu-id="4dfdd-110">В следующем примере продлеваются сертификаты сервера центрального хранилища управления (CMS), сервера-посредника или пограничного сервера, срок действия которых истекает или уже истек.</span><span class="sxs-lookup"><span data-stu-id="4dfdd-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="4dfdd-111">Пример 2</span><span class="sxs-lookup"><span data-stu-id="4dfdd-111">Example 2</span></span>

<span data-ttu-id="4dfdd-112">В следующем примере продлеваются сертификаты сервера-посредника или пограничного сервера, срок действия которых истекает или уже истек.</span><span class="sxs-lookup"><span data-stu-id="4dfdd-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="4dfdd-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="4dfdd-113">Detailed Description</span></span>
<span data-ttu-id="4dfdd-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4dfdd-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="4dfdd-115">Внутренние сертификаты облачного соединителя, выданные для хранилища центрального управления, сервера-посредника и пограничного сервера, действительны в течение двух лет после того, как они были выпущены в службе сертификации.</span><span class="sxs-lookup"><span data-stu-id="4dfdd-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="4dfdd-116">Если срок действия сертификатов истекает или уже истек, выполните командлет Renew-CcServerCertificate для их продления.</span><span class="sxs-lookup"><span data-stu-id="4dfdd-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="4dfdd-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="4dfdd-117">Parameters</span></span>
<span data-ttu-id="4dfdd-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4dfdd-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="4dfdd-119">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="4dfdd-119">**Parameter**</span></span>|<span data-ttu-id="4dfdd-120">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="4dfdd-120">**Required**</span></span>|<span data-ttu-id="4dfdd-121">**Тип**</span><span class="sxs-lookup"><span data-stu-id="4dfdd-121">**Type**</span></span>|<span data-ttu-id="4dfdd-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4dfdd-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4dfdd-123">Роли</span><span class="sxs-lookup"><span data-stu-id="4dfdd-123">Roles</span></span>  <br/> |<span data-ttu-id="4dfdd-124">Необязательно </span><span class="sxs-lookup"><span data-stu-id="4dfdd-124">Optional</span></span>  <br/> |<span data-ttu-id="4dfdd-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="4dfdd-125">System.Array</span></span>  <br/> | <span data-ttu-id="4dfdd-126"> Массив ролей сервера Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4dfdd-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="4dfdd-127">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="4dfdd-127">Input Types</span></span>
<span data-ttu-id="4dfdd-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4dfdd-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="4dfdd-p104">Нет. Командлет Renew-CcServerCertificate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="4dfdd-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4dfdd-131">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="4dfdd-131">Return Types</span></span>
<span data-ttu-id="4dfdd-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4dfdd-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="4dfdd-133">Нет</span><span class="sxs-lookup"><span data-stu-id="4dfdd-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4dfdd-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4dfdd-134">See also</span></span>
<span data-ttu-id="4dfdd-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4dfdd-135"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="4dfdd-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="4dfdd-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="4dfdd-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="4dfdd-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="4dfdd-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="4dfdd-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

