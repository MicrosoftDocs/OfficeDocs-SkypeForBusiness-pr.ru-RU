---
title: Вывод из эксплуатации Skype для бизнеса Server
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
ms.openlocfilehash: e96c4cd37d09fc62fbfbe34a8b8d61c79ea08289
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454342"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="ccc45-103">Удаление локального развертывания Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ccc45-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="ccc45-104">В этой статье описывается, как удалить локальное развертывание Skype для бизнеса развертывания.</span><span class="sxs-lookup"><span data-stu-id="ccc45-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="ccc45-105">Это шаг 4 из следующих действий по выводу из эксплуатации локальной среды:</span><span class="sxs-lookup"><span data-stu-id="ccc45-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="ccc45-106">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="ccc45-106">Step 1.</span></span> <span data-ttu-id="ccc45-107">[Перемещение всех необходимых пользователей из локального в интернет.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="ccc45-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="ccc45-108">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="ccc45-108">Step 2.</span></span> <span data-ttu-id="ccc45-109">[Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="ccc45-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="ccc45-110">Этап 3.</span><span class="sxs-lookup"><span data-stu-id="ccc45-110">Step 3.</span></span> [<span data-ttu-id="ccc45-111">Перенос конечных точек гибридных приложений из локального в online</span><span class="sxs-lookup"><span data-stu-id="ccc45-111">Migrate hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="ccc45-112">**Шаг 4. Удалите локальное развертывание Skype для бизнеса развертывания.**</span><span class="sxs-lookup"><span data-stu-id="ccc45-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="ccc45-113">(В этой статье)</span><span class="sxs-lookup"><span data-stu-id="ccc45-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="ccc45-114">Действия, описанные в этой статье, применяются только в том случае, если метод 2 используется для управления атрибутами пользователей, как [описано здесь.](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)</span><span class="sxs-lookup"><span data-stu-id="ccc45-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="ccc45-115">Если используется метод 1, не используйте описанные в этой статье действия для удаления Skype для бизнеса серверов.</span><span class="sxs-lookup"><span data-stu-id="ccc45-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="ccc45-116">Вместо этого вы можете повторно образ серверов.</span><span class="sxs-lookup"><span data-stu-id="ccc45-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="ccc45-117">Для выполнения действий в этой статье необходимы привилегии как для группы администраторов схемы, так и для Enterprise администратора.</span><span class="sxs-lookup"><span data-stu-id="ccc45-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="ccc45-118">Эти привилегии необходимы для отмены Skype для бизнеса Server схемы и изменений на уровне лесов в службы домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ccc45-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="ccc45-119">Вы также должны быть членом группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ccc45-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="ccc45-120">Подготовка к удалению Skype для бизнеса развертывания</span><span class="sxs-lookup"><span data-stu-id="ccc45-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="ccc45-121">После перемещения всех необходимых учетных записей пользователей в облако могут по-прежнему оставаться некоторые локального объекта, такие как контакты и приложения, которые необходимо очистить.</span><span class="sxs-lookup"><span data-stu-id="ccc45-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="ccc45-122">Чтобы очистить эти объекты, используйте указанные ниже шаги и убедитесь, что вы входите в группу локального администратора и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ccc45-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="ccc45-123">Обратите внимание, что ExUmContacts и PersistantChatEndPoints недоступны в Skype для бизнеса Server 2019 г.</span><span class="sxs-lookup"><span data-stu-id="ccc45-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="ccc45-124">Если у вас Skype для бизнеса Server 2019 г., соответствующие cmdlets в шагах ниже должны быть опущены.</span><span class="sxs-lookup"><span data-stu-id="ccc45-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="ccc45-125">Чтобы проверить, есть ли контакты или приложения, связанные с развертыванием Skype для бизнеса Server локального развертывания, запустите следующие Skype для бизнеса Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ccc45-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

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
2. <span data-ttu-id="ccc45-126">Просмотрите списки выходных данных из списков в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="ccc45-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="ccc45-127">Затем, если объекты можно удалить, запустите следующие Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ccc45-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

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
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="ccc45-128">Удаление локального развертывания Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ccc45-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="ccc45-129">После выполнения всех предварительных действий можно удалить развертывание Skype для бизнеса, следуя следующим шагам:</span><span class="sxs-lookup"><span data-stu-id="ccc45-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="ccc45-130">Логически удалите развертывание Skype для бизнеса Server, за исключением одного переднего конца, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ccc45-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   1. <span data-ttu-id="ccc45-131">Обновите Skype для бизнеса Server топологии, чтобы иметь единый пул переднего входа:</span><span class="sxs-lookup"><span data-stu-id="ccc45-131">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

      1. <span data-ttu-id="ccc45-132">В Topology Builder скачайте новую копию и перейдите в пул Frontend.</span><span class="sxs-lookup"><span data-stu-id="ccc45-132">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
      1. <span data-ttu-id="ccc45-133">Щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ccc45-133">Right-click the pool, and then click **Edit Properties**.</span></span>
      1. <span data-ttu-id="ccc45-134">В **Associations** отойдите от пула **ассоциированных элементов** (для компонентов мультимедиа) и нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccc45-134">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
      1. <span data-ttu-id="ccc45-135">Если имеется несколько пулов frontend, удалите ассоциации для всех остальных пулов.</span><span class="sxs-lookup"><span data-stu-id="ccc45-135">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
      1. <span data-ttu-id="ccc45-136">Выберите **действие > удаление развертывания**.</span><span class="sxs-lookup"><span data-stu-id="ccc45-136">Select **Action > Remove Deployment**.</span></span>
      1. <span data-ttu-id="ccc45-137">Выберите **действие > Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="ccc45-137">Select **Action > Publish Topology**.</span></span>

    1. <span data-ttu-id="ccc45-138">После публикации топологии выполните дополнительные действия, описанные в мастере.</span><span class="sxs-lookup"><span data-stu-id="ccc45-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="ccc45-139">Удалите Skype для бизнеса Server конференций, заняв следующий Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ccc45-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="ccc45-140">Завершите развертывание Skype для бизнеса Server развертывания с помощью следующего Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ccc45-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="ccc45-141">Если на этом шаге возвращается ошибка, откройте билет поддержки Майкрософт, чтобы получить помощь в удалении оставшихся устаревших объектов.</span><span class="sxs-lookup"><span data-stu-id="ccc45-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="ccc45-142">Удалите пункт управления службами Центра управления магазином, заняв следующий Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ccc45-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="ccc45-143">Отмена Skype для бизнеса Server на уровне домена Active Directory при запуске следующего Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ccc45-143">Undo Skype for Business Server Active Directory domain-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="ccc45-144">Отменять Skype для бизнеса Server изменения уровня леса Active Directory, выполнив следующий Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ccc45-144">Undo Skype for Business Server Active Directory forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="ccc45-145">См. также</span><span class="sxs-lookup"><span data-stu-id="ccc45-145">See also</span></span>

- [<span data-ttu-id="ccc45-146">Прекращение использования локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ccc45-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="ccc45-147">Перемещение всех необходимых пользователей из локальной сети в интернет</span><span class="sxs-lookup"><span data-stu-id="ccc45-147">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="ccc45-148">Отключение гибридной конфигурации</span><span class="sxs-lookup"><span data-stu-id="ccc45-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="ccc45-149">Перемещение конечных точек гибридного приложения из локального в online</span><span class="sxs-lookup"><span data-stu-id="ccc45-149">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

