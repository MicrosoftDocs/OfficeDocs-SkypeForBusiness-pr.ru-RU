---
title: Расширитель общих настроек сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Вы можете изменить общие параметры сервера сохраняемого чата или пула серверов сохраняемого чата, настроив или определив следующие свойства:'
ms.openlocfilehash: aae63b2d736f02b717b47aeff5fccb9b676daf99
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216000"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="b418e-103">Расширитель общих настроек сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="b418e-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="b418e-104">Вы можете изменить **Общие** параметры сервера сохраняемого чата или пула серверов сохраняемого чата, настроив или определив следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="b418e-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="b418e-105">**Общие сведения**</span><span class="sxs-lookup"><span data-stu-id="b418e-105">**General**</span></span>
  
- <span data-ttu-id="b418e-106">**Полное доменное**имя: измените этот параметр, чтобы определить полное доменное имя сервера сохраняемого чата или пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b418e-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="b418e-107">**Отображаемое имя пула сохраняемого чата**: определите этот параметр, чтобы обеспечить удобные и пользовательские параметры для сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="b418e-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="b418e-108">Этот параметр упрощает для пользователей сопоставление заданному серверу сохраняемого чата или пула серверов сохраняемого чата на основе отображаемого имени, а не более сложного представления полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="b418e-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="b418e-109">**Порт непрерывных чатов**. Укажите порт, который используется для непрерывных чатов.</span><span class="sxs-lookup"><span data-stu-id="b418e-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="b418e-110">Вы можете изменить параметры **связи** для сервера сохраняемого чата или пула серверов сохраняемого чата, настроив или определив следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="b418e-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="b418e-111">**Связанных**</span><span class="sxs-lookup"><span data-stu-id="b418e-111">**Associations**</span></span>
  
- <span data-ttu-id="b418e-112">**Хранилище SQL Server**: выберите в списке Хранилище SQL Server и необязательный именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b418e-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="b418e-113">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b418e-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b418e-114">Установите флажок **включить зеркалирование хранилища SQL Server** , если вы хотите включить зеркальное отображение для основного хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b418e-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="b418e-115">Если включено зеркальное отображение хранилища SQL Server, выберите хранилище и экземпляр в списке **зеркальное отображение хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b418e-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="b418e-116">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b418e-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b418e-117">Установите флажок **использовать следящий сервер зеркального отображения SQL Server для включения автоматического перехода** на другой ресурс, если требуется автоматическая отработка отказа основного хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b418e-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="b418e-118">Если вы решили включить следящий сервер хранилища SQL Server для автоматического перехода на другой ресурс, выберите хранилище и экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="b418e-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="b418e-119">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр для хранилища-свидетеля.</span><span class="sxs-lookup"><span data-stu-id="b418e-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="b418e-120">Установите флажок **использовать резервные хранилища SQL Server для включения аварийного восстановления** , если необходимо включить аварийное восстановление SQL Server</span><span class="sxs-lookup"><span data-stu-id="b418e-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="b418e-121">Если включена возможность аварийного восстановления, выберите хранилище и экземпляр в списке **Резервное хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b418e-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="b418e-122">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b418e-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b418e-123">Установите флажок **включить зеркалирование хранилища SQL Server** , если вы хотите включить зеркальное отображение для резервного хранилища SQL Server зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="b418e-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="b418e-124">Если вы решили включить зеркальное отображение хранилища SQL Server, выберите хранилище и экземпляр в списке **резервная копия хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b418e-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="b418e-125">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b418e-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b418e-126">Установите флажок **использовать следящий сервер зеркального отображения SQL Server для автоматического перехода** на другой ресурс, если требуется автоматическая отработка отказа резервного хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b418e-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="b418e-127">Если вы решили включить следящий сервер хранилища SQL Server для автоматического перехода на другой ресурс, выберите хранилище и экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="b418e-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="b418e-128">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр для хранилища-свидетеля.</span><span class="sxs-lookup"><span data-stu-id="b418e-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="b418e-129">Установите флажок **Включить соответствие**, если необходимо включить использование базы данных соответствия.</span><span class="sxs-lookup"><span data-stu-id="b418e-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="b418e-130">Если включено соответствие требованиям, выберите хранилище и экземпляр в списке **Совместимое хранилище SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b418e-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="b418e-131">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b418e-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b418e-132">Установите флажок **включить зеркалирование хранилища SQL Server** , если необходимо включить зеркальное отображение для хранилища SQL Server соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b418e-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="b418e-133">Если включено зеркальное отображение хранилища SQL Server соответствия требованиям, выберите хранилище и экземпляр из списка **соответствие зеркальному хранилищу SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b418e-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="b418e-134">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b418e-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b418e-135">Установите флажок **использовать следящий сервер зеркального отображения SQL Server для включения автоматического перехода** на другой ресурс, если требуется автоматическая отработка отказа хранилища SQL Server соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b418e-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="b418e-136">Если вы решили включить следящий сервер хранилища SQL Server для автоматического перехода на другой ресурс, выберите хранилище и экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="b418e-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="b418e-137">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр для хранилища-свидетеля.</span><span class="sxs-lookup"><span data-stu-id="b418e-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="b418e-138">Если включено соответствие требованиям, выберите хранилище и экземпляр в списке **Зеркало резервного совместимого хранилища SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b418e-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="b418e-139">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b418e-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b418e-140">Установите флажок **включить зеркалирование хранилища SQL Server** , если необходимо включить зеркальное отображение для хранилища SQL Server соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="b418e-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="b418e-141">Если включено зеркальное отображение хранилища SQL Server соответствия требованиям, выберите хранилище и экземпляр в списке **зеркало резервного хранилища SQL Server для соответствия резервному копированию**.</span><span class="sxs-lookup"><span data-stu-id="b418e-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="b418e-142">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b418e-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b418e-143">Установите флажок **использовать следящий сервер зеркального отображения SQL Server для автоматического** перехода на другой ресурс, если требуется автоматическая отработка отказа хранилища SQL Server соответствия резервных копий.</span><span class="sxs-lookup"><span data-stu-id="b418e-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="b418e-144">Если вы решили включить следящий сервер хранилища SQL Server для автоматического перехода на другой ресурс, выберите хранилище и экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="b418e-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="b418e-145">Щелкните элемент **Создать**, чтобы определить новое хранилище SQL Server и необязательный экземпляр для хранилища-свидетеля.</span><span class="sxs-lookup"><span data-stu-id="b418e-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="b418e-146">**Хранилище файлов** Выберите расположение хранилища файлов в списке или нажмите кнопку **создать** , чтобы создать новое хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="b418e-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="b418e-147">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="b418e-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="b418e-148">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="b418e-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="b418e-149">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="b418e-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b418e-150">См. также</span><span class="sxs-lookup"><span data-stu-id="b418e-150">See also</span></span>

[<span data-ttu-id="b418e-151">Планирование сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b418e-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="b418e-152">Добавление сервера сохраняемого чата к топологии Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b418e-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="b418e-153">Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b418e-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
