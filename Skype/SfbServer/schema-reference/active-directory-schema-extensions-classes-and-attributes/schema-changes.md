---
title: Изменения схемы в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Перед развертыванием и эксплуатацией Skype для бизнеса Server необходимо подготовить доменные службы Active Directory путем расширения схемы. Расширения схемы добавляют классы и атрибуты, необходимые Skype для бизнеса Server.
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813579"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="348ad-104">Изменения схемы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="348ad-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="348ad-105">Перед развертыванием и эксплуатацией Skype для бизнеса Server необходимо подготовить доменные службы Active Directory путем расширения схемы.</span><span class="sxs-lookup"><span data-stu-id="348ad-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="348ad-106">Расширения схемы добавляют классы и атрибуты, необходимые Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="348ad-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="348ad-107">При обновлении Lync Server 2013 до Skype для бизнеса Server 2015 изменения схемы не вносяся, поэтому эта статья не применяется.</span><span class="sxs-lookup"><span data-stu-id="348ad-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="348ad-108">Skype для бизнеса Server требует нескольких новых классов и атрибутов и изменяет некоторые существующие классы и атрибуты.</span><span class="sxs-lookup"><span data-stu-id="348ad-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="348ad-109">Кроме того, большая часть сведений о конфигурации Skype для бизнеса Server хранится в центральном хранилище управления, а не в AD DS, как в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="348ad-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="348ad-110">Следующие сведения по-прежнему хранятся в AD DS в Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="348ad-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="348ad-111">**Расширения схемы**:</span><span class="sxs-lookup"><span data-stu-id="348ad-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="348ad-112">расширения объектов-пользователей;</span><span class="sxs-lookup"><span data-stu-id="348ad-112">User object extensions</span></span>
    
  - <span data-ttu-id="348ad-113">Расширения для классов для обеспечения обратной совместимости с поддерживаемыми предыдущими версиями Lync Server.</span><span class="sxs-lookup"><span data-stu-id="348ad-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="348ad-114">**Данные** (хранимые в расширенной схеме Skype для бизнеса Server и в существующих классах схемы):</span><span class="sxs-lookup"><span data-stu-id="348ad-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="348ad-115">универсальный код ресурса (URI) SIP и другие параметры пользователя;</span><span class="sxs-lookup"><span data-stu-id="348ad-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="348ad-116">контактные объекты для приложений, такие как группа ответа и помощник по конференц-связи;</span><span class="sxs-lookup"><span data-stu-id="348ad-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="348ad-117">Указатель на центральное хранилище управления</span><span class="sxs-lookup"><span data-stu-id="348ad-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="348ad-118">Учетная запись для проверки подлинности Kerberos (необязательный объект-компьютер)</span><span class="sxs-lookup"><span data-stu-id="348ad-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="348ad-119">В этом разделе описываются изменения схемы Active Directory, необходимые для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="348ad-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="348ad-120">В нем не описываются изменения схемы, которые были представлены в предыдущих версиях Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="348ad-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="348ad-121">Список классов и их описания см. в описании и классах схемы [в Skype для бизнеса Server.](schema-classes-and-descriptions.md)</span><span class="sxs-lookup"><span data-stu-id="348ad-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="348ad-122">Список атрибутов и их описания см. в описании и атрибутах схемы [в Skype для бизнеса Server.](schema-attributes-and-descriptions.md)</span><span class="sxs-lookup"><span data-stu-id="348ad-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="348ad-123">Список классов с атрибутами, которые они могут содержать, см. в атрибутах [схемы по классам в Skype для бизнеса Server.](schema-attributes-by-class.md)</span><span class="sxs-lookup"><span data-stu-id="348ad-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="348ad-124">Префикс msRTCSIP определяет классы и атрибуты, специфические для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="348ad-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="348ad-125">Новые атрибуты Active Directory</span><span class="sxs-lookup"><span data-stu-id="348ad-125">New Active Directory Attributes</span></span>

<span data-ttu-id="348ad-126">В следующей таблице описываются атрибуты Active Directory, добавленные Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="348ad-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="348ad-127">**Атрибуты, добавленные в Skype для бизнеса Server**</span><span class="sxs-lookup"><span data-stu-id="348ad-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="348ad-128">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="348ad-128">**Attribute**</span></span>|<span data-ttu-id="348ad-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="348ad-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="348ad-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="348ad-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="348ad-131">Этот атрибут, поддерживающий несколько значений, содержит идентификаторы политик хранения, которые применяются к пользователю.</span><span class="sxs-lookup"><span data-stu-id="348ad-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="348ad-132">Политики хранения определяют срок хранения элементов почтового ящика для пользователя.</span><span class="sxs-lookup"><span data-stu-id="348ad-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="348ad-133">Этот атрибут является общим для Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="348ad-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="348ad-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="348ad-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="348ad-p106">Это ИД группы маршрутизации SIP. Пользователи в одной группе будут регистрироваться в одном сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="348ad-p106">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="348ad-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="348ad-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="348ad-138">Этот атрибут используется для хранения зеркального SQL Server, используемого пулом переднего входа.</span><span class="sxs-lookup"><span data-stu-id="348ad-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="348ad-139">Измененные классы Active Directory</span><span class="sxs-lookup"><span data-stu-id="348ad-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="348ad-140">В следующей таблице описаны классы Active Directory, измененные в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="348ad-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="348ad-141">**Классы, измененные в Skype для бизнеса Server**</span><span class="sxs-lookup"><span data-stu-id="348ad-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="348ad-142">**Class**</span><span class="sxs-lookup"><span data-stu-id="348ad-142">**Class**</span></span>|<span data-ttu-id="348ad-143">**Изменение**</span><span class="sxs-lookup"><span data-stu-id="348ad-143">**Change**</span></span>|<span data-ttu-id="348ad-144">**Класс или атрибут**</span><span class="sxs-lookup"><span data-stu-id="348ad-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="348ad-145">Пользователь</span><span class="sxs-lookup"><span data-stu-id="348ad-145">User</span></span>  <br/> |<span data-ttu-id="348ad-146">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="348ad-146">add: mayContain</span></span>  <br/> <span data-ttu-id="348ad-147">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="348ad-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="348ad-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="348ad-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="348ad-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="348ad-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="348ad-150">Контакт</span><span class="sxs-lookup"><span data-stu-id="348ad-150">Contact</span></span>  <br/> |<span data-ttu-id="348ad-151">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="348ad-151">add: mayContain</span></span>  <br/> <span data-ttu-id="348ad-152">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="348ad-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="348ad-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="348ad-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="348ad-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="348ad-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="348ad-155">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="348ad-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="348ad-156">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="348ad-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="348ad-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="348ad-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="348ad-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="348ad-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="348ad-159">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="348ad-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="348ad-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="348ad-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

