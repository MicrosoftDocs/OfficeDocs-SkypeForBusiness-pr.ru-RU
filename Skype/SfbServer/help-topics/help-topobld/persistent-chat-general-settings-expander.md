---
title: Расширитель общих настроек сохраняемого чата
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Общие параметры для сервера сохраняемой беседы или пула серверов сохраняемой беседы можно изменить, настроив или определив эти свойства:'
ms.openlocfilehash: 5c0884f4877e622a82b58ea914ffa934eecc3291
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823859"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="dc7ae-103">Расширитель общих параметров сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="dc7ae-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="dc7ae-104">Общие **параметры** для сервера сохраняемой беседы или пула серверов сохраняемой беседы можно изменить, настроив или определив эти свойства:</span><span class="sxs-lookup"><span data-stu-id="dc7ae-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="dc7ae-105">**Общие**</span><span class="sxs-lookup"><span data-stu-id="dc7ae-105">**General**</span></span>
  
- <span data-ttu-id="dc7ae-106">**Полное доменное имя:** изменение этого параметра для определения полного доменного имени сервера сохраняемого чата или пула серверов сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="dc7ae-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="dc7ae-107">**Отображаемое имя пула сохраняемого чата:** определите этот параметр, чтобы предоставить пользователю понятный и понятный параметр для сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="dc7ae-108">Этот параметр упрощает для пользователей связывать заданный сервер сохраняемого чата или пул серверов сохраняемого чата на основе отображаемого имени, а не более сложно понимать полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="dc7ae-109">**Порт непрерывных чатов**. Укажите порт, который используется для непрерывных чатов.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="dc7ae-110">Параметры **связи для** сервера сохраняемой беседы или пула серверов сохраняемой беседы можно изменить, настроив или определив эти свойства:</span><span class="sxs-lookup"><span data-stu-id="dc7ae-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="dc7ae-111">**Связи**</span><span class="sxs-lookup"><span data-stu-id="dc7ae-111">**Associations**</span></span>
  
- <span data-ttu-id="dc7ae-112">**SQL Server хранения:** выберите SQL Server и необязательный именовательный экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="dc7ae-113">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc7ae-114">Если вы хотите включить зеркальное **SQL Server** для основного SQL Server, выберите этот SQL Server зеркального SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="dc7ae-115">Если вы решили включить зеркальное SQL Server хранения, выберите хранилище и экземпляр в списке зеркального **SQL Server хранилище.**</span><span class="sxs-lookup"><span data-stu-id="dc7ae-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="dc7ae-116">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc7ae-117">Выберите **"Использовать SQL Server зеркальном** отображке", чтобы включить автоматический отбой, если необходимо автоматическое отключение основного SQL Server хранения.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="dc7ae-118">Если вы решили включить SQL Server зеркального хранения для автоматической отключки, выберите хранилище и экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="dc7ae-119">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр для хранилища-свидетеля.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="dc7ae-120">Выберите **резервные хранилища SQL Server** резервного копирования, чтобы включить проверку аварийного восстановления, если вы хотите включить SQL Server аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="dc7ae-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="dc7ae-121">Если включена возможность аварийного восстановления, выберите хранилище и экземпляр в списке **Резервное хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="dc7ae-122">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc7ae-123">Чтобы включить **зеркальное SQL Server** резервного копирования, выберите SQL Server зеркального хранения.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="dc7ae-124">Если вы решили включить зеркальное SQL Server резервного копирования, выберите хранилище и экземпляр в списке **Backup SQL Server store mirror.**</span><span class="sxs-lookup"><span data-stu-id="dc7ae-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="dc7ae-125">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc7ae-126">Выберите **"Использовать SQL Server зеркального** зеркального копирования", чтобы включить автоматический отбой, если необходимо автоматическое отключение резервного SQL Server резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="dc7ae-127">Если вы решили включить SQL Server зеркального хранения для автоматической отключки, выберите хранилище и экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="dc7ae-128">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр для хранилища-свидетеля.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="dc7ae-129">Установите флажок **Включить соответствие**, если необходимо включить использование базы данных соответствия.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="dc7ae-130">Если включено соответствие требованиям, выберите хранилище и экземпляр в списке **Совместимое хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="dc7ae-131">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc7ae-132">Если вы хотите **включить зеркальное SQL Server** для хранения соответствия требованиям, выберите SQL Server зеркального SQL Server хранения.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="dc7ae-133">Если вы решили включить зеркальное SQL Server соответствия требованиям, выберите хранилище и экземпляр в списке соответствия SQL Server **зеркальном хранилище.**</span><span class="sxs-lookup"><span data-stu-id="dc7ae-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="dc7ae-134">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc7ae-135">Выберите свидетель **SQL Server использования** зеркального отключа, чтобы включить автоматический отбой, если необходимо автоматически отключить хранилище SQL Server соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="dc7ae-136">Если вы решили включить SQL Server зеркального хранения для автоматической отключки, выберите хранилище и экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="dc7ae-137">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр для хранилища-свидетеля.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="dc7ae-138">Если включено соответствие требованиям, выберите хранилище и экземпляр в списке **Зеркало резервного совместимого хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="dc7ae-139">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc7ae-140">Если вы хотите **включить зеркальное SQL Server** для хранения соответствия требованиям, выберите SQL Server зеркального SQL Server хранения.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="dc7ae-141">Если вы решили включить зеркальное SQL Server хранения соответствия требованиям, выберите хранилище и экземпляр в списке "Резервное копирование соответствия SQL Server **зеркальном хранилище".**</span><span class="sxs-lookup"><span data-stu-id="dc7ae-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="dc7ae-142">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc7ae-143">Выберите **"Использовать SQL Server зеркального** зеркального копирования", чтобы включить автоматический отбой, если необходимо автоматически отключить резервное хранилище соответствия SQL Server резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="dc7ae-144">Если вы решили включить SQL Server зеркального хранения для автоматической отключки, выберите хранилище и экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="dc7ae-145">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр для хранилища-свидетеля.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="dc7ae-146">**Хранилище файлов** Выберите расположение для хранения файлов в  списке или нажмите кнопку "Создать", чтобы создать новое хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="dc7ae-147">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="dc7ae-148">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="dc7ae-149">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="dc7ae-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dc7ae-150">См. также</span><span class="sxs-lookup"><span data-stu-id="dc7ae-150">See also</span></span>

[<span data-ttu-id="dc7ae-151">Планирование сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc7ae-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="dc7ae-152">Добавление сервера сохраняемой беседы в топологию Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc7ae-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="dc7ae-153">Настройка высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc7ae-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
