---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie содержит текущий файлы cookie синхронизации Lightweight Directory Access Protocol (LDAP).
ms.openlocfilehash: d990d02e73be9a4d6178037a314e36add448ad40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929947"
---
# <a name="tbladcookie"></a><span data-ttu-id="0b130-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="0b130-103">tblADCookie</span></span>
 
<span data-ttu-id="0b130-104">tblADCookie содержит текущий файлы cookie синхронизации Lightweight Directory Access Protocol (LDAP).</span><span class="sxs-lookup"><span data-stu-id="0b130-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="0b130-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="0b130-105">**Columns**</span></span>

|<span data-ttu-id="0b130-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0b130-106">**Column**</span></span>|<span data-ttu-id="0b130-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0b130-107">**Type**</span></span>|<span data-ttu-id="0b130-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0b130-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0b130-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="0b130-109">prinGuid</span></span>  <br/> |<span data-ttu-id="0b130-110">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="0b130-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="0b130-111">GUID субъекта домена, за которым ведется наблюдение.</span><span class="sxs-lookup"><span data-stu-id="0b130-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="0b130-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="0b130-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="0b130-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="0b130-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="0b130-114">Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации службы домена Active Directory. Информационные значение равно.</span><span class="sxs-lookup"><span data-stu-id="0b130-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="0b130-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="0b130-115">adcContent</span></span>  <br/> |<span data-ttu-id="0b130-116">изображение (двоичный)</span><span class="sxs-lookup"><span data-stu-id="0b130-116">image (binary)</span></span>  <br/> |<span data-ttu-id="0b130-117">Файл cookie Active Directory синхронизации.</span><span class="sxs-lookup"><span data-stu-id="0b130-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="0b130-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="0b130-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="0b130-119">datetime</span><span class="sxs-lookup"><span data-stu-id="0b130-119">datetime</span></span>  <br/> |<span data-ttu-id="0b130-120">Метка времени со временем обновления строки.</span><span class="sxs-lookup"><span data-stu-id="0b130-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="0b130-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="0b130-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="0b130-122">datetime</span><span class="sxs-lookup"><span data-stu-id="0b130-122">datetime</span></span>  <br/> |<span data-ttu-id="0b130-123">Время, пока не заблокирован строку для изменения.</span><span class="sxs-lookup"><span data-stu-id="0b130-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="0b130-124">Это часть механизм блокировка программного обеспечения, чтобы гарантировать, что только один из службы чата не синхронизации Active Directory за раз.</span><span class="sxs-lookup"><span data-stu-id="0b130-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="0b130-125">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="0b130-125">**Keys**</span></span>

|<span data-ttu-id="0b130-126">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="0b130-126">**Column(s)**</span></span>|<span data-ttu-id="0b130-127">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0b130-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b130-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="0b130-128">prinGuid</span></span>  <br/> |<span data-ttu-id="0b130-129">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="0b130-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0b130-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="0b130-130">prinGuid</span></span>  <br/> |<span data-ttu-id="0b130-131">Внешний ключ с поиском в таблице Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="0b130-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

