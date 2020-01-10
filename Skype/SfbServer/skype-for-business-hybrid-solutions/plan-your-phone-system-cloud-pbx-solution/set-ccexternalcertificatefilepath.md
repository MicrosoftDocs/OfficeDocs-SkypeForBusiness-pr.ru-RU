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
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Командлет Set-CcExternalCertificateFilePath задает путь к сертификату для сервера-посредника или пограничного сервера.
ms.openlocfilehash: e71a50f09a4ce3d085746c30f7591e8a07eb38de
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003209"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="0aaee-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="0aaee-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="0aaee-104">Командлет Set-CcExternalCertificateFilePath задает путь к сертификату для сервера-посредника или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="0aaee-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="0aaee-p101">Этот сертификат требуется для развертывания, а также при добавлении новых устройств Skype для бизнеса Cloud Connector Edition. Кроме того, эта команда позволяет импортировать новый сертификат для сервера-посредника после развертывания.</span><span class="sxs-lookup"><span data-stu-id="0aaee-p101">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition. The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="0aaee-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="0aaee-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="0aaee-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="0aaee-108">Examples</span></span>
<span data-ttu-id="0aaee-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0aaee-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="0aaee-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="0aaee-110">Example 1</span></span>

<span data-ttu-id="0aaee-111">В следующем примере задается путь к сертификату пограничного сервера:</span><span class="sxs-lookup"><span data-stu-id="0aaee-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="0aaee-112">Пример 2</span><span class="sxs-lookup"><span data-stu-id="0aaee-112">Example 2</span></span>

<span data-ttu-id="0aaee-113">В следующем примере задается путь к сертификату сервера-посредника:</span><span class="sxs-lookup"><span data-stu-id="0aaee-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="0aaee-114">Пример 3</span><span class="sxs-lookup"><span data-stu-id="0aaee-114">Example 3</span></span>

<span data-ttu-id="0aaee-115">В следующем примере обновляется сертификат сервера-посредника:</span><span class="sxs-lookup"><span data-stu-id="0aaee-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="0aaee-116">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="0aaee-116">Detailed Description</span></span>
<span data-ttu-id="0aaee-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0aaee-117"></span></span>

<span data-ttu-id="0aaee-118">При развертывании или изменении топологии необходимо указать путь к сертификату пограничного сервера и при необходимости к сертификату сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="0aaee-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="0aaee-119">Сертификат сервера-посредника требуется в том случае, если между шлюзами и сервером-посредником используется протокол TLS.</span><span class="sxs-lookup"><span data-stu-id="0aaee-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="0aaee-120">При развертывании устройства облачного соединителя и необходимости развертывания протокола TLS вы можете указать путь к сертификату, который будет развернут на сервере-посреднике.</span><span class="sxs-lookup"><span data-stu-id="0aaee-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="0aaee-121">Тем не менее, если вы хотите обновить сертификат посредника на ранее развернутом устройстве, необходимо указать путь и параметр -Import.</span><span class="sxs-lookup"><span data-stu-id="0aaee-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="0aaee-122">Чтобы просмотреть путь, используйте командлет Get-CCExternalCertificateFilePath.</span><span class="sxs-lookup"><span data-stu-id="0aaee-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0aaee-123">Параметры</span><span class="sxs-lookup"><span data-stu-id="0aaee-123">Parameters</span></span>
<span data-ttu-id="0aaee-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0aaee-124"></span></span>

|<span data-ttu-id="0aaee-125">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="0aaee-125">**Parameter**</span></span>|<span data-ttu-id="0aaee-126">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="0aaee-126">**Required**</span></span>|<span data-ttu-id="0aaee-127">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0aaee-127">**Type**</span></span>|<span data-ttu-id="0aaee-128">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0aaee-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0aaee-129">Целевой объект</span><span class="sxs-lookup"><span data-stu-id="0aaee-129">Target</span></span> <br/> | <span data-ttu-id="0aaee-130">Обязательно</span><span class="sxs-lookup"><span data-stu-id="0aaee-130">Required</span></span> <br/> |<span data-ttu-id="0aaee-131">System.String</span><span class="sxs-lookup"><span data-stu-id="0aaee-131">System.String</span></span>  <br/> |<span data-ttu-id="0aaee-p103">Тип запрашиваемого пути к файлу. Возможные типы:</span><span class="sxs-lookup"><span data-stu-id="0aaee-p103">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="0aaee-134">EdgeServer (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0aaee-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="0aaee-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="0aaee-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="0aaee-136">Импорт</span><span class="sxs-lookup"><span data-stu-id="0aaee-136">Import</span></span>  <br/> |<span data-ttu-id="0aaee-137">Необязательно</span><span class="sxs-lookup"><span data-stu-id="0aaee-137">Optional</span></span>  <br/> |<span data-ttu-id="0aaee-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0aaee-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0aaee-p104">Указывает, что сертификат необходимо импортировать на сервер-посредник. Этот параметр не требуется, если устройство развертывается впервые. Этот параметр обязателен, если требуется заменить существующий сертификат для ранее развернутой версии.</span><span class="sxs-lookup"><span data-stu-id="0aaee-p104">Indicates that the certificate must be imported to the Mediation Server. This parameter is not needed if you deploy an appliance for first time. The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0aaee-142">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="0aaee-142">Input Types</span></span>
<span data-ttu-id="0aaee-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0aaee-143"></span></span>

<span data-ttu-id="0aaee-144">Командлет Set-CcExternalCertificateFilePath не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="0aaee-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0aaee-145">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="0aaee-145">Return Types</span></span>
<span data-ttu-id="0aaee-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0aaee-146"></span></span>

<span data-ttu-id="0aaee-147">Нет</span><span class="sxs-lookup"><span data-stu-id="0aaee-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0aaee-148">См. также</span><span class="sxs-lookup"><span data-stu-id="0aaee-148">See also</span></span>
<span data-ttu-id="0aaee-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0aaee-149"></span></span>

[<span data-ttu-id="0aaee-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="0aaee-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

