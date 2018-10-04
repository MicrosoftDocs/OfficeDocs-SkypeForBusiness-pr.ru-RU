---
title: Расширитель общих настроек сохраняемого чата
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Изменение общих параметров для сервера сохраняемого чата или пул серверов сохраняемого чата настраиваются путем определения следующих свойств:'
ms.openlocfilehash: 912cacaa050962b85d8e3f70bec78f01306909d6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374961"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="7afa8-103">Расширитель общих настроек сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="7afa8-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="7afa8-104">Изменение **общих** параметров для сервера сохраняемого чата или пул серверов сохраняемого чата настраиваются путем определения следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="7afa8-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="7afa8-105">**Общие**</span><span class="sxs-lookup"><span data-stu-id="7afa8-105">**General**</span></span>
  
- <span data-ttu-id="7afa8-106">**Полное доменное имя**: изменить этот параметр, чтобы определить полное доменное имя сервера сохраняемого чата или пул серверов сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="7afa8-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="7afa8-107">**Отображаемое имя пула Persistent Chat**: определение этот параметр, чтобы предоставить пользователю понятное и пользователя для чтения настройку сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="7afa8-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="7afa8-108">Этот параметр облегчит пользователям для связи данного сервера сохраняемого чата или пул серверов сохраняемого чата на основании отображаемое имя, а не сложнее понять полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="7afa8-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="7afa8-109">**Порт сохраняемых чатов**. Порт, предназначенный для сохраняемых чатов.</span><span class="sxs-lookup"><span data-stu-id="7afa8-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="7afa8-110">Измените параметры **связи** сервера сохраняемого чата или пул серверов сохраняемого чата настраиваются путем определения следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="7afa8-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="7afa8-111">**Связи**</span><span class="sxs-lookup"><span data-stu-id="7afa8-111">**Associations**</span></span>
  
- <span data-ttu-id="7afa8-112">**Хранилище SQL Server**. Выберите в списке хранилище SQL Server и при необходимости именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="7afa8-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="7afa8-113">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7afa8-114">Установите флажок **зеркальное отображение хранилища SQL Server для включения** , если вы хотите включить зеркальное отображение для основного хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7afa8-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="7afa8-115">Если вы хотите включить зеркальное отображение хранилища SQL Server, выберите хранилище и экземпляр в списке **зеркалирование хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="7afa8-116">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7afa8-117">Установите флажок **следящий сервер для включения автоматического переключения зеркального отображения с помощью SQL Server** , если необходимо использовать автоматическую отработку отказа основного хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7afa8-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="7afa8-118">Если вы хотите включить зеркальное отображение следящего сервера для включения автоматического переключения хранилище SQL Server, выберите хранилище и экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="7afa8-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="7afa8-119">Для задания нового хранилища SQL Server (и экземпляра хранилища следящего сервера, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="7afa8-120">Установите флажок **использовать резервного хранилища SQL Server возможность аварийного восстановления** , если вы хотите включить использование аварийного восстановления SQL Server</span><span class="sxs-lookup"><span data-stu-id="7afa8-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="7afa8-121">Разрешив аварийное восстановление, следует выбрать хранилище и экземпляр в списке **Резервное хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="7afa8-122">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7afa8-123">Установите флажок **зеркальное отображение хранилища SQL Server для включения** , если вы хотите включить зеркальное отображение для резервного копирования зеркальное отображение хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7afa8-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="7afa8-124">Если вы хотите включить зеркалирование резервного хранилища SQL Server, выберите хранилище и экземпляр в списке **зеркального хранилища архивации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="7afa8-125">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7afa8-126">Установите флажок **следящий сервер для включения автоматического переключения зеркального отображения с помощью SQL Server** , если необходимо использовать автоматическую отработку отказа резервного хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7afa8-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="7afa8-127">Если вы хотите включить зеркальное отображение следящего сервера для включения автоматического переключения хранилище SQL Server, выберите хранилище и экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="7afa8-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="7afa8-128">Для задания нового хранилища SQL Server (и экземпляра хранилища следящего сервера, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="7afa8-129">Если требуется доступ к базе данных соответствия, установите флажок **Включить соответствие**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="7afa8-130">Разрешив доступ к базе данных соответствия, следует выбрать хранилище и экземпляр в списке **Совместимое хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="7afa8-131">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7afa8-132">Установите флажок **зеркальное отображение хранилища SQL Server для включения** , если вы хотите включить зеркальное отображение для хранилища соответствия SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7afa8-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="7afa8-133">Если вы хотите включить зеркальное отображение хранилища SQL Server соответствия требованиям, выберите хранилище и экземпляр в списке **зеркального хранилища соответствия SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="7afa8-134">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7afa8-135">Установите флажок **следящий сервер для включения автоматического переключения зеркального отображения с помощью SQL Server** , если необходимо использовать автоматическую отработку отказа хранилища соответствия SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7afa8-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="7afa8-136">Если вы хотите включить зеркальное отображение следящего сервера для включения автоматического переключения хранилище SQL Server, выберите хранилище и экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="7afa8-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="7afa8-137">Для задания нового хранилища SQL Server (и экземпляра хранилища следящего сервера, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="7afa8-138">Разрешив доступ к базе данных соответствия, следует выбрать хранилище и экземпляр в списке **Резервное хранилище SQL Server для соответствия требованиям**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="7afa8-139">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7afa8-140">Установите флажок **зеркальное отображение хранилища SQL Server для включения** , если вы хотите включить зеркальное отображение для хранилища соответствия SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7afa8-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="7afa8-141">Если вы хотите включить зеркальное отображение хранилища SQL Server соответствия требованиям, выберите хранилище и экземпляр в списке **зеркального хранилища SQL Server соответствия резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="7afa8-142">Для задания нового хранилища SQL Server (и экземпляра, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7afa8-143">Установите флажок **следящий сервер для включения автоматического переключения зеркального отображения с помощью SQL Server** , если необходимо использовать автоматическую отработку отказа хранилища SQL Server для резервного копирования совместимости.</span><span class="sxs-lookup"><span data-stu-id="7afa8-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="7afa8-144">Если вы хотите включить зеркальное отображение следящего сервера для включения автоматического переключения хранилище SQL Server, выберите хранилище и экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="7afa8-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="7afa8-145">Для задания нового хранилища SQL Server (и экземпляра хранилища следящего сервера, если он требуется) щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7afa8-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="7afa8-146">**Хранение файлов** Выберите расположение хранилища файлов в списке, или нажмите кнопку **Создать** , чтобы создать новое хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="7afa8-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="7afa8-147">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="7afa8-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="7afa8-148">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="7afa8-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="7afa8-149">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="7afa8-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7afa8-150">См. также</span><span class="sxs-lookup"><span data-stu-id="7afa8-150">See also</span></span>

[<span data-ttu-id="7afa8-151">Планирование для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="7afa8-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="7afa8-152">Добавление сервера сохраняемого чата для вашей Скайп для топологии Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7afa8-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="7afa8-153">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="7afa8-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)