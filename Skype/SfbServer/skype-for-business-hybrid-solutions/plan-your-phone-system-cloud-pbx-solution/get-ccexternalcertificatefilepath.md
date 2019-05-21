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
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Командлет Get-CcExternalCertificateFilePath возвращает путь к файлу внешнего сертификата для развертывания Skype для бизнеса Cloud Connector Edition. Этот сертификат подготавливается пользователем.
ms.openlocfilehash: ed725814380741aade73166d01025650dfa78538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287323"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="5b102-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="5b102-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="5b102-p102">Командлет Get-CcExternalCertificateFilePath возвращает путь к файлу внешнего сертификата для развертывания Skype для бизнеса Cloud Connector Edition. Этот сертификат подготавливается пользователем.</span><span class="sxs-lookup"><span data-stu-id="5b102-p102">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment. The user prepares this certificate.</span></span>
  
<span data-ttu-id="5b102-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="5b102-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="5b102-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="5b102-108">Examples</span></span>
<span data-ttu-id="5b102-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5b102-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="5b102-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="5b102-110">Example 1</span></span>

<span data-ttu-id="5b102-111">В следующем примере показан путь к сертификату пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5b102-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="5b102-112">Пример 2</span><span class="sxs-lookup"><span data-stu-id="5b102-112">Example 2</span></span>

<span data-ttu-id="5b102-113">В следующем примере показан путь к сертификату сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="5b102-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="5b102-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="5b102-114">Detailed Description</span></span>
<span data-ttu-id="5b102-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5b102-115"></span></span>

<span data-ttu-id="5b102-p103">При развертывании или изменении топологии необходимо указать путь к сертификату пограничного сервера и при необходимости к сертификату сервера-посредника. Сертификат сервера-посредника требуется в том случае, если между шлюзами и сервером-посредником используется протокол TLS.Чтобы изменить путь, используйте командлет Set-CcExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="5b102-p103">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server. The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server. To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="5b102-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b102-119">Parameters</span></span>
<span data-ttu-id="5b102-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5b102-120"></span></span>

|<span data-ttu-id="5b102-121">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="5b102-121">**Parameter**</span></span>|<span data-ttu-id="5b102-122">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="5b102-122">**Required**</span></span>|<span data-ttu-id="5b102-123">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5b102-123">**Type**</span></span>|<span data-ttu-id="5b102-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5b102-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5b102-125">Целевой объект</span><span class="sxs-lookup"><span data-stu-id="5b102-125">Target</span></span>  <br/> |<span data-ttu-id="5b102-126">Необязательно</span><span class="sxs-lookup"><span data-stu-id="5b102-126">Optional</span></span>  <br/> | <span data-ttu-id="5b102-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5b102-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="5b102-p104">Тип запрашиваемого пути к файлу. Возможные типы:</span><span class="sxs-lookup"><span data-stu-id="5b102-p104">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="5b102-130">EdgeServer (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5b102-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="5b102-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="5b102-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5b102-132">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="5b102-132">Input Types</span></span>
<span data-ttu-id="5b102-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b102-133"></span></span>

<span data-ttu-id="5b102-134">Командлет Get-CcExternalCertificateFilePath не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="5b102-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5b102-135">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="5b102-135">Return Types</span></span>
<span data-ttu-id="5b102-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b102-136"></span></span>

<span data-ttu-id="5b102-137">Команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="5b102-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b102-138">См. также</span><span class="sxs-lookup"><span data-stu-id="5b102-138">See also</span></span>
<span data-ttu-id="5b102-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5b102-139"></span></span>

[<span data-ttu-id="5b102-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="5b102-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

