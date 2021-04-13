---
title: Списание Skype для бизнеса Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Инструкции по выводу из эксплуатации Skype для бизнеса Server.
ms.openlocfilehash: 9c6051a07fc05297985b3692351c36791d8842bb
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656695"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="159ea-103">Удаление локального развертывания Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="159ea-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="159ea-104">В этой статье описывается, как удалить локальное развертывание Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="159ea-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="159ea-105">Это шаг 4 из следующих действий по выводу из эксплуатации локальной среды:</span><span class="sxs-lookup"><span data-stu-id="159ea-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="159ea-106">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="159ea-106">Step 1.</span></span> <span data-ttu-id="159ea-107">[Перемещение всех необходимых пользователей из локального в интернет.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="159ea-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="159ea-108">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="159ea-108">Step 2.</span></span> <span data-ttu-id="159ea-109">[Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="159ea-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="159ea-110">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="159ea-110">Step 3.</span></span> [<span data-ttu-id="159ea-111">Перемещение конечных точек гибридного приложения из локального в online</span><span class="sxs-lookup"><span data-stu-id="159ea-111">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="159ea-112">**Шаг 4. Удалите локальное развертывание Skype для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="159ea-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="159ea-113">(В этой статье)</span><span class="sxs-lookup"><span data-stu-id="159ea-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="159ea-114">Действия, описанные в этой статье, применяются только в том случае, если метод 2 используется для управления атрибутами пользователей, как [описано здесь.](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)</span><span class="sxs-lookup"><span data-stu-id="159ea-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="159ea-115">Если используется метод 1, не используйте описанные в этой статье действия для удаления серверов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="159ea-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="159ea-116">Вместо этого вы можете повторно образ серверов.</span><span class="sxs-lookup"><span data-stu-id="159ea-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="159ea-117">Для выполнения действий в этой статье необходимы привилегии как для группы администраторов схемы, так и для группы корпоративного администратора.</span><span class="sxs-lookup"><span data-stu-id="159ea-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="159ea-118">Эти привилегии необходимы для отмены схемы Skype для бизнес-сервера и изменения уровня леса в службы домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="159ea-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="159ea-119">Вы также должны быть членом группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="159ea-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="159ea-120">Подготовка к удалению развертывания Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="159ea-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="159ea-121">После перемещения всех необходимых учетных записей пользователей в облако могут по-прежнему оставаться некоторые локального объекта, такие как контакты и приложения, которые необходимо очистить.</span><span class="sxs-lookup"><span data-stu-id="159ea-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="159ea-122">Чтобы очистить эти объекты, используйте указанные ниже шаги и убедитесь, что вы входите в группу локального администратора и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="159ea-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="159ea-123">Обратите внимание, что ExUmContacts и PersistantChatEndPoints недоступны в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="159ea-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="159ea-124">Если у вас есть Skype для бизнеса Server 2019, соответствующие cmdlets в шагах ниже должны быть опущены.</span><span class="sxs-lookup"><span data-stu-id="159ea-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="159ea-125">Чтобы проверить, есть ли какие-либо контакты или приложения, связанные с локальной развертыванием Skype для бизнеса Server, запустите следующие cmdlets Skype для бизнеса Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="159ea-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. <span data-ttu-id="159ea-126">Просмотрите списки выходных данных из списков в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="159ea-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="159ea-127">Затем, если объекты можно удалить, запустите следующие кодлеты Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="159ea-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="159ea-128">Удаление локального развертывания Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="159ea-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="159ea-129">После выполнения всех предварительных действий можно удалить развертывание Skype для бизнеса, следуя следующим шагам:</span><span class="sxs-lookup"><span data-stu-id="159ea-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="159ea-130">Логически удалите развертывание Skype для бизнес-сервера, за исключением одного переднего конца, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="159ea-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   <span data-ttu-id="159ea-131">а.</span><span class="sxs-lookup"><span data-stu-id="159ea-131">a.</span></span> <span data-ttu-id="159ea-132">Обновите топологию Skype для бизнес-сервера, чтобы иметь единый пул переднего входа:</span><span class="sxs-lookup"><span data-stu-id="159ea-132">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

     - <span data-ttu-id="159ea-133">В Topology Builder скачайте новую копию и перейдите в пул Frontend.</span><span class="sxs-lookup"><span data-stu-id="159ea-133">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
     - <span data-ttu-id="159ea-134">Щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="159ea-134">Right-click the pool, and then click **Edit Properties**.</span></span>
     - <span data-ttu-id="159ea-135">В **Associations** отойдите от пула **ассоциированных элементов** (для компонентов мультимедиа) и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="159ea-135">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
     - <span data-ttu-id="159ea-136">Если имеется несколько пулов frontend, удалите ассоциации для всех остальных пулов.</span><span class="sxs-lookup"><span data-stu-id="159ea-136">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
     - <span data-ttu-id="159ea-137">Выберите **действие > удаление развертывания**.</span><span class="sxs-lookup"><span data-stu-id="159ea-137">Select **Action > Remove Deployment**.</span></span>
     - <span data-ttu-id="159ea-138">Выберите **действие > Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="159ea-138">Select **Action > Publish Topology**.</span></span>

    <span data-ttu-id="159ea-139">б.</span><span class="sxs-lookup"><span data-stu-id="159ea-139">b.</span></span> <span data-ttu-id="159ea-140">После публикации топологии выполните дополнительные действия, описанные в мастере.</span><span class="sxs-lookup"><span data-stu-id="159ea-140">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="159ea-141">Удалите каталоги конференций Skype для бизнеса Server, заняв следующий кодлет Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="159ea-141">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="159ea-142">Завершите развертывание Skype для бизнес-сервера, заняв следующий код Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="159ea-142">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="159ea-143">Если на этом шаге возвращается ошибка, откройте билет поддержки Майкрософт, чтобы получить помощь в удалении оставшихся устаревших объектов.</span><span class="sxs-lookup"><span data-stu-id="159ea-143">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="159ea-144">Удалите пункт управления централизованным хранилищем обслуживания, заняв следующий код Skype для бизнес-сервера PowerShell:</span><span class="sxs-lookup"><span data-stu-id="159ea-144">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="159ea-145">Отменять изменения лесного уровня домена Skype для бизнеса Server Active Directory, запуская следующий комдлет Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="159ea-145">Undo Skype for Business Server Active Directory Domain forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="159ea-146">Отмена схемы домена Skype для бизнеса Server Active Directory изменяется при запуске следующего cmdlet Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="159ea-146">Undo Skype for Business Server Active Directory Domain schema changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="159ea-147">См. также</span><span class="sxs-lookup"><span data-stu-id="159ea-147">See also</span></span>

- [<span data-ttu-id="159ea-148">Прекращение использования локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="159ea-148">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="159ea-149">Перемещение всех необходимых пользователей из локальной сети в интернет</span><span class="sxs-lookup"><span data-stu-id="159ea-149">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="159ea-150">Отключение гибридной конфигурации</span><span class="sxs-lookup"><span data-stu-id="159ea-150">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="159ea-151">Перемещение конечных точек гибридного приложения из локального в online</span><span class="sxs-lookup"><span data-stu-id="159ea-151">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)











