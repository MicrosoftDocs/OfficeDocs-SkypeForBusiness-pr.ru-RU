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
ms.openlocfilehash: 7a471b0e4258728bfaa50558aab54955346b457c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003379"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="50be1-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="50be1-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="50be1-p102">Командлет Get-CcExternalCertificateFilePath возвращает путь к файлу внешнего сертификата для развертывания Skype для бизнеса Cloud Connector Edition. Этот сертификат подготавливается пользователем.</span><span class="sxs-lookup"><span data-stu-id="50be1-p102">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment. The user prepares this certificate.</span></span>
  
<span data-ttu-id="50be1-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="50be1-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="50be1-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="50be1-108">Examples</span></span>
<span data-ttu-id="50be1-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="50be1-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="50be1-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="50be1-110">Example 1</span></span>

<span data-ttu-id="50be1-111">В следующем примере показан путь к сертификату пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="50be1-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="50be1-112">Пример 2</span><span class="sxs-lookup"><span data-stu-id="50be1-112">Example 2</span></span>

<span data-ttu-id="50be1-113">В следующем примере показан путь к сертификату сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="50be1-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="50be1-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="50be1-114">Detailed Description</span></span>
<span data-ttu-id="50be1-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="50be1-115"></span></span>

<span data-ttu-id="50be1-p103">При развертывании или изменении топологии необходимо указать путь к сертификату пограничного сервера и при необходимости к сертификату сервера-посредника. Сертификат сервера-посредника требуется в том случае, если между шлюзами и сервером-посредником используется протокол TLS.Чтобы изменить путь, используйте командлет Set-CcExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="50be1-p103">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server. The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server. To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="50be1-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="50be1-119">Parameters</span></span>
<span data-ttu-id="50be1-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="50be1-120"></span></span>

|<span data-ttu-id="50be1-121">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="50be1-121">**Parameter**</span></span>|<span data-ttu-id="50be1-122">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="50be1-122">**Required**</span></span>|<span data-ttu-id="50be1-123">**Тип**</span><span class="sxs-lookup"><span data-stu-id="50be1-123">**Type**</span></span>|<span data-ttu-id="50be1-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="50be1-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="50be1-125">Целевой объект</span><span class="sxs-lookup"><span data-stu-id="50be1-125">Target</span></span>  <br/> |<span data-ttu-id="50be1-126">Необязательно</span><span class="sxs-lookup"><span data-stu-id="50be1-126">Optional</span></span>  <br/> | <span data-ttu-id="50be1-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="50be1-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="50be1-p104">Тип запрашиваемого пути к файлу. Возможные типы:</span><span class="sxs-lookup"><span data-stu-id="50be1-p104">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="50be1-130">EdgeServer (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="50be1-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="50be1-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="50be1-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="50be1-132">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="50be1-132">Input Types</span></span>
<span data-ttu-id="50be1-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50be1-133"></span></span>

<span data-ttu-id="50be1-134">Командлет Get-CcExternalCertificateFilePath не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="50be1-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="50be1-135">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="50be1-135">Return Types</span></span>
<span data-ttu-id="50be1-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50be1-136"></span></span>

<span data-ttu-id="50be1-137">Команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="50be1-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="50be1-138">См. также</span><span class="sxs-lookup"><span data-stu-id="50be1-138">See also</span></span>
<span data-ttu-id="50be1-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50be1-139"></span></span>

[<span data-ttu-id="50be1-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="50be1-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

