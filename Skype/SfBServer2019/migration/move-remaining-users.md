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
description: 'Вы можете переместить пользователей в новое развертывание Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server или консоли управления Skype для бизнеса Server. Для обеспечения плавного перехода на Skype для бизнеса Server 2019 необходимо соблюдение определенных требований. Дополнительные сведения о предварительных требованиях для выполнения процедур, описанных в этой статье, можно найти в разделе Настройка клиентов для миграции. Подробное описание действий по перемещению пользователей приведено в разделе Этап 4: перемещение тестовых пользователей в пилотный пул.'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753717"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="d0c53-106">Перемещение оставшихся пользователей в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="d0c53-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="d0c53-107">Вы можете переместить пользователей в новое развертывание Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server или консоли управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d0c53-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="d0c53-108">Для обеспечения плавного перехода на Skype для бизнеса Server 2019 необходимо соблюдение определенных требований.</span><span class="sxs-lookup"><span data-stu-id="d0c53-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="d0c53-109">Дополнительные сведения о предварительных требованиях для выполнения процедур, описанных в этой статье, можно найти в разделе [Настройка клиентов для миграции](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="d0c53-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="d0c53-110">Подробное описание действий по перемещению пользователей приведено в разделе [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d0c53-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d0c53-111">Вы не можете использовать оснастку "Active Directory — пользователи и компьютеры" или средства администрирования прежних версий для перемещения пользователей из старой среды в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d0c53-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="d0c53-112">При перемещении пользователя в пул Skype для бизнеса Server 2019 данные для пользователя перемещаются в фоновую базу данных, связанную с новым пулом.</span><span class="sxs-lookup"><span data-stu-id="d0c53-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d0c53-113">Это относится к активным собраниям, созданным пользователем старой системы.</span><span class="sxs-lookup"><span data-stu-id="d0c53-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="d0c53-114">Например, если устаревший пользователь настроил Конференц- **зал для собраний** , эта конференция по-прежнему будет доступна в новом пуле Skype для бизнеса Server 2019 после того, как пользователь был перемещен.</span><span class="sxs-lookup"><span data-stu-id="d0c53-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="d0c53-115">Сведения для доступа к этому собранию — те же **URL-адрес и код конференции**.</span><span class="sxs-lookup"><span data-stu-id="d0c53-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="d0c53-116">Единственное отличие состоит в том, что Конференция теперь размещается в пуле Skype для бизнеса Server 2019, а не в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="d0c53-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d0c53-117">Пользователи в Skype для бизнеса Server 2019 не требуют развертывания обновленных клиентов одновременно.</span><span class="sxs-lookup"><span data-stu-id="d0c53-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="d0c53-118">Новые функциональные возможности станут доступными пользователям только после обновления до новой версии клиентского программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="d0c53-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="d0c53-119">Задача после миграции</span><span class="sxs-lookup"><span data-stu-id="d0c53-119">Post migration task</span></span>

1. <span data-ttu-id="d0c53-120">После перемещения пользователей убедитесь, что для них назначена политика конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d0c53-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="d0c53-121">Чтобы убедиться, что собрания, организованные пользователями, размещенными в Skype для бизнеса Server 2019, тесно взаимодействуют с федеративными пользователями, размещенными на устаревшей установке, политика конференц-связи, назначенная для перенесенных пользователей, должна иметь анонимных участников.</span><span class="sxs-lookup"><span data-stu-id="d0c53-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="d0c53-122">Политики конференц-связи, которые позволяют анонимным участникам **Разрешить участникам приглашать анонимных пользователей** , выбранные в панели управления Skype для бизнеса Server 2019 и иметь для **аллованонимауспартиЦипантсинмитингс** значение **true** в выходных данных командлета **Get-CsConferencingPolicy** в командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d0c53-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

