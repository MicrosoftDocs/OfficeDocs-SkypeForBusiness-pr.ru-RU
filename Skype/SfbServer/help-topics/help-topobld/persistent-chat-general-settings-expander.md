---
title: Расширитель общих настроек сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: Вы можете изменить общие параметры сервера сохраняемого чата или пула серверов сохраняемого чата, настроив или определив указанные ниже свойства.
ms.openlocfilehash: c79ef61e2b7609aa344766c37cf38adaa195f23d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289975"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="7fc2d-103">Расширитель общих настроек сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="7fc2d-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="7fc2d-104">Вы можете изменить **Общие** параметры сервера сохраняемого чата или пула серверов сохраняемого чата, настроив или определив указанные ниже свойства.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="7fc2d-105">**Общие**</span><span class="sxs-lookup"><span data-stu-id="7fc2d-105">**General**</span></span>
  
- <span data-ttu-id="7fc2d-106">**FQDN**: измените этот параметр, чтобы определить полное доменное имя сервера сохраняемого чата или сохраняемого пула серверов чата.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="7fc2d-107">**Отображаемое имя пула для постоянного чата**: определите этот параметр, чтобы предоставить пользователю понятные и пользовательские параметры для сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="7fc2d-108">Этот параметр упрощает для пользователей связывание указанного сервера или пула для постоянного чата на основе отображаемого имени, а не более сложного представления полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="7fc2d-109">**Порт сохраняемых чатов**. Порт, предназначенный для сохраняемых чатов.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="7fc2d-110">Вы можете изменить \*\*\*\* параметры ассоциаций для сервера сохраняемого чата или пула серверов сохраняемого чата, настроив или определив следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="7fc2d-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="7fc2d-111">**Связи**</span><span class="sxs-lookup"><span data-stu-id="7fc2d-111">**Associations**</span></span>
  
- <span data-ttu-id="7fc2d-112">**Хранилище SQL Server**. Выберите в списке хранилище SQL Server и при необходимости именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="7fc2d-113">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7fc2d-114">Установите флажок **включить зеркальное отображение хранилища SQL Server** , если вы хотите включить зеркальное отображение для основного хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="7fc2d-115">Если вы решили включить зеркальное отображение хранилища SQL Server, выберите магазин и экземпляр из **хранилища SQL**Server в зеркальном отображении.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="7fc2d-116">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7fc2d-117">Установите флажок **использовать следящий сервер зеркального отображения SQL Server, чтобы включить автоматический переход на другой ресурс** , если требуется автоматически отработка отказа основного хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="7fc2d-118">Если вы решили включить следящий сервер хранилища SQL Server для включения автоматического перехода на другой ресурс, выберите магазин и экземпляр из списка.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="7fc2d-119">Для задания нового хранилища SQL Server (и экземпляра хранилища следящего сервера, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="7fc2d-120">Установите флажок **использовать архивацию хранилищ SQL Server для включения аварийного восстановления** , если вы хотите включить использование SQL Server с аварийным восстановлением</span><span class="sxs-lookup"><span data-stu-id="7fc2d-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="7fc2d-121">Разрешив аварийное восстановление, следует выбрать хранилище и экземпляр в списке **Резервное хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="7fc2d-122">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7fc2d-123">Установите флажок **включить зеркальное отображение хранилища SQL Server** , если вы хотите включить зеркальное отображение резервного хранилища SQL Server Mirroring.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="7fc2d-124">Если вы решили включить резервное копирование хранилища в хранилище SQL Server, выберите магазин и экземпляр из резервной **копии хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="7fc2d-125">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7fc2d-126">Установите флажок **использовать следящий сервер зеркального отображения SQL Server, чтобы включить автоматический переход на другой ресурс** , если требуется автоматический переход резервного хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="7fc2d-127">Если вы решили включить следящий сервер хранилища SQL Server для включения автоматического перехода на другой ресурс, выберите магазин и экземпляр из списка.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="7fc2d-128">Для задания нового хранилища SQL Server (и экземпляра хранилища следящего сервера, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="7fc2d-129">Если требуется доступ к базе данных соответствия, установите флажок **Включить соответствие**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="7fc2d-130">Разрешив доступ к базе данных соответствия, следует выбрать хранилище и экземпляр в списке **Совместимое хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="7fc2d-131">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7fc2d-132">Установите флажок **включить зеркальное отображение хранилища SQL Server** , если вы хотите включить зеркальное отображение для хранилища SQL Server соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="7fc2d-133">Если вы решили включить зеркальное отображение хранилища SQL Server, выберите магазин и экземпляр из списка **соответствие требованиям зеркальной копии хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="7fc2d-134">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7fc2d-135">Установите флажок **использовать следящий сервер зеркального отображения SQL Server, чтобы включить автоматический переход на другой ресурс** , если требуется автоматически отработка отказа в хранилище SQL Server соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="7fc2d-136">Если вы решили включить следящий сервер хранилища SQL Server для включения автоматического перехода на другой ресурс, выберите магазин и экземпляр из списка.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="7fc2d-137">Для задания нового хранилища SQL Server (и экземпляра хранилища следящего сервера, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="7fc2d-138">Разрешив доступ к базе данных соответствия, следует выбрать хранилище и экземпляр в списке **Резервное хранилище SQL Server для соответствия требованиям**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="7fc2d-139">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7fc2d-140">Установите флажок **включить зеркальное отображение хранилища SQL Server** , если вы хотите включить зеркальное отображение для хранилища SQL Server соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="7fc2d-141">Если вы решили включить зеркальное отображение хранилища SQL Server, выберите магазин и экземпляр из **зеркала хранилища SQL Server для обеспечения соответствия резервным копированием**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="7fc2d-142">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7fc2d-143">Установите флажок **использовать следящий сервер зеркального отображения SQL Server, чтобы включить автоматический переход на другой ресурс** , если требуется автоматически отработка отказа в хранилище SQL Server соответствия резервной копии.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="7fc2d-144">Если вы решили включить следящий сервер хранилища SQL Server для включения автоматического перехода на другой ресурс, выберите магазин и экземпляр из списка.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="7fc2d-145">Для задания нового хранилища SQL Server (и экземпляра хранилища следящего сервера, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="7fc2d-146">**Хранилище файлов** Выберите расположение хранилища файлов в списке или нажмите кнопку **создать** , чтобы создать новое хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="7fc2d-147">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="7fc2d-148">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="7fc2d-149">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="7fc2d-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7fc2d-150">См. также</span><span class="sxs-lookup"><span data-stu-id="7fc2d-150">See also</span></span>

[<span data-ttu-id="7fc2d-151">Планирование для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="7fc2d-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="7fc2d-152">Добавление постоянного сервера чата в топологию 2015 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7fc2d-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="7fc2d-153">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="7fc2d-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
