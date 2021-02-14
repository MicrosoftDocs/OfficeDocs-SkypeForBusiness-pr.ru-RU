---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Этот Get-CcExternalCertificateFilePath возвращает путь к файлу внешнего сертификата для развертывания Skype для бизнеса Cloud Connector Edition. Пользователь подготавливает этот сертификат.
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799909"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="20994-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="20994-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="20994-105">Этот Get-CcExternalCertificateFilePath возвращает путь к файлу внешнего сертификата для развертывания Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="20994-105">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="20994-106">Пользователь подготавливает этот сертификат.</span><span class="sxs-lookup"><span data-stu-id="20994-106">The user prepares this certificate.</span></span>
  
<span data-ttu-id="20994-107">Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="20994-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="20994-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="20994-108">Examples</span></span>
<span data-ttu-id="20994-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="20994-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="20994-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="20994-110">Example 1</span></span>

<span data-ttu-id="20994-111">В следующем примере показан путь к сертификату для edge Server:</span><span class="sxs-lookup"><span data-stu-id="20994-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="20994-112">Пример 2</span><span class="sxs-lookup"><span data-stu-id="20994-112">Example 2</span></span>

<span data-ttu-id="20994-113">В следующем примере показан набор сертификатов для сервера-посредника:</span><span class="sxs-lookup"><span data-stu-id="20994-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="20994-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="20994-114">Detailed Description</span></span>
<span data-ttu-id="20994-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="20994-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="20994-116">Во время развертывания или изменения топологии необходимо указать путь к сертификату сервера-посредника и,при необходимости, для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="20994-116">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server.</span></span> <span data-ttu-id="20994-117">Сертификат для сервера-посредника необходим, если между шлюзом и сервером-посредником будет использоваться TLS.</span><span class="sxs-lookup"><span data-stu-id="20994-117">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="20994-118">Чтобы изменить путь, используйте Set-CcExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="20994-118">To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="20994-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="20994-119">Parameters</span></span>
<span data-ttu-id="20994-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="20994-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="20994-121">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="20994-121">**Parameter**</span></span>|<span data-ttu-id="20994-122">**Required**</span><span class="sxs-lookup"><span data-stu-id="20994-122">**Required**</span></span>|<span data-ttu-id="20994-123">**Тип**</span><span class="sxs-lookup"><span data-stu-id="20994-123">**Type**</span></span>|<span data-ttu-id="20994-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="20994-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="20994-125">Target</span><span class="sxs-lookup"><span data-stu-id="20994-125">Target</span></span>  <br/> |<span data-ttu-id="20994-126">Необязательный</span><span class="sxs-lookup"><span data-stu-id="20994-126">Optional</span></span>  <br/> | <span data-ttu-id="20994-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="20994-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="20994-128">Тип запрашиваемого пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="20994-128">Type of file path requested.</span></span> <span data-ttu-id="20994-129">К типам относятся:</span><span class="sxs-lookup"><span data-stu-id="20994-129">Types include:</span></span>  <br/> <span data-ttu-id="20994-130">EdgeServer (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="20994-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="20994-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="20994-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="20994-132">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="20994-132">Input Types</span></span>
<span data-ttu-id="20994-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="20994-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="20994-134">Этот Get-CcExternalCertificateFilePath не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="20994-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="20994-135">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="20994-135">Return Types</span></span>
<span data-ttu-id="20994-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="20994-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="20994-137">Команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="20994-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="20994-138">См. также</span><span class="sxs-lookup"><span data-stu-id="20994-138">See also</span></span>
<span data-ttu-id="20994-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="20994-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="20994-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="20994-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

