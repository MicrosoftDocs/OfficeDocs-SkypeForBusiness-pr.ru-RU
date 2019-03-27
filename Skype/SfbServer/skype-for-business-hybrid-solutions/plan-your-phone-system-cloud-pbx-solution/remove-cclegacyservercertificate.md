---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Командлет Remove-CcLegacyServerCertificate удаляет прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после выполнения командлетов Renew-CcCACertificate или Renew CcServerCertificate.
ms.openlocfilehash: 5f148aa083b646565adf0158f34fb15314296170
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882462"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="9df85-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="9df85-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="9df85-104">Командлет Remove-CcLegacyServerCertificate удаляет прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после выполнения командлетов Renew-CcCACertificate или Renew CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="9df85-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="9df85-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="9df85-105">Examples</span></span>
<span data-ttu-id="9df85-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9df85-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="9df85-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="9df85-107">Example 1</span></span>

<span data-ttu-id="9df85-108">В следующем примере удаляются прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после продления сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9df85-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="9df85-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="9df85-109">Example 2</span></span>

<span data-ttu-id="9df85-110">В следующем примере удаляются прежние версии сертификатов сервера-посредника и пограничного сервера после продления сертификатов. </span><span class="sxs-lookup"><span data-stu-id="9df85-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="9df85-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="9df85-111">Parameters</span></span>
<span data-ttu-id="9df85-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9df85-112"></span></span>

|<span data-ttu-id="9df85-113">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="9df85-113">**Parameter**</span></span>|<span data-ttu-id="9df85-114">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="9df85-114">**Required**</span></span>|<span data-ttu-id="9df85-115">**Тип**</span><span class="sxs-lookup"><span data-stu-id="9df85-115">**Type**</span></span>|<span data-ttu-id="9df85-116">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="9df85-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="9df85-117">Роли</span><span class="sxs-lookup"><span data-stu-id="9df85-117">Roles</span></span> <br/> |<span data-ttu-id="9df85-118">Необязательно </span><span class="sxs-lookup"><span data-stu-id="9df85-118">Optional</span></span>  <br/> |<span data-ttu-id="9df85-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="9df85-119">System.Array</span></span>  <br/> | <span data-ttu-id="9df85-120"> Массив ролей сервера Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9df85-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9df85-121">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="9df85-121">Input Types</span></span>
<span data-ttu-id="9df85-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9df85-122"></span></span>

<span data-ttu-id="9df85-p101">Нет. Командлет Remove-CcLegacyServerCertificate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9df85-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9df85-125">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="9df85-125">Return Types</span></span>
<span data-ttu-id="9df85-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9df85-126"></span></span>

<span data-ttu-id="9df85-127">Нет</span><span class="sxs-lookup"><span data-stu-id="9df85-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9df85-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9df85-128">See also</span></span>
<span data-ttu-id="9df85-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9df85-129"></span></span>

[<span data-ttu-id="9df85-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="9df85-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="9df85-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="9df85-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="9df85-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="9df85-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="9df85-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="9df85-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

