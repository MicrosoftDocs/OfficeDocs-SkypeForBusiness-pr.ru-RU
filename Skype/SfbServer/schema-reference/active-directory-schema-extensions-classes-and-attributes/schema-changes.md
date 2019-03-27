---
title: Изменения схемы в Скайп для Business Server
ms.reviewer: ''
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
ms.openlocfilehash: ba76f57197e9cd812163c8abac5f51005933eace
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874642"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="fed86-104">Изменения схемы в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="fed86-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="fed86-105">Прежде чем развертывать и использование Скайп для Business Server, необходимо подготовить доменных служб Active Directory путем расширения схемы.</span><span class="sxs-lookup"><span data-stu-id="fed86-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="fed86-106">Расширения схемы добавьте классы и атрибуты, которые необходимы Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="fed86-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="fed86-107">При обновлении с Lync Server 2013 для Скайп для Business Server 2015, не изменяются схемы и поэтому эта статья не применяется.</span><span class="sxs-lookup"><span data-stu-id="fed86-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="fed86-108">Скайп для Business Server требуется несколько новых классов и атрибутов и изменяет некоторые существующие классы и атрибуты.</span><span class="sxs-lookup"><span data-stu-id="fed86-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="fed86-109">Кроме того объем сведений о конфигурации Скайп для Business Server хранится в центрального хранилища управления вместо в Доменные службы Active Directory как в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="fed86-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="fed86-110">Следующие сведения по-прежнему хранятся в Доменных службах Active Directory в Скайп для Business Server:</span><span class="sxs-lookup"><span data-stu-id="fed86-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="fed86-111">**Расширения схемы**:</span><span class="sxs-lookup"><span data-stu-id="fed86-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="fed86-112">Расширения объекта пользователя</span><span class="sxs-lookup"><span data-stu-id="fed86-112">User object extensions</span></span>
    
  - <span data-ttu-id="fed86-113">Расширения для классов для обеспечения обратной совместимости с предыдущими версиями сервера Lync.</span><span class="sxs-lookup"><span data-stu-id="fed86-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="fed86-114">**Данные** (хранятся в Скайп для расширенной схеме Business Server и существующей схеме классов):</span><span class="sxs-lookup"><span data-stu-id="fed86-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="fed86-115">Пользователь SIP универсальный код ресурса (URI) и другие параметры пользователей</span><span class="sxs-lookup"><span data-stu-id="fed86-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="fed86-116">Контактные объекты для приложений, таких как группа ответа и помощник по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="fed86-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="fed86-117">Указатель на центральном хранилище управления</span><span class="sxs-lookup"><span data-stu-id="fed86-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="fed86-118">Учетная запись проверки подлинности Kerberos (дополнительный объект-компьютер)</span><span class="sxs-lookup"><span data-stu-id="fed86-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="fed86-119">В этом разделе описываются изменения схемы Active Directory, необходимые для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="fed86-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="fed86-120">Изменения схемы, которые были представлены в предыдущих версиях Office Communications Server не приведены.</span><span class="sxs-lookup"><span data-stu-id="fed86-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="fed86-121">Список классов и их описания в разделе [классы схемы и описания в Скайп для Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="fed86-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="fed86-122">Список атрибутов и их описания в разделе [атрибуты схемы и описания в Скайп для Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="fed86-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="fed86-123">Список классов с атрибутами они могут содержать см [атрибуты схемы по классам в Скайп для Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="fed86-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="fed86-124">Префикс msRTCSIP идентифицирует классы и атрибуты, относящиеся к Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="fed86-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="fed86-125">Новые атрибуты Active Directory</span><span class="sxs-lookup"><span data-stu-id="fed86-125">New Active Directory Attributes</span></span>

<span data-ttu-id="fed86-126">В следующей таблице описываются атрибуты Active Directory, добавленные Скайп Business Server.</span><span class="sxs-lookup"><span data-stu-id="fed86-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="fed86-127">**Атрибуты, добавленные Скайп для Business Server**</span><span class="sxs-lookup"><span data-stu-id="fed86-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="fed86-128">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="fed86-128">**Attribute**</span></span>|<span data-ttu-id="fed86-129">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="fed86-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fed86-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="fed86-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="fed86-131">Этот атрибут со множеством значений содержит идентификаторы для хранения политик, которые применяются к пользователю.</span><span class="sxs-lookup"><span data-stu-id="fed86-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="fed86-132">Удержаний политик сохраняются элементы почтовых ящиков для пользователя во время выполнения удержания.</span><span class="sxs-lookup"><span data-stu-id="fed86-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="fed86-133">Этот атрибут используется совместно с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="fed86-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="fed86-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="fed86-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="fed86-135">Это SIP, маршрутизация идентификатор группы.</span><span class="sxs-lookup"><span data-stu-id="fed86-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="fed86-136">Пользователи в той же группе будет регистрировать на тот же сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="fed86-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="fed86-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="fed86-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="fed86-138">Этот атрибут используется для хранения зеркальных внутреннего сервера SQL Server, используемая пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="fed86-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="fed86-139">Измененные классы Active Directory</span><span class="sxs-lookup"><span data-stu-id="fed86-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="fed86-140">В следующей таблице описываются классы Active Directory, изменяемые Скайп Business Server.</span><span class="sxs-lookup"><span data-stu-id="fed86-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="fed86-141">**Классы, изменяемые Скайп для Business Server**</span><span class="sxs-lookup"><span data-stu-id="fed86-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="fed86-142">**Класс**</span><span class="sxs-lookup"><span data-stu-id="fed86-142">**Class**</span></span>|<span data-ttu-id="fed86-143">**Изменение**</span><span class="sxs-lookup"><span data-stu-id="fed86-143">**Change**</span></span>|<span data-ttu-id="fed86-144">**Класс или атрибут**</span><span class="sxs-lookup"><span data-stu-id="fed86-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fed86-145">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fed86-145">User</span></span>  <br/> |<span data-ttu-id="fed86-146">Добавление: mayContain</span><span class="sxs-lookup"><span data-stu-id="fed86-146">add: mayContain</span></span>  <br/> <span data-ttu-id="fed86-147">Добавление: mayContain</span><span class="sxs-lookup"><span data-stu-id="fed86-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="fed86-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="fed86-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="fed86-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="fed86-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="fed86-150">Контакт</span><span class="sxs-lookup"><span data-stu-id="fed86-150">Contact</span></span>  <br/> |<span data-ttu-id="fed86-151">Добавление: mayContain</span><span class="sxs-lookup"><span data-stu-id="fed86-151">add: mayContain</span></span>  <br/> <span data-ttu-id="fed86-152">Добавление: mayContain</span><span class="sxs-lookup"><span data-stu-id="fed86-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="fed86-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="fed86-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="fed86-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="fed86-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="fed86-155">Получатель почты</span><span class="sxs-lookup"><span data-stu-id="fed86-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="fed86-156">Добавление: mayContain</span><span class="sxs-lookup"><span data-stu-id="fed86-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="fed86-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="fed86-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="fed86-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="fed86-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="fed86-159">Добавление: mayContain</span><span class="sxs-lookup"><span data-stu-id="fed86-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="fed86-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="fed86-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

