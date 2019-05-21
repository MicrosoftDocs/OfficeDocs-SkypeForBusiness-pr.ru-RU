---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'Командлет Set-CcCredential задает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition. '
ms.openlocfilehash: 59c058f8965bbc6fc011806f383c547c1e7b6cd1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286980"
---
# <a name="set-cccredential"></a><span data-ttu-id="8ae71-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="8ae71-103">Set-CcCredential</span></span>
 
<span data-ttu-id="8ae71-104">Командлет Set-CcCredential задает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="8ae71-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="8ae71-105">С помощью облачного соединителя версии 2,0 и более поздних версий этот командлет также может задать сведения об учетной записи для администратора виртуальных машин и для администратора домена.</span><span class="sxs-lookup"><span data-stu-id="8ae71-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="8ae71-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="8ae71-106">Examples</span></span>
<span data-ttu-id="8ae71-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8ae71-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="8ae71-108">Пример 1</span><span class="sxs-lookup"><span data-stu-id="8ae71-108">Example 1</span></span>

<span data-ttu-id="8ae71-109">В следующем примере задаются имя и пароль учетной записи для администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="8ae71-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="8ae71-110">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="8ae71-110">Detailed Description</span></span>
<span data-ttu-id="8ae71-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8ae71-111"></span></span>

<span data-ttu-id="8ae71-112">Командлет Set-CcCredential задает имя и пароль учетной записи для администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="8ae71-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="8ae71-113">В выпусках вплоть до версии 2.0 этот администратор должен быть глобальным администратором Office 365.</span><span class="sxs-lookup"><span data-stu-id="8ae71-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="8ae71-114">Облачный соединитель использует эту учетную запись для получения сведений о конфигурации, настройки параметров конфигурации и обновления состояния устройства в конфигурации клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="8ae71-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="8ae71-115">С выпуском 2,0 и более поздними версиями вы также можете использовать этот командлет, чтобы обновить пароли для учетных записей Вмадмин и Домаинадмин.</span><span class="sxs-lookup"><span data-stu-id="8ae71-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="8ae71-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ae71-116">Parameters</span></span>
<span data-ttu-id="8ae71-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8ae71-117"></span></span>

|<span data-ttu-id="8ae71-118">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="8ae71-118">**Parameter**</span></span>|<span data-ttu-id="8ae71-119">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="8ae71-119">**Required**</span></span>|<span data-ttu-id="8ae71-120">**Тип**</span><span class="sxs-lookup"><span data-stu-id="8ae71-120">**Type**</span></span>|<span data-ttu-id="8ae71-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8ae71-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8ae71-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="8ae71-122">AccountType</span></span> <br/> | <span data-ttu-id="8ae71-123">Обязательный</span><span class="sxs-lookup"><span data-stu-id="8ae71-123">Required</span></span> <br/> |<span data-ttu-id="8ae71-124">System.String</span><span class="sxs-lookup"><span data-stu-id="8ae71-124">System.String</span></span>  <br/> | <span data-ttu-id="8ae71-125"> Параметр должен иметь значение "TenantAdmin", "VmAdmin" или "DomainAdmin".</span><span class="sxs-lookup"><span data-stu-id="8ae71-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="8ae71-126">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="8ae71-126">Input Types</span></span>
<span data-ttu-id="8ae71-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8ae71-127"></span></span>

<span data-ttu-id="8ae71-p102">Отсутствуют. Командлет Set-CcCredential не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="8ae71-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8ae71-130">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="8ae71-130">Return Types</span></span>
<span data-ttu-id="8ae71-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8ae71-131"></span></span>

<span data-ttu-id="8ae71-132">Нет</span><span class="sxs-lookup"><span data-stu-id="8ae71-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8ae71-133">См. также</span><span class="sxs-lookup"><span data-stu-id="8ae71-133">See also</span></span>
<span data-ttu-id="8ae71-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8ae71-134"></span></span>

[<span data-ttu-id="8ae71-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="8ae71-135">Get-CcCredential</span></span>](get-cccredential.md)
  

