---
title: tblADCookie
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie содержит текущие файлы cookie синхронизации для протокола LDAP.
ms.openlocfilehash: 78a477399da811e674bb5a4493e61100acdd4782
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814759"
---
# <a name="tbladcookie"></a><span data-ttu-id="3e8a7-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="3e8a7-103">tblADCookie</span></span>
 
<span data-ttu-id="3e8a7-104">tblADCookie содержит текущие файлы cookie синхронизации для протокола LDAP.</span><span class="sxs-lookup"><span data-stu-id="3e8a7-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="3e8a7-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="3e8a7-105">**Columns**</span></span>

|<span data-ttu-id="3e8a7-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="3e8a7-106">**Column**</span></span>|<span data-ttu-id="3e8a7-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="3e8a7-107">**Type**</span></span>|<span data-ttu-id="3e8a7-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3e8a7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3e8a7-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3e8a7-109">prinGuid</span></span>  <br/> |<span data-ttu-id="3e8a7-110">GUID, не NULL</span><span class="sxs-lookup"><span data-stu-id="3e8a7-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="3e8a7-111">GUID субъекта для домена, за которым осуществляется мониторинг.</span><span class="sxs-lookup"><span data-stu-id="3e8a7-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="3e8a7-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="3e8a7-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="3e8a7-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="3e8a7-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="3e8a7-114">Полное доменное имя текущего контроллера домена, используемого для синхронизации доменных служб Active Directory. Имеет информационное значение.</span><span class="sxs-lookup"><span data-stu-id="3e8a7-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="3e8a7-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="3e8a7-115">adcContent</span></span>  <br/> |<span data-ttu-id="3e8a7-116">image (binary)</span><span class="sxs-lookup"><span data-stu-id="3e8a7-116">image (binary)</span></span>  <br/> |<span data-ttu-id="3e8a7-117">Файл cookie синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3e8a7-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="3e8a7-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="3e8a7-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="3e8a7-119">datetime</span><span class="sxs-lookup"><span data-stu-id="3e8a7-119">datetime</span></span>  <br/> |<span data-ttu-id="3e8a7-120">Метка времени со временем обновления строки.</span><span class="sxs-lookup"><span data-stu-id="3e8a7-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="3e8a7-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="3e8a7-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="3e8a7-122">datetime</span><span class="sxs-lookup"><span data-stu-id="3e8a7-122">datetime</span></span>  <br/> |<span data-ttu-id="3e8a7-p101">время, до которого строка заблокирована для внесения изменений. Это часть механизма программной блокировки, которая обеспечивает одновременное выполнение синхронизации Active Directory только одной службой чата.</span><span class="sxs-lookup"><span data-stu-id="3e8a7-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="3e8a7-125">**Keys**</span><span class="sxs-lookup"><span data-stu-id="3e8a7-125">**Keys**</span></span>

|<span data-ttu-id="3e8a7-126">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="3e8a7-126">**Column(s)**</span></span>|<span data-ttu-id="3e8a7-127">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3e8a7-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3e8a7-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3e8a7-128">prinGuid</span></span>  <br/> |<span data-ttu-id="3e8a7-129">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="3e8a7-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3e8a7-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3e8a7-130">prinGuid</span></span>  <br/> |<span data-ttu-id="3e8a7-131">Внешний ключ с поиском в таблице Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="3e8a7-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

