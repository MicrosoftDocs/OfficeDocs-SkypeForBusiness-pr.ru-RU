---
title: Изменения схемы в Скайп для Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Прежде чем развертывать и использование Скайп для Business Server, необходимо подготовить доменных служб Active Directory путем расширения схемы. Расширения схемы добавьте классы и атрибуты, которые необходимы Скайп для Business Server.
ms.openlocfilehash: 42b4417311c557323535aa03053ccb03d95cc840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="ea42a-104">Изменения схемы в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="ea42a-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="ea42a-105">Прежде чем развертывать и использование Скайп для Business Server, необходимо подготовить доменных служб Active Directory путем расширения схемы.</span><span class="sxs-lookup"><span data-stu-id="ea42a-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="ea42a-106">Расширения схемы добавьте классы и атрибуты, которые необходимы Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="ea42a-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span> 
  
<span data-ttu-id="ea42a-107">Скайп для Business Server требуется несколько новых классов и атрибутов и изменяет некоторые существующие классы и атрибуты.</span><span class="sxs-lookup"><span data-stu-id="ea42a-107">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="ea42a-108">Кроме того объем сведений о конфигурации Скайп для Business Server хранится в центрального хранилища управления вместо в Доменные службы Active Directory как в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="ea42a-108">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="ea42a-109">Следующие сведения по-прежнему хранятся в Доменных службах Active Directory в Скайп для Business Server:</span><span class="sxs-lookup"><span data-stu-id="ea42a-109">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="ea42a-110">**Расширения схемы**:</span><span class="sxs-lookup"><span data-stu-id="ea42a-110">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="ea42a-111">Расширения объекта пользователя</span><span class="sxs-lookup"><span data-stu-id="ea42a-111">User object extensions</span></span>
    
  - <span data-ttu-id="ea42a-112">Расширения для классов для обеспечения обратной совместимости с предыдущими версиями сервера Lync.</span><span class="sxs-lookup"><span data-stu-id="ea42a-112">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="ea42a-113">**Данные** (хранятся в Скайп для расширенной схеме Business Server и существующей схеме классов):</span><span class="sxs-lookup"><span data-stu-id="ea42a-113">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="ea42a-114">Пользователь SIP универсальный код ресурса (URI) и другие параметры пользователей</span><span class="sxs-lookup"><span data-stu-id="ea42a-114">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="ea42a-115">Контактные объекты для приложений, таких как группа ответа и помощник по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="ea42a-115">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="ea42a-116">Указатель на центральном хранилище управления</span><span class="sxs-lookup"><span data-stu-id="ea42a-116">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="ea42a-117">Учетная запись проверки подлинности Kerberos (дополнительный объект-компьютер)</span><span class="sxs-lookup"><span data-stu-id="ea42a-117">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="ea42a-118">В этом разделе описываются изменения схемы Active Directory, необходимые для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="ea42a-118">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="ea42a-119">Изменения схемы, которые были представлены в предыдущих версиях Office Communications Server не приведены.</span><span class="sxs-lookup"><span data-stu-id="ea42a-119">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="ea42a-120">Список классов и их описания в разделе [классы схемы и описания в Скайп для Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="ea42a-120">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="ea42a-121">Список атрибутов и их описания в разделе [атрибуты схемы и описания в Скайп для Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="ea42a-121">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="ea42a-122">Список классов с атрибутами они могут содержать см [атрибуты схемы по классам в Скайп для Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="ea42a-122">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="ea42a-123">Префикс msRTCSIP идентифицирует классы и атрибуты, относящиеся к Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="ea42a-123">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="ea42a-124">Новые атрибуты Active Directory</span><span class="sxs-lookup"><span data-stu-id="ea42a-124">New Active Directory Attributes</span></span>

<span data-ttu-id="ea42a-125">В следующей таблице описываются атрибуты Active Directory, добавленные Скайп Business Server.</span><span class="sxs-lookup"><span data-stu-id="ea42a-125">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="ea42a-126">**Атрибуты, добавленные Скайп для Business Server**</span><span class="sxs-lookup"><span data-stu-id="ea42a-126">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="ea42a-127">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="ea42a-127">**Attribute**</span></span>|<span data-ttu-id="ea42a-128">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ea42a-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ea42a-129">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="ea42a-129">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="ea42a-130">Этот атрибут со множеством значений содержит идентификаторы для хранения политик, которые применяются к пользователю.</span><span class="sxs-lookup"><span data-stu-id="ea42a-130">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="ea42a-131">Удержаний политик сохраняются элементы почтовых ящиков для пользователя во время выполнения удержания.</span><span class="sxs-lookup"><span data-stu-id="ea42a-131">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="ea42a-132">Этот атрибут используется совместно с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ea42a-132">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="ea42a-133">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="ea42a-133">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="ea42a-134">Это SIP, маршрутизация идентификатор группы.</span><span class="sxs-lookup"><span data-stu-id="ea42a-134">This is the SIP routing group ID.</span></span> <span data-ttu-id="ea42a-135">Пользователи в той же группе будет регистрировать на тот же сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ea42a-135">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="ea42a-136">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="ea42a-136">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="ea42a-137">Этот атрибут используется для хранения зеркальных внутреннего сервера SQL Server, используемая пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ea42a-137">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="ea42a-138">Измененные классы Active Directory</span><span class="sxs-lookup"><span data-stu-id="ea42a-138">Modified Active Directory Classes</span></span>

<span data-ttu-id="ea42a-139">В следующей таблице описываются классы Active Directory, изменяемые Скайп Business Server.</span><span class="sxs-lookup"><span data-stu-id="ea42a-139">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="ea42a-140">**Классы, изменяемые Скайп для Business Server**</span><span class="sxs-lookup"><span data-stu-id="ea42a-140">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="ea42a-141">**Класс**</span><span class="sxs-lookup"><span data-stu-id="ea42a-141">**Class**</span></span>|<span data-ttu-id="ea42a-142">**Изменения**</span><span class="sxs-lookup"><span data-stu-id="ea42a-142">**Change**</span></span>|<span data-ttu-id="ea42a-143">**Класс или атрибут**</span><span class="sxs-lookup"><span data-stu-id="ea42a-143">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea42a-144">Пользователь</span><span class="sxs-lookup"><span data-stu-id="ea42a-144">User</span></span>  <br/> |<span data-ttu-id="ea42a-145">Добавление: mayContain</span><span class="sxs-lookup"><span data-stu-id="ea42a-145">add: mayContain</span></span>  <br/> <span data-ttu-id="ea42a-146">Добавление: mayContain</span><span class="sxs-lookup"><span data-stu-id="ea42a-146">add: mayContain</span></span>  <br/> |<span data-ttu-id="ea42a-147">ProxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="ea42a-147">ProxyAddresses</span></span>  <br/> <span data-ttu-id="ea42a-148">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="ea42a-148">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="ea42a-149">Контакт</span><span class="sxs-lookup"><span data-stu-id="ea42a-149">Contact</span></span>  <br/> |<span data-ttu-id="ea42a-150">Добавление: mayContain</span><span class="sxs-lookup"><span data-stu-id="ea42a-150">add: mayContain</span></span>  <br/> <span data-ttu-id="ea42a-151">Добавление: mayContain</span><span class="sxs-lookup"><span data-stu-id="ea42a-151">add: mayContain</span></span>  <br/> |<span data-ttu-id="ea42a-152">ProxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="ea42a-152">ProxyAddresses</span></span>  <br/> <span data-ttu-id="ea42a-153">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="ea42a-153">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="ea42a-154">Получатель почты</span><span class="sxs-lookup"><span data-stu-id="ea42a-154">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="ea42a-155">Добавление: mayContain</span><span class="sxs-lookup"><span data-stu-id="ea42a-155">add: mayContain</span></span>  <br/> |<span data-ttu-id="ea42a-156">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="ea42a-156">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="ea42a-157">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="ea42a-157">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="ea42a-158">Добавление: mayContain</span><span class="sxs-lookup"><span data-stu-id="ea42a-158">add: mayContain</span></span>  <br/> |<span data-ttu-id="ea42a-159">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="ea42a-159">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

