---
title: Перемещение оставшихся пользователей
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Вы можете переместить пользователей в новое развертывание Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server или skype для бизнеса Server Management Shell. Необходимо выполнить некоторые требования, чтобы обеспечить плавный переход на Skype для бизнеса Server 2019. Подробные сведения о предварительных условиях для выполнения процедур, которые см. в этом разделе, см. в разделе "Настройка клиентов для миграции". Подробные инструкции по перемещению пользователей см. в этапе 4. Перемещение тестовых пользователей в пилотный пул.
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753717"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="da04b-106">Перемещение оставшихся пользователей в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="da04b-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="da04b-107">Вы можете переместить пользователей в новое развертывание Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server или skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="da04b-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="da04b-108">Необходимо выполнить некоторые требования, чтобы обеспечить плавный переход на Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="da04b-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="da04b-109">Подробные сведения о предварительных условиях для выполнения процедур, которые см. в этом разделе, см. в разделе ["Настройка клиентов для миграции".](configure-clients-for-migration.md)</span><span class="sxs-lookup"><span data-stu-id="da04b-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="da04b-110">Подробные инструкции по перемещению пользователей см. в [этапе 4. Перемещение](phase-4-move-test-users-to-the-pilot-pool.md)тестовых пользователей в пилотный пул.</span><span class="sxs-lookup"><span data-stu-id="da04b-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="da04b-111">Оснастку "Пользователи и компьютеры Active Directory" или устаревшие средства администрирования нельзя использовать для перемещения пользователей из устаревшей среды в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="da04b-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="da04b-112">При перемещении пользователя в пул Skype для бизнеса Server 2019 данные пользователя перемещаются во серверную базу данных, связанную с новым пулом.</span><span class="sxs-lookup"><span data-stu-id="da04b-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="da04b-113">Это относится к активным собраниям, созданным пользователем старой системы.</span><span class="sxs-lookup"><span data-stu-id="da04b-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="da04b-114">Например, если устаревший пользователь настроил конференцию для собраний, эта конференция будет по-прежнему доступна в новом пуле Skype для бизнеса Server 2019 после того, как пользователь будет перемещен. </span><span class="sxs-lookup"><span data-stu-id="da04b-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="da04b-115">Сведения для доступа к этому собранию — те же **URL-адрес и код конференции**.</span><span class="sxs-lookup"><span data-stu-id="da04b-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="da04b-116">Единственное отличие заключается в том, что конференция теперь находится в пуле Skype для бизнеса Server 2019, а не в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="da04b-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="da04b-117">Размещение пользователей в Skype для бизнеса Server 2019 не требует одновременного развертывания обновленных клиентов.</span><span class="sxs-lookup"><span data-stu-id="da04b-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="da04b-118">Новые функциональные возможности станут доступными пользователям только после обновления до новой версии клиентского программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="da04b-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="da04b-119">Задача после миграции</span><span class="sxs-lookup"><span data-stu-id="da04b-119">Post migration task</span></span>

1. <span data-ttu-id="da04b-120">После перемещения пользователей убедитесь, что для них назначена политика конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="da04b-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="da04b-121">Чтобы собрания, организованные пользователями, которые находятся в Skype для бизнеса Server 2019, без проблем работали с федеративными пользователями, которые находятся в устаревшей установке, политика конференций, назначенная перенесенным пользователям, должна разрешать анонимных участников.</span><span class="sxs-lookup"><span data-stu-id="da04b-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="da04b-122">Политики конференций, разрешающие анонимным  участникам приглашать анонимных пользователей, выбранных в панели управления Skype для бизнеса Server 2019, и для  **allowAnonymousParticipantsInMeetings** в выходных данных из команды **Get-CsConferencingPolicy** в оболочке управления Skype для бизнеса Server задано true.</span><span class="sxs-lookup"><span data-stu-id="da04b-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

