---
title: Set — CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Командлет Set-CcCredential задает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: a97d85ef6fec31383b349e9a0c3b3d9e25d04337
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780678"
---
# <a name="set-cccredential"></a><span data-ttu-id="c566e-103">Set — CcCredential</span><span class="sxs-lookup"><span data-stu-id="c566e-103">Set-CcCredential</span></span>
 
<span data-ttu-id="c566e-104">Командлет Set-CcCredential задает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c566e-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="c566e-105">С помощью Cloud Connector версии 2,0 и более поздних версий этот командлет также может задавать сведения об учетной записи для администратора виртуальной машины и администратора домена.</span><span class="sxs-lookup"><span data-stu-id="c566e-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="c566e-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="c566e-106">Examples</span></span>
<span data-ttu-id="c566e-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c566e-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c566e-108">Пример 1</span><span class="sxs-lookup"><span data-stu-id="c566e-108">Example 1</span></span>

<span data-ttu-id="c566e-109">В следующем примере задаются имя и пароль учетной записи для администратора клиента:</span><span class="sxs-lookup"><span data-stu-id="c566e-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="c566e-110">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="c566e-110">Detailed Description</span></span>
<span data-ttu-id="c566e-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c566e-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c566e-112">Командлет Set – CcCredential задает имя и пароль учетной записи для администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="c566e-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="c566e-113">Для выпусков до 2,0 этот администратор должен быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="c566e-113">For releases prior to 2.0, this administrator must be a Global Administrator.</span></span> <span data-ttu-id="c566e-114">Cloud Connector использует эту учетную запись для получения сведений о конфигурации, установки параметров конфигурации и обновления состояния устройства до конфигурации организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="c566e-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 organization configuration.</span></span> <span data-ttu-id="c566e-115">С выпуском 2,0 и более поздних версий можно также использовать этот командлет, чтобы обновить пароли для учетных записей VmAdmin и DomainAdmin.</span><span class="sxs-lookup"><span data-stu-id="c566e-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c566e-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="c566e-116">Parameters</span></span>
<span data-ttu-id="c566e-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c566e-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="c566e-118">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="c566e-118">**Parameter**</span></span>|<span data-ttu-id="c566e-119">**Required**</span><span class="sxs-lookup"><span data-stu-id="c566e-119">**Required**</span></span>|<span data-ttu-id="c566e-120">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c566e-120">**Type**</span></span>|<span data-ttu-id="c566e-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c566e-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c566e-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="c566e-122">AccountType</span></span> <br/> | <span data-ttu-id="c566e-123">Обязательный</span><span class="sxs-lookup"><span data-stu-id="c566e-123">Required</span></span> <br/> |<span data-ttu-id="c566e-124">System.String</span><span class="sxs-lookup"><span data-stu-id="c566e-124">System.String</span></span>  <br/> | <span data-ttu-id="c566e-125">Параметр должен иметь значение "TenantAdmin", "VmAdmin" или "DomainAdmin".</span><span class="sxs-lookup"><span data-stu-id="c566e-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c566e-126">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="c566e-126">Input Types</span></span>
<span data-ttu-id="c566e-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c566e-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c566e-128">Нет.</span><span class="sxs-lookup"><span data-stu-id="c566e-128">None.</span></span> <span data-ttu-id="c566e-129">Командлет Set – CcCredential не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="c566e-129">The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c566e-130">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="c566e-130">Return Types</span></span>
<span data-ttu-id="c566e-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c566e-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c566e-132">Нет</span><span class="sxs-lookup"><span data-stu-id="c566e-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c566e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="c566e-133">See also</span></span>
<span data-ttu-id="c566e-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c566e-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="c566e-135">Get — CcCredential</span><span class="sxs-lookup"><span data-stu-id="c566e-135">Get-CcCredential</span></span>](get-cccredential.md)
  

