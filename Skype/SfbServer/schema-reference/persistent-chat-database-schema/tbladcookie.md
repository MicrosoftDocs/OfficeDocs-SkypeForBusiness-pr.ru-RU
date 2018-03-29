---
title: tblADCookie
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie содержит текущий файлы cookie синхронизации Lightweight Directory Access Protocol (LDAP).
ms.openlocfilehash: bc2c0657caa66a0420bc493bf4b688a2a081db36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tbladcookie"></a><span data-ttu-id="c11e7-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="c11e7-103">tblADCookie</span></span>
 
<span data-ttu-id="c11e7-104">tblADCookie содержит текущий файлы cookie синхронизации Lightweight Directory Access Protocol (LDAP).</span><span class="sxs-lookup"><span data-stu-id="c11e7-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="c11e7-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="c11e7-105">**Columns**</span></span>

|<span data-ttu-id="c11e7-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c11e7-106">**Column**</span></span>|<span data-ttu-id="c11e7-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c11e7-107">**Type**</span></span>|<span data-ttu-id="c11e7-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c11e7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c11e7-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c11e7-109">prinGuid</span></span>  <br/> |<span data-ttu-id="c11e7-110">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="c11e7-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="c11e7-111">GUID субъекта домена, за которым ведется наблюдение.</span><span class="sxs-lookup"><span data-stu-id="c11e7-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="c11e7-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="c11e7-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="c11e7-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="c11e7-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="c11e7-114">Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации службы домена Active Directory. Информационные значение равно.</span><span class="sxs-lookup"><span data-stu-id="c11e7-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="c11e7-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="c11e7-115">adcContent</span></span>  <br/> |<span data-ttu-id="c11e7-116">изображение (двоичный)</span><span class="sxs-lookup"><span data-stu-id="c11e7-116">image (binary)</span></span>  <br/> |<span data-ttu-id="c11e7-117">Файл cookie Active Directory синхронизации.</span><span class="sxs-lookup"><span data-stu-id="c11e7-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="c11e7-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="c11e7-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="c11e7-119">datetime</span><span class="sxs-lookup"><span data-stu-id="c11e7-119">datetime</span></span>  <br/> |<span data-ttu-id="c11e7-120">Метка времени со временем обновления строки.</span><span class="sxs-lookup"><span data-stu-id="c11e7-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="c11e7-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="c11e7-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="c11e7-122">datetime</span><span class="sxs-lookup"><span data-stu-id="c11e7-122">datetime</span></span>  <br/> |<span data-ttu-id="c11e7-123">Время, пока не заблокирован строку для изменения.</span><span class="sxs-lookup"><span data-stu-id="c11e7-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="c11e7-124">Это часть механизм блокировка программного обеспечения, чтобы гарантировать, что только один из службы чата не синхронизации Active Directory за раз.</span><span class="sxs-lookup"><span data-stu-id="c11e7-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="c11e7-125">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="c11e7-125">**Keys**</span></span>

|<span data-ttu-id="c11e7-126">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="c11e7-126">**Column(s)**</span></span>|<span data-ttu-id="c11e7-127">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c11e7-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c11e7-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c11e7-128">prinGuid</span></span>  <br/> |<span data-ttu-id="c11e7-129">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="c11e7-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c11e7-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c11e7-130">prinGuid</span></span>  <br/> |<span data-ttu-id="c11e7-131">Внешний ключ с поиском в таблице Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="c11e7-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

