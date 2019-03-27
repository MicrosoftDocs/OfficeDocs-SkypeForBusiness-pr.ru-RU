---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Командлет Set-CcExternalCertificateFilePath задает путь к сертификату для сервера-посредника или пограничного сервера.
ms.openlocfilehash: 059d0f2fbf5fee708ceccd0d6e10ad4286fe4f85
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895351"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="e1b32-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="e1b32-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="e1b32-104">Командлет Set-CcExternalCertificateFilePath задает путь к сертификату для сервера-посредника или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e1b32-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="e1b32-p101">Этот сертификат требуется для развертывания, а также при добавлении новых устройств Skype для бизнеса Cloud Connector Edition. Кроме того, эта команда позволяет импортировать новый сертификат для сервера-посредника после развертывания.</span><span class="sxs-lookup"><span data-stu-id="e1b32-p101">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition. The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="e1b32-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="e1b32-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="e1b32-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="e1b32-108">Examples</span></span>
<span data-ttu-id="e1b32-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e1b32-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="e1b32-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="e1b32-110">Example 1</span></span>

<span data-ttu-id="e1b32-111">В следующем примере задается путь к сертификату пограничного сервера:</span><span class="sxs-lookup"><span data-stu-id="e1b32-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="e1b32-112">Пример 2</span><span class="sxs-lookup"><span data-stu-id="e1b32-112">Example 2</span></span>

<span data-ttu-id="e1b32-113">В следующем примере задается путь к сертификату сервера-посредника:</span><span class="sxs-lookup"><span data-stu-id="e1b32-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="e1b32-114">Пример 3</span><span class="sxs-lookup"><span data-stu-id="e1b32-114">Example 3</span></span>

<span data-ttu-id="e1b32-115">В следующем примере обновляется сертификат сервера-посредника:</span><span class="sxs-lookup"><span data-stu-id="e1b32-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="e1b32-116">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="e1b32-116">Detailed Description</span></span>
<span data-ttu-id="e1b32-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e1b32-117"></span></span>

<span data-ttu-id="e1b32-118">При развертывании или изменении топологии необходимо указать путь к сертификату пограничного сервера и при необходимости к сертификату сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="e1b32-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="e1b32-119">Сертификат сервера-посредника требуется в том случае, если между шлюзами и сервером-посредником используется протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="e1b32-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="e1b32-120">При развертывании appliance облачных соединителя и хотите развернуть TLS, можно указать только путь к сертификату, который будет развертываться на сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="e1b32-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="e1b32-121">Тем не менее, если вы хотите обновить сертификат посредника на ранее развернутом устройстве, необходимо указать путь и параметр -Import.</span><span class="sxs-lookup"><span data-stu-id="e1b32-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="e1b32-122">Чтобы просмотреть путь, используйте командлет Get-CCExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="e1b32-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="e1b32-123">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1b32-123">Parameters</span></span>
<span data-ttu-id="e1b32-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e1b32-124"></span></span>

|<span data-ttu-id="e1b32-125">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="e1b32-125">**Parameter**</span></span>|<span data-ttu-id="e1b32-126">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="e1b32-126">**Required**</span></span>|<span data-ttu-id="e1b32-127">**Тип**</span><span class="sxs-lookup"><span data-stu-id="e1b32-127">**Type**</span></span>|<span data-ttu-id="e1b32-128">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="e1b32-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e1b32-129">Целевой объект</span><span class="sxs-lookup"><span data-stu-id="e1b32-129">Target</span></span> <br/> | <span data-ttu-id="e1b32-130">Обязательно</span><span class="sxs-lookup"><span data-stu-id="e1b32-130">Required</span></span> <br/> |<span data-ttu-id="e1b32-131">System.String</span><span class="sxs-lookup"><span data-stu-id="e1b32-131">System.String</span></span>  <br/> |<span data-ttu-id="e1b32-p103">Тип запрашиваемого пути к файлу. Возможные типы:</span><span class="sxs-lookup"><span data-stu-id="e1b32-p103">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="e1b32-134">EdgeServer (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e1b32-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="e1b32-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="e1b32-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="e1b32-136">Импорт</span><span class="sxs-lookup"><span data-stu-id="e1b32-136">Import</span></span>  <br/> |<span data-ttu-id="e1b32-137">Необязательно</span><span class="sxs-lookup"><span data-stu-id="e1b32-137">Optional</span></span>  <br/> |<span data-ttu-id="e1b32-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="e1b32-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="e1b32-p104">Указывает, что сертификат необходимо импортировать на сервер-посредник. Этот параметр не требуется, если устройство развертывается впервые. Этот параметр обязателен, если требуется заменить существующий сертификат для ранее развернутой версии.</span><span class="sxs-lookup"><span data-stu-id="e1b32-p104">Indicates that the certificate must be imported to the Mediation Server. This parameter is not needed if you deploy an appliance for first time. The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="e1b32-142">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="e1b32-142">Input Types</span></span>
<span data-ttu-id="e1b32-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e1b32-143"></span></span>

<span data-ttu-id="e1b32-144">Командлет Set-CcExternalCertificateFilePath не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="e1b32-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e1b32-145">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="e1b32-145">Return Types</span></span>
<span data-ttu-id="e1b32-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e1b32-146"></span></span>

<span data-ttu-id="e1b32-147">Нет</span><span class="sxs-lookup"><span data-stu-id="e1b32-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e1b32-148">См. также</span><span class="sxs-lookup"><span data-stu-id="e1b32-148">See also</span></span>
<span data-ttu-id="e1b32-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e1b32-149"></span></span>

[<span data-ttu-id="e1b32-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="e1b32-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

