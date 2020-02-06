---
title: Изменения схемы в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Перед развертыванием и эксплуатацией Skype для бизнеса Server необходимо подготовить доменные службы Active Directory, расширив схему. Расширения схемы добавляют классы и атрибуты, необходимые для работы Skype для бизнеса Server.
ms.openlocfilehash: 0c3765fe36b252cc03218a3fa4365c5cc36c7f48
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815487"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="54856-104">Изменения схемы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="54856-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="54856-105">Перед развертыванием и эксплуатацией Skype для бизнеса Server необходимо подготовить доменные службы Active Directory, расширив схему.</span><span class="sxs-lookup"><span data-stu-id="54856-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="54856-106">Расширения схемы добавляют классы и атрибуты, необходимые для работы Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="54856-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="54856-107">Если вы обновляете приложение Lync Server 2013 на Skype для бизнеса Server 2015, изменения схемы не вносятся, поэтому эта статья не применяется.</span><span class="sxs-lookup"><span data-stu-id="54856-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="54856-108">В Skype для бизнеса Server требуется несколько новых классов и атрибутов, а некоторые существующие классы и атрибуты изменяются.</span><span class="sxs-lookup"><span data-stu-id="54856-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="54856-109">Кроме того, многие сведения о настройке Skype для бизнеса Server хранятся в главном хранилище управления, а не в службах AD DS, как в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="54856-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="54856-110">Следующая информация сохраняется в службах AD DS в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="54856-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="54856-111">**Расширения схемы**.</span><span class="sxs-lookup"><span data-stu-id="54856-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="54856-112">Расширения объекта пользователя</span><span class="sxs-lookup"><span data-stu-id="54856-112">User object extensions</span></span>
    
  - <span data-ttu-id="54856-113">Расширения для классов для обеспечения обратной совместимости с более ранними версиями Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54856-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="54856-114">**Данные** (хранящиеся в расширенной схеме и в существующих классах схемы Skype для бизнеса Server):</span><span class="sxs-lookup"><span data-stu-id="54856-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="54856-115">Универсальный код ресурса (URI) пользователя SIP и другие пользовательские параметры</span><span class="sxs-lookup"><span data-stu-id="54856-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="54856-116">Объекты контактов для таких приложений, как группа ответа и конференц-связь</span><span class="sxs-lookup"><span data-stu-id="54856-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="54856-117">Указатель на хранилище Центрального управления</span><span class="sxs-lookup"><span data-stu-id="54856-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="54856-118">Учетная запись для проверки подлинности Kerberos (необязательный объект-компьютер)</span><span class="sxs-lookup"><span data-stu-id="54856-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="54856-119">В этой статье описаны изменения схемы Active Directory, необходимые для сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="54856-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="54856-120">В нем не описаны изменения схемы, которые появились в предыдущих версиях Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="54856-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="54856-121">Список классов и их описаний можно найти в разделе [классы и описания схемы в Skype для бизнеса Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="54856-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="54856-122">Список атрибутов и их описание можно найти [в разделе атрибуты и описания схемы в Skype для бизнеса Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="54856-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="54856-123">Список классов с атрибутами, которые они могут содержать, приведены [в разделе атрибуты схемы по классам в Skype для бизнеса Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="54856-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="54856-124">Префикс msRTCSIP определяет классы и атрибуты, специфичные для сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="54856-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="54856-125">Новые атрибуты Active Directory</span><span class="sxs-lookup"><span data-stu-id="54856-125">New Active Directory Attributes</span></span>

<span data-ttu-id="54856-126">В таблице ниже описаны атрибуты Active Directory, добавленные в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="54856-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="54856-127">**Атрибуты, добавленные в Skype для бизнеса Server**</span><span class="sxs-lookup"><span data-stu-id="54856-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="54856-128">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="54856-128">**Attribute**</span></span>|<span data-ttu-id="54856-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="54856-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="54856-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="54856-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="54856-131">Этот атрибут с несколькими значениями содержит идентификаторы для политик хранения, которые применяются к пользователю.</span><span class="sxs-lookup"><span data-stu-id="54856-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="54856-132">Политики удержания сохраняют для пользователя элементы почтового ящика на время удержания.</span><span class="sxs-lookup"><span data-stu-id="54856-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="54856-133">Этот атрибут является общим для Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="54856-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="54856-134">msRTCSIP-Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="54856-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="54856-135">Это идентификатор группы маршрутизации SIP.</span><span class="sxs-lookup"><span data-stu-id="54856-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="54856-136">Пользователи в одной группе будут регистрироваться на одном и том же внешнем сервере.</span><span class="sxs-lookup"><span data-stu-id="54856-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="54856-137">msRTCSIP-Миррорбаккендсервер</span><span class="sxs-lookup"><span data-stu-id="54856-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="54856-138">Этот атрибут используется для хранения зеркальной серверной части SQL Server, используемой в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="54856-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="54856-139">Измененные классы Active Directory</span><span class="sxs-lookup"><span data-stu-id="54856-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="54856-140">В таблице ниже описаны классы Active Directory, измененные в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="54856-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="54856-141">**Классы, измененные в Skype для бизнеса Server**</span><span class="sxs-lookup"><span data-stu-id="54856-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="54856-142">**Классов**</span><span class="sxs-lookup"><span data-stu-id="54856-142">**Class**</span></span>|<span data-ttu-id="54856-143">**Изменение**</span><span class="sxs-lookup"><span data-stu-id="54856-143">**Change**</span></span>|<span data-ttu-id="54856-144">**Класс или атрибут**</span><span class="sxs-lookup"><span data-stu-id="54856-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="54856-145">Пользователь</span><span class="sxs-lookup"><span data-stu-id="54856-145">User</span></span>  <br/> |<span data-ttu-id="54856-146">Add (Добавить): Майконтаин</span><span class="sxs-lookup"><span data-stu-id="54856-146">add: mayContain</span></span>  <br/> <span data-ttu-id="54856-147">Add (Добавить): Майконтаин</span><span class="sxs-lookup"><span data-stu-id="54856-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="54856-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="54856-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="54856-149">msRTCSIP-Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="54856-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="54856-150">Службу</span><span class="sxs-lookup"><span data-stu-id="54856-150">Contact</span></span>  <br/> |<span data-ttu-id="54856-151">Add (Добавить): Майконтаин</span><span class="sxs-lookup"><span data-stu-id="54856-151">add: mayContain</span></span>  <br/> <span data-ttu-id="54856-152">Add (Добавить): Майконтаин</span><span class="sxs-lookup"><span data-stu-id="54856-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="54856-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="54856-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="54856-154">msRTCSIP-Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="54856-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="54856-155">Почта-получатель</span><span class="sxs-lookup"><span data-stu-id="54856-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="54856-156">Add (Добавить): Майконтаин</span><span class="sxs-lookup"><span data-stu-id="54856-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="54856-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="54856-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="54856-158">msRTCSIP-Глобалтопологисеттинг</span><span class="sxs-lookup"><span data-stu-id="54856-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="54856-159">Add (Добавить): Майконтаин</span><span class="sxs-lookup"><span data-stu-id="54856-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="54856-160">msRTCSIP-Миррорбаккендсервер</span><span class="sxs-lookup"><span data-stu-id="54856-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

