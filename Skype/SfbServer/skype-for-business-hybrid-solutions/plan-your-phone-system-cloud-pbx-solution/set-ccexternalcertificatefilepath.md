---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Этот Set-CcExternalCertificateFilePath указывает путь, в котором хранится сертификат для сервера-посредника или сервера-посредника.
ms.openlocfilehash: 9216b82626da7160d6e1bfa8d611757321a2683a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824203"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="de4d8-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="de4d8-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="de4d8-104">Этот Set-CcExternalCertificateFilePath указывает путь, в котором хранится сертификат для сервера-посредника или сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="de4d8-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="de4d8-105">Этот сертификат требуется во время развертывания или при добавлении новых устройств Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="de4d8-105">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="de4d8-106">Команда также позволяет импортировать новый сертификат для сервера-посредника после развертывания.</span><span class="sxs-lookup"><span data-stu-id="de4d8-106">The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="de4d8-107">Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="de4d8-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="de4d8-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="de4d8-108">Examples</span></span>
<span data-ttu-id="de4d8-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="de4d8-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="de4d8-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="de4d8-110">Example 1</span></span>

<span data-ttu-id="de4d8-111">В следующем примере задан путь к сертификату для edge Server:</span><span class="sxs-lookup"><span data-stu-id="de4d8-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="de4d8-112">Пример 2</span><span class="sxs-lookup"><span data-stu-id="de4d8-112">Example 2</span></span>

<span data-ttu-id="de4d8-113">В следующем примере задан путь к сертификату для сервера-посредника:</span><span class="sxs-lookup"><span data-stu-id="de4d8-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="de4d8-114">Пример 3</span><span class="sxs-lookup"><span data-stu-id="de4d8-114">Example 3</span></span>

<span data-ttu-id="de4d8-115">В следующем примере обновляется сертификат для сервера-посредника:</span><span class="sxs-lookup"><span data-stu-id="de4d8-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="de4d8-116">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="de4d8-116">Detailed Description</span></span>
<span data-ttu-id="de4d8-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="de4d8-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="de4d8-118">Во время развертывания или при изменении топологии необходимо указать путь к сертификату сервера-посредника и, при необходимости, сертификату сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="de4d8-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="de4d8-119">Сертификат для сервера-посредника необходим, если между шлюзом и сервером-посредником будет использоваться TLS.</span><span class="sxs-lookup"><span data-stu-id="de4d8-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="de4d8-120">При развертывании устройства Cloud Connector и развертывании TLS можно указать только путь к сертификату, который будет развернут на сервере-посреднике.</span><span class="sxs-lookup"><span data-stu-id="de4d8-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="de4d8-121">Однако если вы хотите обновить сертификат-посредник на уже развернутом устройстве, необходимо указать путь и параметр -Import.</span><span class="sxs-lookup"><span data-stu-id="de4d8-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="de4d8-122">Чтобы увидеть путь, используйте Get-CCExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="de4d8-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="de4d8-123">Параметры</span><span class="sxs-lookup"><span data-stu-id="de4d8-123">Parameters</span></span>
<span data-ttu-id="de4d8-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="de4d8-124"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="de4d8-125">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="de4d8-125">**Parameter**</span></span>|<span data-ttu-id="de4d8-126">**Required**</span><span class="sxs-lookup"><span data-stu-id="de4d8-126">**Required**</span></span>|<span data-ttu-id="de4d8-127">**Тип**</span><span class="sxs-lookup"><span data-stu-id="de4d8-127">**Type**</span></span>|<span data-ttu-id="de4d8-128">**Описание**</span><span class="sxs-lookup"><span data-stu-id="de4d8-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="de4d8-129">Target</span><span class="sxs-lookup"><span data-stu-id="de4d8-129">Target</span></span> <br/> | <span data-ttu-id="de4d8-130">Обязательный</span><span class="sxs-lookup"><span data-stu-id="de4d8-130">Required</span></span> <br/> |<span data-ttu-id="de4d8-131">System.String</span><span class="sxs-lookup"><span data-stu-id="de4d8-131">System.String</span></span>  <br/> |<span data-ttu-id="de4d8-132">Тип запрашиваемого пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="de4d8-132">Type of file path requested.</span></span> <span data-ttu-id="de4d8-133">К типам относятся:</span><span class="sxs-lookup"><span data-stu-id="de4d8-133">Types include:</span></span>  <br/> <span data-ttu-id="de4d8-134">EdgeServer (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="de4d8-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="de4d8-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="de4d8-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="de4d8-136">Импорт</span><span class="sxs-lookup"><span data-stu-id="de4d8-136">Import</span></span>  <br/> |<span data-ttu-id="de4d8-137">Необязательный</span><span class="sxs-lookup"><span data-stu-id="de4d8-137">Optional</span></span>  <br/> |<span data-ttu-id="de4d8-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="de4d8-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="de4d8-139">Указывает, что сертификат необходимо импортировать на сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="de4d8-139">Indicates that the certificate must be imported to the Mediation Server.</span></span> <span data-ttu-id="de4d8-140">Этот параметр не требуется при первом развертывании устройства.</span><span class="sxs-lookup"><span data-stu-id="de4d8-140">This parameter is not needed if you deploy an appliance for first time.</span></span> <span data-ttu-id="de4d8-141">Этот параметр необходим, если требуется изменить существующий сертификат в уже развернутой версии.</span><span class="sxs-lookup"><span data-stu-id="de4d8-141">The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="de4d8-142">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="de4d8-142">Input Types</span></span>
<span data-ttu-id="de4d8-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="de4d8-143"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="de4d8-144">Этот Set-CcExternalCertificateFilePath не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="de4d8-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="de4d8-145">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="de4d8-145">Return Types</span></span>
<span data-ttu-id="de4d8-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="de4d8-146"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="de4d8-147">Нет</span><span class="sxs-lookup"><span data-stu-id="de4d8-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="de4d8-148">См. также</span><span class="sxs-lookup"><span data-stu-id="de4d8-148">See also</span></span>
<span data-ttu-id="de4d8-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="de4d8-149"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="de4d8-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="de4d8-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

